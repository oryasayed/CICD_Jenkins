1. after the configuratin of Jenkins, Sonar and Nexus
2. go to Jenknis GUI install plugins.
3. Sonarqubescanner, Nexus artifact uploader
4. docker, docker pipeline, docker-build-step, cloudbees Docker build and Publish
5. owasp dependency-Check
6. we need jdk so for jdk we use Eclipse Temurin Installer
##-----------------------------------##
some configurations
1. manage Jenkins> tools>JDK installations
   <img width="881" alt="image" src="https://github.com/user-attachments/assets/7b614f26-5f63-48fd-b19a-f552b56687c6" />
we can add 
version 11 incase 17 doen't work

<img width="568" alt="image" src="https://github.com/user-attachments/assets/d2cc0960-53c4-47ea-818e-b1dec33c81d0" />

2. SonarQubeScanner

   <img width="1231" alt="image" src="https://github.com/user-attachments/assets/03d0e8da-2e9f-41e1-b6d8-ca3258ea7d57" />

3. Maven

   <img width="1116" alt="image" src="https://github.com/user-attachments/assets/af4b7037-5998-442a-9669-773820361780" />

or 6.3.6

4. Dependency-Check installation

   <img width="1165" alt="image" src="https://github.com/user-attachments/assets/84e1e3c3-15c2-41e9-bc61-a7f54f3dc1c6" />

5. Docekr


   <img width="711" alt="image" src="https://github.com/user-attachments/assets/a7c6c498-c07a-4691-9764-a35fc6338b6d" />


# how to connect SonarQube with Jenkins

SonarQube>Administrator>Generate Token>copyToken>
<img width="1271" alt="image" src="https://github.com/user-attachments/assets/e3c5b56e-b5ee-4c96-8a95-b2cc22a0ab52" />

Jenkins>manageJenkins>Credentials>system>GlobalCredentials

<img width="1192" alt="image" src="https://github.com/user-attachments/assets/ee6ebdbb-c079-4c88-a605-55c281374948" />

we will docker cred as well
<img width="894" alt="image" src="https://github.com/user-attachments/assets/65b26ae1-7a78-461a-abbe-8a468fa798d5" />

we have to add SonarQube Server


<img width="979" alt="image" src="https://github.com/user-attachments/assets/dd6b19ec-f98a-4d3b-8e94-2781e1a23fb9" />

add token which was already saved in jenkins

<img width="860" alt="image" src="https://github.com/user-attachments/assets/44236845-215a-4162-94fb-78c58de11b3c" />

for adding Nexus we need config plugins

<img width="1075" alt="image" src="https://github.com/user-attachments/assets/61693480-8836-4df7-825c-15b40a169116" />

now we have this managed files plugin

Dashboard > Manage Jenkins


<img width="425" alt="image" src="https://github.com/user-attachments/assets/e57548a4-c34e-47a5-baf8-76b8591ad4be" />

add a new config

<img width="589" alt="image" src="https://github.com/user-attachments/assets/92a5fd44-ee9a-4782-9ca7-61551e3854bb" />

ID should be global maven


<img width="722" alt="image" src="https://github.com/user-attachments/assets/49129430-af49-4539-8498-5e6604487746" />

next

now we need maven-releases and manven-snapshot

copy server and edit it

<img width="738" alt="image" src="https://github.com/user-attachments/assets/5e898ac8-826d-4813-b819-141a63c16c09" />

copy from here
<img width="671" alt="image" src="https://github.com/user-attachments/assets/29f6404c-4065-4784-8ebb-7ad1a6828cc3" />


if you don't want to edit the scripts you can add your credential above 
<img width="761" alt="image" src="https://github.com/user-attachments/assets/d06559a6-b78c-4b61-b19f-76adedd12629" />

for snapshot

<img width="467" alt="image" src="https://github.com/user-attachments/assets/3b2d27c1-c52b-4ffa-aae1-7daf0e38d40b" />





<img width="746" alt="image" src="https://github.com/user-attachments/assets/1749bb3c-5553-4282-aee1-ae0af5bd46c8" />


we have to edit the pom.xml file too for nexus the last part of pom.xml

<img width="587" alt="image" src="https://github.com/user-attachments/assets/a2612463-6e22-4cc1-8953-f00121f4f215" />


only the url need to be changed, for manven-release and maven-snapshots.

<img width="1163" alt="image" src="https://github.com/user-attachments/assets/dd5cea43-a3de-43ef-b202-f395d57f5116" />

<img width="893" alt="image" src="https://github.com/user-attachments/assets/be2165d7-096b-45c8-bbfc-c5a6be9d7790" />

<img width="594" alt="image" src="https://github.com/user-attachments/assets/d70fc934-f53a-4aa5-a93f-c1e647e4e12d" />


<img width="550" alt="image" src="https://github.com/user-attachments/assets/f6d08633-f242-443e-9f8e-5385048fefd6" />


# we are creating pipeline



<img width="1006" alt="image" src="https://github.com/user-attachments/assets/89d12bba-511b-41ab-bfdd-a647f87ac54d" />























