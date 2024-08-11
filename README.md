# h2-database

### Connection Modes
The following connection modes are supported:
* Embedded mode (local connections using JDBC)
* Server mode (remote connections using JDBC or ODBC over TCP/IP)
* Mixed mode (local and remote connections at the same time)

[Connection Modes](https://www.h2database.com/html/features.html#connection_modes)

### Quick start with Server Mode
1. Download Binary JAR https://www.h2database.com/html/download.html
2. Start the H2 server with TCP connections enabled and the console active, but configure it to prevent database creation through TCP connections.
```sh
  java -cp h2-*.jar org.h2.tools.Server -tcp -tcpAllowOthers -tcpPort 8083 -web -webAllowOthers -webPort 8082
```
3. Create database with local
```sh
java -cp h2-*.jar org.h2.tools.Shell    

Welcome to H2 Shell 2.3.230 (2024-07-15)
Exit with Ctrl+C
URL       jdbc:h2:~/demo
Driver   org.h2.Driver
User      sa
Password  
```
4. Access console : http://{IP}:8082
5. Spring boot application configuration
```yml
spring.datasource.url=jdbc:h2:tcp://{IP}:8083/~/demo
spring.datasource.driverClassName=org.h2.Driver
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.datasource.username=sa
spring.datasource.password=
#spring.jpa.show-sql = true
spring.jpa.hibernate.ddl-auto = create-drop
```

[Server Modes](https://h2database.com/html/tutorial.html#using_server)

### Additional configuration
```sh
java -cp h2-*.jar org.h2.tools.Server -tcp -tcpAllowOthers -tcpPort 8083 -pg -pgAllowOthers -pgPort 5435 -web -webAllowOthers -webPort 8082 -ifNotExists
```
* tcpAllowOthers: Allows remote TCP connections.
* pgAllowOthers: Allows remote PostgreSQL-compatible connections.
* webAllowOthers: Allows remote access to the Web Console.
* ifNotExists: Used in JDBC URLs to allow database creation if it doesn’t exist (not applicable to Server tool).
