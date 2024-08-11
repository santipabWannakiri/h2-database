# h2-database

### Connection Modes
The following connection modes are supported:
Embedded mode (local connections using JDBC)
Server mode (remote connections using JDBC or ODBC over TCP/IP)
Mixed mode (local and remote connections at the same time)


### Creating New Databases
 java -cp ./h2-*.jar org.h2.tools.Shell

 
### Starting the Server Tool from Command Line
java -cp ./h2-*.jar org.h2.tools.Server -tcp -tcpAllowOthers -tcpPort 8083


 java -cp h2*.jar org.h2.tools.Server -ifNotExists
