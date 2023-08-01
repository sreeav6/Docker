# First clone the below repo [Given by the docker community]
    git clone https://github.com/docker/welcome-to-docker

# Verify the Dockerfile 
    cd welcome-to-docker && cat Dockerfile

# Now build the image
   docker build -t welcome-to-docker .
   ---------------------------------------------------
   The output will show like below
   docker build -t first-docker-image .
[+] Building 87.4s (12/12) FINISHED
 => [internal] load .dockerignore                                                                                                                                                  0.1s
 => => transferring context: 52B                                                                                                                                                   0.0s
 => [internal] load build definition from Dockerfile                                                                                                                               0.1s
 => => transferring dockerfile: 653B                                                                                                                                               0.0s
 => [internal] load metadata for docker.io/library/node:18-alpine                                                                                                                  4.1s
 => [auth] library/node:pull token for registry-1.docker.io                                                                                                                        0.0s
 => [1/6] FROM docker.io/library/node:18-alpine@sha256:93d91deea65c9a0475507e8bc8b1917d6278522322f00c00b3ab09cab6830060                                                            7.1s
 => => resolve docker.io/library/node:18-alpine@sha256:93d91deea65c9a0475507e8bc8b1917d6278522322f00c00b3ab09cab6830060                                                            0.0s
 => => sha256:93d91deea65c9a0475507e8bc8b1917d6278522322f00c00b3ab09cab6830060 1.43kB / 1.43kB                                                                                     0.0s
 => => sha256:ef5e088232f803cadb83326edb4731015f42961d23a11510b109c2c98cfbb945 1.16kB / 1.16kB                                                                                     0.0s
 => => sha256:9112cb38e57e8bfbc18330dfe346483e20db1fc77c84e4238f63dd6fef798f66 6.73kB / 6.73kB                                                                                     0.0s
 => => sha256:31e352740f534f9ad170f75378a84fe453d6156e40700b882d737a8f4a6988a3 3.40MB / 3.40MB                                                                                     0.7s
 => => sha256:2629b68d431155efb7618354d25920459fa7e2e0e74cee98f77d9dd4f40dbdc2 47.76MB / 47.76MB                                                                                   2.3s
 => => sha256:ddb7cc70f260e201d3baddd8db072ecf6847e889e8750bea0c0e2c3aab41d020 2.34MB / 2.34MB                                                                                     1.3s
 => => extracting sha256:31e352740f534f9ad170f75378a84fe453d6156e40700b882d737a8f4a6988a3                                                                                          0.1s
 => => sha256:18afe63734743ad86235f2917c4a8e874db1fcdae23de45b4bdbf1264ed0540d 449B / 449B                                                                                         1.3s
 => => extracting sha256:2629b68d431155efb7618354d25920459fa7e2e0e74cee98f77d9dd4f40dbdc2                                                                                          4.4s
 => => extracting sha256:ddb7cc70f260e201d3baddd8db072ecf6847e889e8750bea0c0e2c3aab41d020                                                                                          0.1s
 => => extracting sha256:18afe63734743ad86235f2917c4a8e874db1fcdae23de45b4bdbf1264ed0540d                                                                                          0.0s
 => [internal] load build context                                                                                                                                                  0.0s
 => => transferring context: 690.94kB                                                                                                                                              0.0s
 => [2/6] WORKDIR /app                                                                                                                                                             1.7s
 => [3/6] COPY package*.json ./                                                                                                                                                    0.0s
 => [4/6] COPY ./src ./src                                                                                                                                                         0.0s
 => [5/6] COPY ./public ./public                                                                                                                                                   0.0s
 => [6/6] RUN npm install     && npm install -g serve     && npm run build     && rm -fr node_modules                                                                             72.2s
 => exporting to image                                                                                                                                                             2.1s
 => => exporting layers                                                                                                                                                            2.0s
 => => writing image sha256:c231ca4825c9341ccd9b7b62b9a35413ce17a3d6df37b14e211ee0cdd5f41b54                                                                                       0.0s
 => => naming to docker.io/library/first-docker-image:latest                                                                                                                       0.0s
# Run the container
   docker run -it -d -p 8089:3000 --name fc first-docker-image

# You can stop the container
    docker stop <type container Id here>

# 
