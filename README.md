# spring-cloud
this project implements my problem of common property file issue faced at airtel.

spring-config-cloud-server is the config server which connects to the git/bitbucket repository.

Imp Points to know and how to setup the project :

Config server:
1. go to start.spring.io and setup a maven project and specify config server dependency and spring boot starter.
2. import the project in IDE and build it 
3. add @EnableConfigServer annotation on the default created Spring bootstrap class containing the main method. This annotation tells spring to look for the configuration provided in the property files
4. setup a local repo or use a git hub repo 
5. copy the property file and change in the project accordingly.
6. Build and run to check the application 

Config Client :
Config client will be any spring boot project but need to add spring-cloud-starter-config and actuator dependency in the pom.xml and enable
some properties for it 

Sample Pom.xml is attached 
<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-config</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
    
property needed to add :
spring.config.import=optional:configserver:http://localhost:8888
spring.cloud.config.enabled=true
spring.application.name = rateplanservice-application 

Note :
----the name of application should match for properety file mentioned in git repo along with the profile needed dev,sit etc.
If refresh option is required then actuator needs to be enabled.




