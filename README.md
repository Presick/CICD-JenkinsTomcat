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

##### description
+ Once the developer commit the code and once this one is merged to the main branch, a build is triggered on Jenkins via webhook
+ The artefact is successively built( Maven), analyzed for quality 9 SonarQube) then deployed to production ( Apache- Tomcat) while a copy of the .war file is stored in Nexus.
+ Notifications are sent to the DevOps team via Email/SMS/Slack
  

