# Simple Node.js application in docker

> Made by Serhii Hatsan, IK-01

--------------------------------------

This is sample application, which was taken from [Node.js documentation](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/).

## What you will need to build and run it locally:
 - [Docker](https://www.docker.com/)
 - [Node.js](https://nodejs.org) (if you want to modify code later)

## How to build docker image
1. Download source to your computer: ```git clone https://github.com/RubyLegend/DevOps_docker.git```
2. Move into downloaded repo: ```cd DevOps_docker/```
3. Build image: ```docker build . -t <image_name>```

You can also get prebuilt image from Docker Hub: ```docker pull rubylegend/node-web-app:latest```

## To push your built image to docker hub:
1. Login into Docker Hub account: ```docker login```
2. Push your image to docker hub: ```docker push <image_name>:latest```

--------------------------------------

## How to run it locally
Run ```docker run -d -p 80:80 -m 1g --cpus="1" --name node-app --rm rubylegend/node-web-app```

### Some details about command above:
 - ```-d``` : Run container in background.
 - ```-p 80:80``` : Binds external port 80 to internal (inside container) port 80. You can change external port to your own, but if you want to change internal port, then also change it in ```server.js``` file.
 - ```-m 1g``` : Limits memory, which will be available to container. Available suffixes: ```b```, ```k```, ```m```, ```g```, which corresponds to bytes, kilobytes, megabytes or gigabytes.
 - ```--cpus="1"``` : Specify how much of the available CPU resources a container can use.
 - ```--name node-app``` : Custom name for your docker container.
 - ```--rm``` : Remove container after stop.
 - ```rubylegend/node-web-app``` : Container name.

After that you can list all your running containers by running: ```docker ps```.

To stop container, run: ```docker stop node-app```

--------------------------------------

Happy coding with Node.js!
