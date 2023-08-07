#This will helps us to reduce the image size as less as possible using distroless concepts and multi stage builds
#In the second dockerfile which we have build the image almost has 1.17 GB we will try to reduce this by using multi stage builds.

# Using mluti stage builds it helps to in two things
It helps in reducing the image size, where we use distroless concepts
It also helps in providing security when we are going to deploy the application in the container.

# To this as well followed Docker community docs
Reference doc: < https://docs.docker.com/build/building/multi-stage/ >

# Now let's build the image
Use this command < docker build -t docker-gs-ping:multistage -f Dockerfile.multistage . > 
# Let's observe the out put below 

anilsree@DESKTOP-5KNU6U1:~/learning/docker-gs-ping$ docker build -t docker-gs-ping:multistage -f Dockerfile.multistage .
[+] Building 12.2s (18/18) FINISHED                                                                                                                                  
 => [internal] load build definition from Dockerfile.multistage                                                                                                 0.0s
 => => transferring dockerfile: 643B                                                                                                                            0.0s
 => [internal] load .dockerignore                                                                                                                               0.0s
 => => transferring context: 2B                                                                                                                                 0.0s
 => resolve image config for docker.io/docker/dockerfile:1                                                                                                      2.7s
 => [auth] docker/dockerfile:pull token for registry-1.docker.io                                                                                                0.0s
 => CACHED docker-image://docker.io/docker/dockerfile:1@sha256:ac85f380a63b13dfcefa89046420e1781752bab202122f8f50032edf31be0021                                 0.0s
 => [internal] load metadata for docker.io/library/golang:1.19                                                                                                  1.8s
 => [internal] load metadata for gcr.io/distroless/base-debian11:latest                                                                                         3.0s
 => [auth] library/golang:pull token for registry-1.docker.io                                                                                                   0.0s
 => [build-stage 1/6] FROM docker.io/library/golang:1.19@sha256:d680597c753e7c73814ddd09c69bef5b78922d81d3ca103c82fa69771ea8151c                                0.0s
 => [build-release-stage 1/3] FROM gcr.io/distroless/base-debian11:latest@sha256:73deaaf6a207c1a33850257ba74e0f196bc418636cada9943a03d7abea980d6d               4.0s
 => => resolve gcr.io/distroless/base-debian11:latest@sha256:73deaaf6a207c1a33850257ba74e0f196bc418636cada9943a03d7abea980d6d                                   0.0s
 => => sha256:b02a7525f878e61fc1ef8a7405a2cc17f866e8de222c1c98fd6681aff6e509db 716.49kB / 716.49kB                                                              0.7s
 => => sha256:e03afa0858f2679999f6f9403e47509b63c2905a42a638fb21089f639af4ab28 1.60kB / 1.60kB                                                                  0.0s
 => => sha256:73deaaf6a207c1a33850257ba74e0f196bc418636cada9943a03d7abea980d6d 1.46kB / 1.46kB                                                                  0.0s
 => => sha256:fe5ca62666f04366c8e7f605aa82997d71320183e99962fa76b3209fdfbb8b58 21.20kB / 21.20kB                                                                0.6s
 => => sha256:559bc54043fc1429f1b9c4e16f52670c7861b7c7fd4125129c29c924b293c2b2 2.12kB / 2.12kB                                                                  0.0s
 => => sha256:a7ca0d9ba68fdce7e15bc0952d3e898e970548ca24d57698725836c039086639 103.73kB / 103.73kB                                                              0.5s
 => => extracting sha256:a7ca0d9ba68fdce7e15bc0952d3e898e970548ca24d57698725836c039086639                                                                       0.0s
 => => sha256:fcb6f6d2c9986d9cd6a2ea3cc2936e5fc613e09f1af9042329011e43057f3265 317B / 317B                                                                      1.0s
 => => extracting sha256:fe5ca62666f04366c8e7f605aa82997d71320183e99962fa76b3209fdfbb8b58                                                                       0.0s
 => => extracting sha256:b02a7525f878e61fc1ef8a7405a2cc17f866e8de222c1c98fd6681aff6e509db                                                                       0.6s
 => => sha256:1e3d9b7d145208fa8fa3ee1c9612d0adaac7255f1bbc9ddea7e461e0b317805c 113B / 113B                                                                      1.1s
 => => sha256:e8c73c638ae9ec5ad70c49df7e484040d889cca6b4a9af056579c3d058ea93f0 198B / 198B                                                                      1.0s
 => => sha256:5627a970d25e752d971a501ec7e35d0d6fdcd4a3ce9e958715a686853024794a 130.56kB / 130.56kB                                                              1.6s
 => => sha256:4aa0ea1413d37a58615488592a0b827ea4b2e48fa5a77cf707d0e35f025e613f 385B / 385B                                                                      1.6s
 => => sha256:7c881f9ab25e0d86562a123b5fb56aebf8aa0ddd7d48ef602faf8d1e7cf43d8c 355B / 355B                                                                      1.5s
 => => extracting sha256:fcb6f6d2c9986d9cd6a2ea3cc2936e5fc613e09f1af9042329011e43057f3265                                                                       0.0s
 => => sha256:08553ba93cfea7ad45b59911d8ed0a025489e7c3623920dfda331b9a49f1e8aa 961.77kB / 961.77kB                                                              2.1s
 => => sha256:96266735468f361ae6828901a80fc15a7f75e26640351df9e0f0f9824f36cf92 5.85MB / 5.85MB                                                                  2.6s
 => => extracting sha256:e8c73c638ae9ec5ad70c49df7e484040d889cca6b4a9af056579c3d058ea93f0                                                                       0.0s
 => => extracting sha256:1e3d9b7d145208fa8fa3ee1c9612d0adaac7255f1bbc9ddea7e461e0b317805c                                                                       0.0s
 => => sha256:2758d0c31c8ca76c3379e7b1be20adc4144e9230873bb2c5bdb41f3691fa75bc 2.06MB / 2.06MB                                                                  2.1s
 => => extracting sha256:4aa0ea1413d37a58615488592a0b827ea4b2e48fa5a77cf707d0e35f025e613f                                                                       0.0s
 => => extracting sha256:7c881f9ab25e0d86562a123b5fb56aebf8aa0ddd7d48ef602faf8d1e7cf43d8c                                                                       0.0s
 => => extracting sha256:5627a970d25e752d971a501ec7e35d0d6fdcd4a3ce9e958715a686853024794a                                                                       0.0s
 => => extracting sha256:96266735468f361ae6828901a80fc15a7f75e26640351df9e0f0f9824f36cf92                                                                       0.3s
 => => extracting sha256:2758d0c31c8ca76c3379e7b1be20adc4144e9230873bb2c5bdb41f3691fa75bc                                                                       0.0s
 => => extracting sha256:08553ba93cfea7ad45b59911d8ed0a025489e7c3623920dfda331b9a49f1e8aa                                                                       0.0s
 => [internal] load build context                                                                                                                               0.0s
 => => transferring context: 113B                                                                                                                               0.0s
 => CACHED [build-stage 2/6] WORKDIR /app                                                                                                                       0.0s
 => CACHED [build-stage 3/6] COPY go.mod go.sum ./                                                                                                              0.0s
 => CACHED [build-stage 4/6] RUN go mod download                                                                                                                0.0s
 => CACHED [build-stage 5/6] COPY *.go ./                                                                                                                       0.0s
 => CACHED [build-stage 6/6] RUN CGO_ENABLED=0 GOOS=linux go build -o /docker-gs-ping                                                                           0.0s
 => [build-release-stage 2/3] COPY --from=build-stage /docker-gs-ping /docker-gs-ping                                                                           1.6s
 => exporting to image                                                                                                                                          0.3s
 => => exporting layers                                                                                                                                         0.3s
 => => writing image sha256:6f30a5e934a2576aa777ffcafcc8badbcc7e155a9bd9fdcb86a22b06267ace15                                                                    0.0s
 => => naming to docker.io/library/docker-gs-ping:multistage                                                                                                    0.0s
anilsree@DESKTOP-5KNU6U1:~/learning/docker-gs-ping$ 

# Now let's compare the sizes of second dockerfile and multistage dockerfile
Multistage dockerfile will have less image size as we have used distroless  base image that we have used in the second stage of the build and is designed for lean deployments of static binaries
Use the command to see the changes < docker image ls >
![image](https://github.com/sreeav6/Docker/assets/139438620/e5128f01-4a6b-4fba-aba4-f9c09a1192a0)


