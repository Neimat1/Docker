# Docker

### 1. Some commands in docker you will use.

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
  
  
 ***Errors may help you***:
 
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
   
   
  
 
  
