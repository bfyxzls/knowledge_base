#  Java 8 日期时间 API   #
Java 8通过发布新的Date-Time API (JSR 310)来进一步加强对日期与时间的处理。
在旧版的 Java 中，日期时间 API 存在诸多问题，其中有：
- **非线程安全** − java.util.Date 是非线程安全的，所有的日期类都是可变的，这是Java日期类最大的问题之一。
- **设计很差** − Java的日期/时间类的定义并不一致，在java.util和java.sql的包中都有日期类，此外用于格式化和解析的类在java.text包中定义。java.util.Date同时包含日期和时间，而java.sql.Date仅包含日期，将其纳入java.sql包并不合理。另外这两个类都有相同的名字，这本身就是一个非常糟糕的设计。
- **时区处理麻烦** − 日期类并不提供国际化，没有时区支持，因此Java引入了java.util.Calendar和java.util.TimeZone类，但他们同样存在上述所有的问题。

Java 8 在 **java.time** 包下提供了很多新的 API。以下为两个比较重要的 API：
- **Local(本地)** − 简化了日期时间的处理，没有时区的问题。
- **Zoned(时区)** − 通过制定的时区处理日期时间。

新的**java.time**包涵盖了所有处理日期，时间，日期/时间，时区，时刻（instants），过程（during）与时钟（clock）的操作。

## 本地化日期（LocalDate） ##
Java 8中有一个叫LocalDate的类，它只包含日期，没有时间。以下是它的一些常用的API：
1. 获取当天的日期
    ``` 
	LocalDate localDate = LocalDate.now();
    System.out.println("Today's Local date : " + localDate); 
	```	
    Output : 
    Today's Local date : 2017-07-14
1. 独立获取当前的年月日
    ```
    int year = localDate.getYear(); 
    int month = localDate.getMonthValue(); 
    int day = localDate.getDayOfMonth(); 
    System.out.printf("Year : %d Month : %d day : %d \t %n", year, month, day); 
    ```    

    Output:
    Year : 2017 Month : 7 day : 14
1. 创建某个特定的日期
    ```
    LocalDate dateOfBirth = LocalDate.of(1994, 08, 27);
    System.out.println("Your Date of birth is : " + dateOfBirth); 
    ```

    Output：
	Your Date of birth is : 1994-08-27
1. 检查两个日期是否相等
    ```
    if(!dateOfBirth.equals(localDate)){ 
        System.out.printf("dateOfBirth %s and localDate %s are not the same date %n", dateOfBirth, localDate); 
    } 
   ```
Output:
dateOfBirth 1994-08-27 and localDate 2017-07-14 are not the same date
1. 检查每年的重复事件
MonthDay类，只包含月日信息，不包含年信息，可以用它来代表每年重复出现的一些日子，比如生日、节日、结婚纪念日等。
	```
	MonthDay birthday = MonthDay.of(dateOfBirth.getMonth(), dateOfBirth.getDayOfMonth());
	MonthDay currentMonthDay = MonthDay.from(localDate);
	if(currentMonthDay.equals(birthday)){
	    System.out.println("Happy Birthday！");
	}else{
	    System.out.println("Sorry, today is not your birthday！");
	}
	``` 
	Output:
	Sorry, today is not your birthday!
1. 检查固定的日期
正如MonthDay表示的是某个重复出现的日子的，YearMonth又是另一个组合，它代表的是像信用卡还款日，定期存款到期日这类的日期。其中lengthOfMonth()这个方法返回的是这个YearMonth实例有多少天，这对于检查2月到底是28天还是29天可是非常有用的。
    ```
    YearMonth currentYearMonth = YearMonth.now();`  `System.out.printf("Days in month year %s: %d%n",currentYearMonth, currentYearMonth.lengthOfMonth()); 
    YearMonth creditCardExpiry = YearMonth.of(2018, Month.FEBRUARY);
    System.out.printf("Your credit card expires on %s %n", creditCardExpiry); 
    ```
    Output:
    Days in month year 2017-07: 31 
    Your credit card expires on 2018-02
1. 增加当前日期的日、周、月
    ```
    LocalDate nextWeek = localDate.plus(1, ChronoUnit.WEEKS);
    System.out.println("Today is : " + localDate); 
    System.out.println("Date after 1 week : " + nextWeek); 
    ```
    OutPut:
    Today is : 2017-07-14 
    Date after 1 week : 2017-07-21
    可以用同样的方法来增加月、年、小时、分钟等，查看Java API中的ChronoUnit类来获取更多的选项。
1. 减少当前日期的日、周、月
    ```
    LocalDate previousYear = localDate.minus(1, ChronoUnit.YEARS); 
    System.out.println("Date before 1 year : " + previousYear); 
    LocalDate nextYear = localDate.plus(1, ChronoUnit.YEARS); 
    System.out.println("Date after 1 year : " + nextYear); 
    ```
    Output:
    Date before 1 year : 2016-07-14 
	Date after 1 year : 2018-07-14
1. 日期的比较（之前 or 之后）
如果调用方法的那个日期比给定的日期要早的话，isBefore()方法会返回true。
如果调用方法的那个日期比给定的日期要晚的话，isAfter()方法会返回true。
    ```
    LocalDate today = LocalDate.Now();
    LocalDate tomorrow = localDate.plus(1, ChronoUnit.DAYS);
    if(tommorow.isAfter(today)){ 
    	System.out.println("Tomorrow comes after today");} 
    	LocalDate yesterday = localDate.minus(1, ChronoUnit.DAYS) 
    if(yesterday.isBefore(today)){ 
    	System.out.println("Yesterday is day before today");
    } 
    ```
    Output:
    Tomorrow comes after today 
    Yesterday is day before today
1. 检查是否是闰年
    ```
    if(localDate.isLeapYear()){
         System.out.println("This year is Leap year"); 
    }else { 
         System.out.println("2017 is not a Leap year"); 
    } 
    ```
    Output:
    2017 is not a Leap year

1. 计算两个日期间相隔的日、月、周、年
java.time.Period类可以用来完成这个功能。
    ```
    LocalDate java8ReleaseDate = LocalDate.of(2014, Month.MARCH, 14);
    Period period = Period.between(java8ReleaseDate，LocalDate); 
    System.out.println("Months left between current date and Java 8 release date : " +  (period.getYears()*12+period.getMonths()) );
	```
	Output:
	Months left between current date and Java 8 release date : 40
## 本地化时间（LocalTime） ##
Java 8中有一个叫LocalTime的类，它只包含时间，没有日期。以下是它的一些常用的API：
1. 获取当前的时间
	```
    LocalTime localTime = LocalTime.now();
    System.out.println("local time now : " + localTime);
	``` 
    Output：
	local time now : 11:19:329.482   // in hour, minutes, seconds, nano seconds

1. 增加当前时间的小时数
	```
    LocalTime newLocalTime = localTime.plusHours(2); // adding two hours 
    System.out.println("Time after 2 hours : " + newLocalTime);
	```
    Output：
	Time after 2 hours : 13:19:329.482
## 时钟类（Clock） ##
Java 8中自带了一个Clock类，你可以用它来获取某个时区下当前的瞬时时间，日期或者时间。可以用Clock来替代System.currentTimeInMillis()与 TimeZone.getDefault()方法。
1. 获取当前时间
	```
    // Returns the current time based on your system clock and set to UTC. 
	Clock clock = Clock.systemUTC(); 
	System.out.println("Clock : " + clock); 
	// Returns time based on system clock zone Clock 
	defaultClock = Clock.systemDefaultZone(); 
	System.out.println("Clock : " + clock);
	```
	Output:
	Clock : SystemClock[Z] 
	Clock : SystemClock[Z]

## 时区类（LocalDateTime） ##
Java 8不仅将日期和时间进行了分离，同时还有时区。现在已经有好几组与时区相关的类了，比如ZonId代表的是某个特定的时区，而ZonedDateTime代表的是带时区的时间。
1. 不同时区的时间转换
	```
    LocalDateTime localtDateAndTime = LocalDateTime.now(); 
    // Date and time with timezone in Java 8 ZoneId america = ZoneId.of("America/New_York"); 
    ZonedDateTime dateAndTimeInNewYork = ZonedDateTime.of(localtDateAndTime, america ); 
	System.out.println("Current date and time in a particular timezone : " + dateAndTimeInNewYork); 
	```
    Output:
	Current date and time in a particular timezone : 2017-07-14T11:38:10.916-04:00[America/New_York]

1. 带时区偏移量的日期与时间
在Java 8里面，你可以用ZoneOffset类来代表某个时区，比如印度是GMT或者UTC5：30，你可以使用它的静态方法ZoneOffset.of()方法来获取对应的时区。只要获取到了这个偏移量，你就可以拿LocalDateTime和这个偏移量创建出一个OffsetDateTime。
	```
	LocalDateTime datetime = LocalDateTime.of(2017, Month.JULY, 14, 12, 30);
	ZoneOffset offset = ZoneOffset.of("+05:30");
	OffsetDateTime date = OffsetDateTime.of(datetime, offset); 
	System.out.println("Date and Time with timezone offset in Java : " + date);
	```
	Output:
	Date and Time with timezone offset in Java : 2017-07-14T12:30+05:30
## 时间戳（Instant） ##
1. 获取当前时间戳
	```
	Instant timestamp = Instant.now();
	System.out.println("What is value of this instant " + timestamp);
	```
	Output:
	What is value of this instant 2017-07-14T03:49:18.868Z
## 日期解析/格式化 ##
在Java 8之前，时间日期的格式化是利用SimpleDateFormat实现的，但SimpleDateFormat并不是线程安全的，而用作本地变量来格式化又显得有些笨重。Java 8，这次它引入了一个全新的线程安全的日期与时间格式器。它还自带了一些预定义好的格式器，包含了常用的日期格式。
1. 用预定义格式器对日期进行解析
	```
	String dayAfterTommorrow = "20170715"; 
	LocalDate formatted = LocalDate.parse(dayAfterTommorrow, DateTimeFormatter.BASIC_ISO_DATE);
	System.out.printf("Date generated from String %s is %s %n", dayAfterTommorrow, formatted); 
	```
	Output:
	Date generated from String 20170715 is 2017-07-15

1. 用自定义格式器对日期进行解析
	```
	String isFriday = "07 14 2017";
	try {
	    DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MM dd yyyy");     
	    LocalDate holiday = LocalDate.parse(goodFriday, formatter); 
	    System.out.printf("Successfully parsed String %s, date is %s%n", goodFriday, holiday);
	} catch (DateTimeParseException ex) {`
	    System.out.printf("%s is not parsable!%n", goodFriday);
	    ex.printStackTrace(); 
	}
	```
	Output:
	Successfully parsed String 07 14 2017, date is 2017-07-14 
1. 对日期进行格式化，转换成字符串
	```
	LocalDateTime arrivalDate = LocalDateTime.now();
	try { 
	    DateTimeFormatter format = DateTimeFormatter.ofPattern("MMM dd yyyy hh:mm a"); 
	    String landing = arrivalDate.format(format); 
	    System.out.printf("Arriving at : %s %n", landing);
    } catch (DateTimeException ex) { 
	    System.out.printf("%s can't be formatted!%n", arrivalDate); 
	    ex.printStackTrace(); 
	} 
	```
	Output:
    Arriving at : 七月 14 2017 11:55 上午

    
