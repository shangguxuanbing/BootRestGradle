# BootRestGradle
Spring Boot Rest with Spring Security and HTTP Basic Authentication using Mysql  

# Environment
Spring Boot 1.4.0 , Spring Security 4.0.3 , HTTP Basic Authentication<br>
Gradle<br>
mysql , mybatis 3.3.1 , mybatis-spring 1.2.4<br>
using @RestController No jerysy<br>
Logback<br>
External Tomcat 8 with https<br>
Test URL : https://localhost:8443/BootRestGradle/api/users

# HTTP Basic Authentication
include request Header : Authorization: Basic cmVzdDpyZXN0<br>
or<br>
https://rest:rest@localhost:8443/BootRestGradle/api/users

# Tomcat Datasource JNDI
```
<GlobalNamingResources>
<Resource auth="Container" driverClassName="com.mysql.jdbc.Driver" 
loginTimeout="10" maxActive="200" maxIdle="8" maxWait="5000" 
name="jdbc/sim" username="dbuser" password="1234" 
type="javax.sql.DataSource"
url="jdbc:mysql://db.example.com:3306/exampledb?zeroDateTimeBehavior=convertToNull"/>      
</GlobalNamingResources>

<Context docBase="BootRestGradle" path="/BootRestGradle" reloadable="true">
<ResourceLink global="jdbc/sim" name="jdbc/sim" type="javax.sql.DataSource"/>
</Context>
```

# Tomcat SSL
```
    <Connector SSLEnabled="true" clientAuth="false" 
    keystoreFile="C:/job/sts/Servers/Tomcat v8.0 Server at localhost-config/.keystore" 
    keystorePass="1234" keystoreType="pkcs12" maxThreads="150" port="8443"
    protocol="org.apache.coyote.http11.Http11Protocol" scheme="https" secure="true" sslProtocol="TLS"/>
```
