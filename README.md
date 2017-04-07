# hyp
Repository for the HYP course at Politecnico di Milano (Summer 2017)

## Build Docker image 
Go to the directory that has your Dockerfile and run the following command to build the Docker image. The -t flag lets you tag your image so it's easier to find later using the docker images command:

`$ docker build -t <your username>/hyp ./src`

Your image will now be listed by Docker:

`$ docker images`

## Run the Docker image
Running your image with -d runs the container in detached mode, leaving the container running in the background. The -p flag redirects a public port to a private port inside the container. Run the image you previously built:

`$ docker run -p 49160:8080 -d <your username>/hyp`

Print the output of your app:

Get container ID

`$ docker ps`

Print app output

`$ docker logs <container id>`

If you need to go inside the container you can use the exec command:

`$ docker exec -it <container id> /bin/bash`

## Test app

To test your app, get the port of your app that Docker mapped:

`$ docker ps`

Now you can call your app using curl (install if needed via: sudo apt-get install curl):

`$ docker curl -i localhost:49160`
