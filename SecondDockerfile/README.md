#This is basically building the Dockerfile using go lang as example

#Source is from Docker Community Docs

#Reference Doc from Docker docs< https://docs.docker.com/language/golang/build-images/ >

#Where it has exaplained in details step by step

1) As a summary we can know that Building Base image where we can get from the Hub in which this image contains libraries, modules, packages to compile
   and run the go application which is written in Dockerfile
2) We are creating a directory where it will instructs the docker to use the directory as a default destination
3) Thirdly we are using COPY to copy from source to destination. In a simple sentence what to copy and where to copy the files.
4) We are using RUN command to install go modules and it will be installed into a directory inside the image
5) We need to copy the source code in to the image to this we be using again COPY command
6) We need to compile our application using RUN command
7) Finally we need to tell the Docker what command is used to execute when the image will spin up the container to this we use CMD command.
