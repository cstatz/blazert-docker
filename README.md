# blazert-docker
## Step 1 - Install Docker for your System
Go to official [Docker website](https://docs.docker.com/get-docker/), select your OS and follow the instructions for installation.
## Step 2 - Pull Image
If everything is set up, you could pull the Docker image.
```
$ docker pull tobiaskhfs/blazert:1
```
## Step 3 - Run Image
If you use the image for the first time, a container must be created first.
```
C:\Users\tobias> docker image ls
REPOSITORY           TAG                 IMAGE ID            CREATED             SIZE
tobiaskhfs/blazert   1                   70419blaze21        1 hours ago         1.92GB
```
The command ``docker image ls`` shows every docker repository on the host os. Next you select the repository
to start from, using the IMAGE ID. You must also specify a port for the localhost.
```
C:\Users\tobias> docker run -p 2222:22 --name BlazeRT_Container tobiaskhfs/blazert:1
```
- ``docker run`` specifies that you want to run an image 
- ``-p 2222:22`` connects the tcp 22 port of the container with the localhost port 2222
- ``--name BlazeRT_Container`` name of the container (optional)
- ``tobiaskhfs/blazert:1`` chooses the repository and tag
    - alternatively the IMAGE ID can be used: ``70419blaze21``
## Step 4 - Add Remote Host to Clion
## How to write Dockerfile ? 
## List of useful Docker commands

| Command       | Description   | 
| ------------- |:-------------:| 
| `docker images`     | List images  | 
| `docker ps -a`      | List containers      | 


`docker run -p 2222:22 <IMAGE-ID>`: Startet Container mit unter localhost mit port 2222 

docker images - zeigt alle vorhandenen images an
docker login - login in docker -> danach eingabe von DockerID und Passwort
docker pull <image-name> - Downloadet jeweiliges docker image
docker run -it -d <REPOSITORY> - Startet das jeweilige image/container
docker ps -a -> lists containers
docker exec -it <CONTAINER-ID> bash -> startet powershell des jeweilgen containers
docker commit <CONTAINER-ID> <new-name:Tag> -> erzeugt neues image vom jeweiligen container unter einem neuen namen, praktisch wenn änderungen im container durchgeführt wurden (erzeugung con cmake-debug etc.), tag nicht unbedingt nötig
docker push <REPOSITORY:TAG> -> pusht das jeweilige image nach dockerhub