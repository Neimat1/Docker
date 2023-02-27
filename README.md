# Docker
Some commands in docker you will use.

- To know the images those are running now
  ```
  docker ps
  ```
- Show all containers are running and closed
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
  
 #### Note:
 
 if you get this error 
 ![Screenshot 2023-02-27 140215](https://user-images.githubusercontent.com/63751555/221559100-e44cdc44-bfa2-42da-9832-077140ac3ef7.png)
  
   solution: use this 3 commands
   ```
   service docker stop 
   rm ~/.docker/config.json 
   service docker start
   ```
   ref : https://stackoverflow.com/questions/71770693/error-saving-credentials-error-storing-credentials-err-exit-status-1-out
  
 
  
