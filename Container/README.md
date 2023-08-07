Basically a container is a collection of system dependencies, libraries and collection of packages.
They are basically light in weight which will help building the applications in a smoother way

# Now let try to get first container up and running using the below ones
  Prerequisites: Install Docker Desktop

# First let's clone from the officail docker docs
    git clone https://github.com/docker/welcome-to-docker

# Once you clone the above repo then type below command in order to explore the Dockerfile
    cd welcome-to-docker

# After exploring the Dockerfile. Now you need to build first image. To do this type the below command
    docker build -t welcome-to-docker .

#Now you can able to view the images in the Docker Desktop simply by clicking the images option.

# If you want to run the container with the image you have build, see the below command to run the container
    docker run -it -d -p 8089:3000 --name fc first-docker-image
    
    docker run: Docker deamon will understand the input received from Docker client and tries to pull from the Docker Hub and run and execute the container
    -it interactive terminal; 
    -p port mapping host port to container port; 
    --name you are naming the container else it will pickup automatically a random name if you don't specify finally you need to provide the image name which will       help us in building the container.

# Else if you don't want to run command as specified above please follow the below doc given by docker community
  https://docs.docker.com/get-started/run-your-own-container/

  
  
    
  
