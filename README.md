# h2-database

### Connection Modes
The following connection modes are supported:
Embedded mode (local connections using JDBC)
Server mode (remote connections using JDBC or ODBC over TCP/IP)
Mixed mode (local and remote connections at the same time)


### Starting the Server Tool from Command Line
To allow remote database creation, you can use the -ifNotExists parameter:
java -cp h2-*.jar org.h2.tools.Server -tcp -tcpAllowOthers -tcpPort 8083 -ifNotExists

### Creating New Databases
java -cp h2-*.jar org.h2.tools.Shell -url jdbc:h2:tcp://192.168.1.152:8083/~/demo1;IFEXISTS=FALSE -user sa -password



### Start H2 with default configuration
 java -cp h2*.jar org.h2.tools.Server -ifNotExists


java -cp h2-*.jar org.h2.tools.Server -tcp -tcpAllowOthers -tcpPort 8083 -web -webAllowOthers -webPort 8082




-tcpAllowOthers: Allows remote TCP connections.
-pgAllowOthers: Allows remote PostgreSQL-compatible connections.
-webAllowOthers: Allows remote access to the Web Console.
-ifNotExists: Used in JDBC URLs to allow database creation if it doesn’t exist (not applicable to Server tool).

