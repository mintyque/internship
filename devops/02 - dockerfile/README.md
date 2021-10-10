## Prerequsite

* Docker 19.03 or greater

## Legend

A go web application that outputs container_id(hostname) and access count.
There is a dockerfile and application code in current folder.
You need to optimize the Dockerfile by correcting or adding steps.

## Questions

1. What is Docker? Which technology is it based on?
Docker is a platform that uses OS virtualization for creating virtual containers to host applications. It is faster than virtual machines and allows for robust hosting and deployment.

2. Look at the Docker file – what would you change in it?
Use different image such as golang:alpine for lesser image size.

3. How do I pass variables to the Docker file when building and running the container?
Introduce new argument in Dockerfile with 'ARG var_name ENV env_var_name=$var_name' and then during build: 'docker build --build-arg var_name=${VARIABLE_NAME}'

4. Why do we need multistage build ?
Multi-stage builds make for simpler RUN commands and allow for less memory usage by containers.

## Tasks

* Dockerfile - generate .env file inside Dockerfile, provide value of port at build step.
Done

* Multi-stage build – change the Dockerfile to make it multi-stage. Try to get the lowest container size.
Done

* Compare size of docker images with and without multistage build.
Without multistage build: 858 MB
Without multistage build with golang:alpine: 337 MB
With multistage build with golang:alpine: 11.9 MB

* Write down all commands which you have used.
docker build -t alpine_image . --build-arg PORT=8080 	- build original image
docker build -t lesser_image . --build-arg PORT=8080 	- build multistage image
docker images                                        	- view images to compare sizes
