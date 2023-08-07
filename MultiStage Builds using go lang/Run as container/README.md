
# Now let's try to run the container with the image we have build
docker run <image name> 
Example: docker run docker-gs-ping
With the above command we can't return the terminal back, if we type ctrl+c the container will exit in order to avoid that we will run the container in the
detatch mode by publishing the host port as well container port

# Let's try to run in the detatch mode
docker run -d -p 8080:8080 < image name>
Example: docker run -d -p 8080:8080 docker-gs-ping

# Let's try to list the container which are in running/exited state
docker ps < It will only show the containers which are in UP
![image](https://github.com/sreeav6/Docker/assets/139438620/c86b96ed-f54b-4cc7-94a8-bccb31fb3030)
docker ps -al < It will show all Exited and Running containers >
![image](https://github.com/sreeav6/Docker/assets/139438620/60f9ee46-7e40-4b07-a645-3b2fb12dcb19)

# Let's try to name the container 
docker run -d -p 8080:8080 --name learndocker <image name>
Example: docker


 

