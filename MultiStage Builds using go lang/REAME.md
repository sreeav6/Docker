#This will helps us to reduce the image size as less as possible using distroless concepts and multi stage builds
#In the second file which we have build the image almost has 1.17 GB we will try to reduce this by using multi stage builds

# Using mluti stage builds it helps to in two things
It helps in reducing the image, where we use distroless concepts 
It also helps in providing security when we are going to deploy the application in the container

# To this as well followed Docker community docs
Reference doc: < https://docs.docker.com/build/building/multi-stage/ >


