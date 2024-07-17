## PROJECT

##### Context
We have been tasked by a company called Landmark Technology to build a CI CD ( Continuous Integration Continuous Deployment) pipeline fro their holiday sales as their offers change quickly based on the demand. They want to be able to publish new offer quickly. 

##### Tools
+ AWS
+ Jenkins CE
+ SCM (git/github)
+ Maven plugin
+ SonarQube
+ Nexus
+ Apache Tomcat
##### Infrastructure
+ Cloud provider account: in our case AWS
+ 4 EC2 server t2.medium OS RHEL 7/8
+ Create security group and open port 22, 8080, 8081, 9000 which are the port we will be using for this project
+ Bind servers to that security group

 ![image](https://github.com/user-attachments/assets/085d267b-0d4a-4ec0-8caf-02ec4baab498)
 

  ![image](https://github.com/user-attachments/assets/6c109e1b-7ecd-4ce3-b280-b9dca43e8034)

  ![image](https://github.com/user-attachments/assets/6d424081-e4a5-4e8e-9f2e-7a563a494e84)

##### WORFLOW

![image](https://github.com/user-attachments/assets/905f6c4d-c29b-4b2e-9449-9f2dd81ba2f1)

##### description
+ Once the developer commit the code and once this one is merged to the main branch, a build is triggered on Jenkins via webhook
+ The artefact is successively built( Maven), analyzed for quality 9 SonarQube) then deployed to production ( Apache- Tomcat) while a copy of the .war file is stored in Nexus.
+ Notifications are sent to the DevOps team via Email/SMS/Slack

##### step 1 create the project on Jenkins dashboard
On Jenkins dashboard: + NewItem - Name the project ( Landmark-project) - Select Freestyle Project - click OK
![image](https://github.com/user-attachments/assets/56c3cb2a-79f0-4539-91a9-2e3f7711083f)


##### step 2 Jenkins - Git integration + Webhook configuration
From the project dashboard in Jenkins go to Configuration - Source Code Management

![image](https://github.com/user-attachments/assets/632a0f2a-f797-4a20-86f7-83ff0bec7073)

Go to the project repository on Github - Settings - Webhook
![image](https://github.com/user-attachments/assets/f456ab99-e03e-49cf-a324-99ddbb7b54a8)

##### step 3 Jenkins - maven, SonarQube and Nexus configuration

From the project configuration page
![image](https://github.com/user-attachments/assets/7ab9e2ae-fcc3-4dc1-b3a6-9fa0a10c04cb)


##### step 4 Jenkins - Tomcat Integration

install Deploy to container Plugin
![image](https://github.com/user-attachments/assets/e0f27653-2754-4279-ba6e-8f7416a9cefe)

Configure the project to deploy on Tomcat
![image](https://github.com/user-attachments/assets/34adbedd-e78d-47e6-8476-ea4b7f2d435d)

##### step 5 Jenkins notification configuration
from Jenkins dashboard go to: Manage Jenkins - System - E-mail Notification. ( Prior to that make sure to install the Email Extension Plugin)
![image](https://github.com/user-attachments/assets/b6d8af6d-3d1f-4c44-ad5f-9545698e0079)


![image](https://github.com/user-attachments/assets/e80fcadb-6eb1-4972-97ad-71aa6c818e9e)

##### Deployment
![image](https://github.com/user-attachments/assets/16eb274c-edf8-44c4-a345-fd18a567cd2e)
![image](https://github.com/user-attachments/assets/4bccf556-2700-4139-a113-aee479121ce6)
![image](https://github.com/user-attachments/assets/f04f528c-433f-4720-ba87-5c35b8371520)


## REFERENCE LINK
Project Github repository

https://github.com/Presick/maven-web-application
