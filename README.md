# Task-1

# Step-1 Identify a Sample Application

Took a hello world node application, 

# Command To Exec
nano app.js

This opens a txt editor, write the app code

const http = require('http');

const hostname = '0.0.0.0';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'application/json');
  res.end(JSON.stringify({ message: 'Hello, world!' }));
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

to close and save press CTRL + X then CTRL + Y & then press enter.

# Step-2 Identify Dependencies

# Step-3 Create a Dockerfile

# Command To Exec
nano dockerfile

This opens a txt editor, write the app code
FROM node:14-alpine
WORKDIR /app
COPY package*.json .
RUN npm install
COPY app.js .
EXPOSE 3000
CMD [ "npm", "start" ]

to close and save press CTRL + X then CTRL + Y & then press enter.

# Step-4 Build the Docker Image

# Command To Exec
docker build -t myapp .

# Output
[+] Building 31.2s (11/11) FINISHED                                            
 => [internal] load build definition from dockerfile                      0.3s
 => => transferring dockerfile: 156B                                      0.1s
 => [internal] load .dockerignore                                         0.4s
 => => transferring context: 2B                                           0.1s
 => [internal] load metadata for docker.io/library/node:14-alpine        11.9s
 => [auth] library/node:pull token for registry-1.docker.io               0.0s
 => [1/5] FROM docker.io/library/node:14-alpine@sha256:434215b487a329c9e  0.1s
 => => resolve docker.io/library/node:14-alpine@sha256:434215b487a329c9e  0.1s
 => [internal] load build context                                         1.2s
 => => transferring context: 720B                                         1.1s
 => CACHED [2/5] WORKDIR /app                                             0.0s
 => [3/5] COPY package*.json .                                            0.7s
 => [4/5] RUN npm install                                                15.6s
 => [5/5] COPY app.js .                                                   0.7s
 => exporting to image                                                    0.3s 
 => => exporting layers                                                   0.2s 
 => => writing image sha256:4e466b4d01a1c472e11dd441150568d241791d11571e  0.0s 
 => => naming to docker.io/library/myapp
 
 # What The Command Is
 Here, -t option is used to tag the Docker image with a name (in this case, myapp). The . at the end specifies that the Docker build context is the current directory.

Docker will then build the image according to the instructions in the Dockerfile. You can verify that the image is built correctly by running the following command:

docker images 

It will show the images with latest at top.

# Step-5 

# Command To Exec
docker push mrbasit01/myapp:latest

# Output
The push refers to repository [docker.io/mrbasit01/myapp]
8772238ce3d3: Layer already exists 
7109132d7281: Layer already exists 
5f70bf18a086: Layer already exists 
73b4f4f66193: Layer already exists 
a7a37857ed5c: Layer already exists 
e0f3c9fac6a6: Layer already exists 
c9ceed64ad27: Layer already exists 
7cd52847ad77: Layer already exists 
latest: digest: sha256:ff64a285b58feb796a9ce8ea6f539a107c97389c5535ac3330d0f3ffca9f0739 size: 1984


myapp is my dockerimage name & latest is tag.

# Step-6 Create a GitHub Repository

Created

# Step-7 Include a README.md file

Created & Updated

# Step-8 Push To Github

First cloned the repo then updated the README

then add files via git ADD
then commit via git commit -m ""
then push


