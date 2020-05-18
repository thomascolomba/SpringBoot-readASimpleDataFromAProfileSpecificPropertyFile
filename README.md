How to read a profile specific properties file with Spring Boot.<br/>
<br/>
How to compile and execute :<br/>
mvn package<br/>
java -jar ./target/readASimpleDataFromAProfileSpecificPropertyFile-0.0.1-SNAPSHOT.jar --spring.profiles.active=dev<br/>
(or we can remove the '--spring.profiles.active=dev' parameter to deactivate the 'dev' profile)<br/>
<br/>
---application.properties<br/>
myString=qwerty<br/>
---application-dev.properties<br/>
myString=qwertyFromDevSpecificPropertyFile<br/>
---MyConfigurationBean.java<br/>
private String myString;<br/>
+getter and setter<br/>
---The class who displays the value of the 'myString' configuration<br/>
@Autowired<br/>
MyConfigurationBean myConf;<br/>
...<br/>
System.out.println(myConf.getMyString());<br/>
<br/>
<br/>
The application will read the value 'qwertyFromDevSpecificPropertyFile' of the property myString in the profile specific application-dev.properties configuration file then display it in the terminal. (if the '--spring.profiles.active=dev' parameter is used<br/>


