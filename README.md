# Docker

**Main problem:**
 When we have multiple projects in our environment and each project use different versions of **PHP** and also **MySQL** in that case what will happen?
 
 That's cause error in projects abd to control this problem we need to make each project isolated so to do this solution we need to choose one option from those:
 1. Configuration: This means we will change configuration for each projcet and that is a bad idea
    + Not Scalable 
    + Risk to breaking everything
    + it's too hard
 2. Virtual Machine: To use multiple virtual machine for each project this's not a good solution becaues 
    + VMs are resource hungry
    + Cannot be reused 
    + Cannot be shared among the team members     
 3. Vagrant: Not ideal Solution because it's a VM 
 4. Docker: It's a 
    + Light weight
    + Extendable
    + Configuration injection: Change the confuguration and updated it
    + Sharable: Once it's uploaded to the repository any one can use the image  
 
One of the pros of docker that it's the prerequisite of microservice and that's by isolating each service to achieve the concept of microservice.

### Some commands in docker:

- List all containers are running now
  ```
  docker ps
  ```
- List all containers are running and closed
  ```
  docker ps -a
  ```
- Show last container was running 
  ```
  docker ps -l
  ```
  
- To remove container  
  ```
  docker rm <name Of image> 
  ```
    OR
  ```
  docker rm <ID of image> 
  ```
  
- To remove image  
  ```
  docker rmi <image> 
  ```
- To stop running container  
  ```
  docker stop <container Name>
  ```
- List number of processes that are working in specific container  
  ```
  docker exec <Container Name> ps -eaf
  ```
 
___

### Docker Structure:
```
# list docker folders
sudo ls -l /var/lib/docker
```
![image](https://user-images.githubusercontent.com/63751555/222992644-08a083a8-ca7c-4b6d-bf80-8204e0ba7425.png)

____
### Kubernets:
we use because docker run only one instance of image 
and in case we want to run multiple instances or to roll back we can use kubernets

  + Kubernets architecture:
      + cluster consits of multiple nodes each node is about worker machine
      + master is a node that responsible for orchestration in cluster 
    

___
 
 ### Errors may help you 
 
 + if you get this error 
 ![Screenshot 2023-02-27 140215](https://user-images.githubusercontent.com/63751555/221559100-e44cdc44-bfa2-42da-9832-077140ac3ef7.png)
  
   + solution: use this 3 commands
     ```
     service docker stop 
     rm ~/.docker/config.json 
     service docker start
     ```
   + ref : https://stackoverflow.com/questions/71770693/error-saving-credentials-error-storing-credentials-err-exit-status-1-out
   
   
   
 + if you ran the tomcat image then 404 error page appeared to you instead of tomcat webpage 
  ![image](https://user-images.githubusercontent.com/63751555/222397615-1f15c829-ed61-4017-a530-cc4f04f12812.png)
    + solution:
      ```
      docker pull tomcat:latest
      docker run -d --name mytomcat -p 8080:8080 tomcat:latest
      docker exec -it mytomcat /bin/bash
      mv webapps webapps2
      mv webapps.dist/ webapps
      exit
      ```
 

    + ref : https://www.topzenith.com/2020/07/http-status-404-not-found-docker-tomcat-image.html 
   
   ---
   ### Good References
   + https://github.com/mmumshad/simple-webapp-flask
   + https://github.com/mmumshad/example-voting-app
   + https://stackoverflow.com/questions/30853247/how-do-i-edit-a-file-after-i-shell-to-a-docker-container
   
   
  
 
  
