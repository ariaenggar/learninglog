# Spring Log

Used for spring family tools, spring boot, spring cloud, etc..


### Spring Centralized Configuration
(https://spring.io/guides/gs/centralized-configuration/)

#### 5 Jul 2018 15:49

Trying spring.cloud.config.server.git.uri=${HOME} not working, using complete full url with "file://" prefix. spring.cloud.config.server.git.uri=spring.cloud.config.server.git.uri=file://C:/Users/LEGION/Desktop/config
(check: https://github.com/spring-guides/gs-centralized-configuration/issues/3, dsyer said it works.)

Firewall turned off with BlockInbound,AllowOutbound policy. Will try AllowInbound at home. Got to go now (15:49)

#### 5 Jul 2018 21:59

All firewall turned off, the client still can't read config using ${HOME}. Will try again later. Using file:// prefix for now.


### Spring Hot Swap with spring-boot-devtools on IntelliJ

#### 9 Jul 2018 14:59

1. add "runtime('org.springframework.boot:spring-boot-devtools')" to dependencies
2. File -> Settings -> Build, Execution, Deployment -> Compiler -> (at right panel) set "Build automatically" to checked -> OK
3. Ctrl + Shift + A -> type "registry" -> select "Regsitry..." (make sure it's with the ellipsis/three dots)
4. Find "compiler.automake.allow.when.app.running" key, set value to true (checked) -> Close
5. Restart IntelliJ


### Spring Boot to DB, HikariCP

#### 9 Jul 2018 15:43

It is said that: 'If you use the spring-boot-starter-jdbc or spring-boot-starter-data-jpa “starters”, you automatically get a dependency to HikariCP.'
https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-sql.html#boot-features-connect-to-production-database


### Spring uploading files (or generic to Java?)
(https://spring.io/guides/gs/uploading-files/)

#### 13 Jul 2018 14:33

My intention and question: "How to upload files to resources folder?"
Googling result: Don't

Why?
1. Resources should be considered read-only. (https://stackoverflow.com/questions/36981703/how-to-upload-files-in-resources-folder-in-spring-rest)
2. Redeploying WAR will delete them. (https://stackoverflow.com/questions/21063140/saving-file-to-resource-directory-using-spring)
3. The WAR deploy space didn't intended as permanent file storage location (https://stackoverflow.com/questions/19139426/how-to-write-a-file-to-resource-images-folder-of-the-app)
4. Still about the WAR, some servers do (either by default or by configuration) not expand the deployed WAR file into the local disk file system, but instead fully in the memory. (https://stackoverflow.com/questions/8885201/uploaded-image-only-available-after-refreshing-the-page/8889096#8889096)

Conclusion: MUST use another folder, and NOT "resources/*"

### Spring REST POST/PUT/PATCH/DELETE method not supported, CSRF

#### 14 Sep 2018 19:11

Somehow when I fire the POST-method API, it returns "Request method 'POST' not supported" at the console.

After some googling, it is because Spring Security's CSRF is enabled.
Read here for the CSRF: https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)

There are two ways (so far I know) too solve this:

1. Disable the CSRF security, but our apps will be vulnerable to the attack.
2. Include CSRF token in the request. Set the param name as "_csrf", the value must looks like "814f212c-ec6b-4db8-93ba-eec97cb063b2"
