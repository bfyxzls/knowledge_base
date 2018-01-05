
### authorization server升级
```
clients.inMemory()
                .withClient("android")
                .scopes("xx")
                .secret("$2a$10$sCeoatJoccD4y1ff8AhdROLd2u6AWYBwH7YrbWXxdk6fA4VGhGITm")
                .authorizedGrantTypes("password", "authorization_code", "refresh_token")
```

### RedisTokenStore升级
针对RedisTokenStore出现的`NoSuchMethodError RedisConnection.set([B[B)V`错误，目前解决方案是重写`RedisTokenStore`第160行`conn..set(accessKey, serializedAccessToken);`修改为`conn.stringCommands().set(accessKey, serializedAccessToken);`
在下次版本更新时，若RedisTokenStore代码已正常，应删除重写的代码

### ResourceServer升级
因升级`Spring Boot 2.0`，`Spring Boot 1.5`的`autoconfigure`中关于`ResourceServer`的自动配置被移除，将被移到`Spring Security`项目中，目前的替代方案为使用`https://github.com/spring-projects/spring-security-oauth2-boot.git`


### pay-module升级
`HttpMessageConverters`包由`org.springframework.boot.autoconfigure.web.HttpMessageConverters`变更为`org.springframework.boot.autoconfigure.http.HttpMessageConverters`
`feign`的依赖变更为`spring-cloud-starter-openfeign`


### ElasticSearch升级
- 依赖变化
```xml
<dependency>
			<groupId>org.elasticsearch.client</groupId>
			<artifactId>x-pack-transport</artifactId>
			<version>5.5.3</version>
		</dependency>

<repository>
			<id>elasticsearch-releases</id>
			<url>https://artifacts.elastic.co/maven</url>
			<releases>
				<enabled>true</enabled>
			</releases>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</repository>
```
- 连接配置变化
```yaml
spring:
  data:
    elasticsearch:
      cluster-nodes: 192.168.1.222:9300
      cluster-name: docker-cluster
      properties:
        username: elastic
        password: changeme
```
- 增加配置
```java
@Configuration
@EnableConfigurationProperties(ElasticsearchProperties.class)
public class EsConfig {

    private final ElasticsearchProperties properties;

    public EsConfig(ElasticsearchProperties properties){
        this.properties = properties;
    }

    @Bean
    public TransportClient elasticTransportClient() throws UnknownHostException {
        String usernameAndPassword = properties.getProperties().get("username") + ":" + properties.getProperties().get("password");
        Settings settings = Settings.builder().put("cluster.name", properties.getClusterName())
                .put("client.transport.sniff", false)
                .put("xpack.security.user", usernameAndPassword)
                .build();
        String server = properties.getClusterNodes().split(":")[0];
        Integer port = Integer.parseInt(properties.getClusterNodes().split(":")[1]);
        return new PreBuiltXPackTransportClient(settings).addTransportAddress(new InetSocketTransportAddress(InetAddress.getByName(server), port));
    }
}
```

### Spring-data 2.0 api变化
- `findOne`: `findById`,返回Option
- `save(list)`: `saveAll`
- ``

### 服务无故shutdown
- 需配置`log4j`
- `feign client`添加`oauth2`配置
```java
public class FeignClientOAuthConfig {

    @Bean
    public RequestInterceptor requestInterceptor(OAuth2ClientContext oauth2ClientContext, OAuth2ProtectedResourceDetails resource){
        return new OAuth2FeignRequestInterceptor(oauth2ClientContext, resource);
    }

    @Bean
    public DefaultOAuth2ClientContext oauth2ClientContext() {
        return new DefaultOAuth2ClientContext(new DefaultAccessTokenRequest());
    }

    @Bean
    public AuthorizationCodeResourceDetails oauth2RemoteResource() {
        return new AuthorizationCodeResourceDetails();
    }
}

```