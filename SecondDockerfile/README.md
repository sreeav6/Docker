#This is basically building the Dockerfile using go lang as example

#Source is from Docker Community Docs

# Reference Doc from Docker docs< https://docs.docker.com/language/golang/build-images/ >

#Where it has exaplained in details step by step

1) As a summary we can know that Building Base image where we can get from the Hub in which this image contains libraries, modules, packages to compile
   and run the go application which is written in Dockerfile.
2) We are creating a directory where it will instructs the docker to use the directory as a default destination.
3) Thirdly we are using COPY command to copy from source to destination. In a simple sentence what to copy and where to copy the files.
4) We are using RUN command to install go modules and it will be installed into a directory inside the image.
5) We need to copy the source code in to the image to this we be using again COPY command.
6) We need to compile our application using RUN command.
7) Finally we need to tell the Docker what command is used to execute when the image will spin up the container to this we use CMD command.

# Now we are building the image by using this Dockerfile. 
#Use the following command to build < docker build --tag docker-gs-ping > Here you are providing the tag with no name hence while building the dockerfile it will use as latest the below output will tell you.
![image](https://github.com/sreeav6/Docker/assets/139438620/5a980a48-7f53-41a3-9ead-39b01b08f7f6)

# Now let's use the tag, basically tag helps you to identify which one is newer/older image it is useful to use tags.
Now let try this command to tag the image which we have build< docker image --tag docker-gs-ping:latest docker-gs-ping:v1.0 > 
Let's observe the below output with the command as < docker image ls >
![image](https://github.com/sreeav6/Docker/assets/139438620/0a1c92b3-f1d9-4026-a2d1-d4f6956630fd)

# Now let's try to untag the one which we have taged just before
Let's try to untag now to this use the command as <docker rmi docker-gs-ping:v1.0 >
Let's observe the output in the below, though we have untagged we didn't lose the image which we have build earlier
![image](https://github.com/sreeav6/Docker/assets/139438620/9381f5b9-6093-41f7-9224-742ca68c35eb)

#Now we are moving to Multistage builds which will helps in reducing the image size and as well as in security.




