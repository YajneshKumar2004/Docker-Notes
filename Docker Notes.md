https://hub.docker.com/



$ docker run \[image name]

&nbsp;	Image is like recipe and container is the dish you cook from that recipe.

$ docker run hello-world

&nbsp;	hello-world is the image name. If does not exist locally it will download from docker registry

&nbsp;	



$ docker version  // will show version of client and server engine



How many containers are running on this host?

$ docker ps // Shows only running containers. If a container is stopped or exited, it won’t appear

$ docker ps -a



How many images are available on this host?

$ docker images 



Run a container using the redis image

$ docker run redis

$ docker run -d redis // to run the container in detach mode



&nbsp;	How to stop?

&nbsp;	1. $ docker ps // to get the container id

&nbsp;	2. $ docker stop \[container id]





Stop the container you just created

$ docker ps -a   		// to get the container id

$ docker stop \[container id]



What is the image used to run the nginx-1 container?

$ docker ps   

CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS     NAMES

&nbsp;	       nginx:alpine									nginx-1

&nbsp;	       ubuntu										awesome\_northcut

{Ans: nginx:alpine}





What is the name of the container created using the ubuntu image?

$ docker ps

{Ans: awesome\_northcut}



What is the state of the stopped alpine container?

Ans: Exited



Stop all containers from the Docker Host.

$ **docker stop $(docker ps -q)**	

&nbsp;	docker ps -q ==> gets IDs of ***running*** containers

$ **docker stop container1 container2 container3**





Delete all containers from the Docker Host.

Both Running and Not Running ones. Remember you may have to stop containers before deleting them.

$ **docker stop $(docker ps -q)**

$ **docker rm $(docker ps -a -q)**    or $ docker rm $(docker ps -aq)





Force:	

&nbsp;    $ docker rm -f <container\_name\_or\_id>

&nbsp;    $ docker kill <container\_name\_or\_id>



Delete the ubuntu Image.

$ docker rmi <image\_name\_or\_image\_id>





You are required to pull a docker image which will be used to run a container later. Pull the image nginx:1.14-alpine

Only pull the image, do not create a container.

$ docker pull nginx:1.14-alpine





Run a container using the image name nginx:1.14-alpine (not the image ID) and name it webapp.

$ docker run --name webapp nginx:1.14-alpine

&nbsp;	***docker run***: Runs a container.

&nbsp;	***--name webapp***: Assigns the name webapp to the container.

&nbsp;	***nginx:1.14-alpine***: The image to use to create the container.



&nbsp;	$ docker ps -a // container name will be webapp





Delete all images on the host

$ docker rmi $(docker images -q)

$ docker rmi -f $(docker images -q)





-p → Port mapping

&nbsp;	-p <host\_port>:<container\_port>

&nbsp;	Example: 

&nbsp;		$ docker run -p 8080:80 nginx

&nbsp;		Open port 8080 on your computer

&nbsp;		Forward traffic to port 80 inside the container (where Nginx runs)

&nbsp;		So you can access it in browser: http://localhost:8080





-e → Environment variable

&nbsp;	-e VARIABLE\_NAME=value

&nbsp;	Example: 

&nbsp;		$ docker run -e MYSQL\_ROOT\_PASSWORD=1234 mysql

&nbsp;		Inside the container, an environment variable is created: MYSQL\_ROOT\_PASSWORD=1234





&nbsp;		







