# Docker

1.  What is Docker
2.  Why we need Docker
3.  Docker Installation Linux
4.  What is Docker File
5.  What is Docker Image
6.  What is Docker Containers
7.  Flow of Docker
8.  Docker Daemon
9.  Docker Client
10. Docker Host
11. Docker Hub/Registry
12. Architecture of Docker
13. Basic Command of Docker
14. conclusion
15. Reference link

# What is Docker?
Docker is a tool that makes developer to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all parts it needs, like libraries and other dependencies, and ship it all out as one package. This ensures that the application runs consistently across different computing environments.

![image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSPohD640FmYsp7JfKZ5kv1MgeyCowXRdeImQ&s)

# Why use Docker?

## Portability:

Containers can run on any system that supports Docker, making it easy to move applications across different environments and platforms.

## Simplified Deployment:

Docker allows for easy and consistent application deployment, reducing the complexity of setting up environments.

## Dependency Management:

Docker containers include all necessary dependencies, libraries, and configurations, ensuring the application runs correctly without missing dependencies.

## Improved Collaboration:

Teams can share Docker images and containers, ensuring everyone is working with the same setup and reducing discrepancies between development and production environments.

## Rapid Prototyping:

Docker allows developers to quickly create and test new features or applications without setting up complex environments.

# Docker Installation Linux
Prerequisite for Installation

- Ubuntu 22.04.4 LTS or compatible Linux distribution
- 64-bit of Ubuntu version
- At least 2 GB of RAM for running Docker
- Sufficient disk space for Docker images and containers.

#### Step 1. Check if the system up-to-date using following command :
```bash
 sudo apt-get update
```
#### Step 2. Set up Docker's `apt` repository.
```bash sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

#### Step 3. Add the repository to Apt sources:
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### Step 4. To install the latest version of Docker Engine:
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### Step 5. check the version of Docker :

```bash
docker version
tanu@tanu-HP:~$ docker --version
Docker version 27.0.3, build 7d4bcd8

```
#### Step 6. Verify Installation of docker :
* verify Docker is running correctly by running a test container.
```bash
 docker run hello-world
```
```bash
tanu@tanu-HP:~$  docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

```
#### Step 7. Start the service of docker :
```bash
 systemctl start docker
```
#### step 7. Check the status of docker service :
```bash
systemctl status docker
```
```bash
tanu@tanu-HP:~$ systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset>
     Active: active (running) since Tue 2024-07-23 11:12:07 IST; 1h 31min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 1706 (dockerd)
      Tasks: 18
     Memory: 112.5M
        CPU: 1.322s
     CGroup: /system.slice/docker.service
             └─1706 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/cont>

Jul 23 11:12:06 tanu-HP dockerd[1706]: time="2024-07-23T11:12:06.331575170+05:3>
Jul 23 11:12:06 tanu-HP dockerd[1706]: time="2024-07-23T11:12:06.441314821+05:3>
Jul 23 11:12:07 tanu-HP dockerd[1706]: time="2024-07-23T11:12:07.162073893+05:3>
Jul 23 11:12:07 tanu-HP dockerd[1706]: time="2024-07-23T11:12:07.237654522+05:3>
Jul 23 11:12:07 tanu-HP dockerd[1706]: time="2024-07-23T11:12:07.253224427+05:3>
Jul 23 11:12:07 tanu-HP dockerd[1706]: time="2024-07-23T11:12:07.253771271+05:3>
Jul 23 11:12:07 tanu-HP dockerd[1706]: time="2024-07-23T11:12:07.305614645+05:3>
Jul 23 11:12:07 tanu-HP systemd[1]: Started Docker Application Container Engine.
Jul 23 12:40:13 tanu-HP dockerd[1706]: time="2024-07-23T12:40:13.298105851+05:3>
Jul 23 12:40:40 tanu-HP dockerd[1706]: time="2024-07-23T12:40:40.558510949+05:3>

````

# what is Docker file

- A Dockerfile is a text file containing a series of instructions that define how to build a Docker image. Each instruction in a Dockerfile specifies a step to create the image, such as setting a base image, copying files, installing dependencies, and running commands. When Docker processes this Dockerfile, it creates an image that can be used to run a containerized application consistently across different environments.

# What is Docker Images

- Docker image are the read only binary templates used to create docker container.
- Single file with all dependencies and configuaration required to run a program.

### Way to create an Images
- Take image from docker hub
- Create image from docker file
- Create images from exiting docker container

# what is Docker Container

- A Docker container is a light weightand executable environment that packages and runs applications with all their dependencies, ensuring consistent behavior across different systems.
- In other words, we can say that ,the image is a template and the container is a copy of that template.
- Image become container when they run on docker engine.

![images](https://gatling.io/hs-fs/hubfs/docker-containers.png?width=450&height=374&name=docker-containers.png)

# Flow of Docker
![image](https://suresoft.gitlab-pages.rz.tu-bs.de/workshop-website/_images/about-dockerworking.JPG)
# Docker Daemon

- Docker Daemon runs on the `Host O.S`.

- It is responsible for running containers to manage docker services.

- It can communicate with other `daemons`.

# Docker Client

- Docker users can interact with `Docker Daemon` through a client `(CLI)`.

- Docker client uses commands(CLI) & rest `API` to communicate with docker daemon.

- When a client runs any command on the docker client terminal, the client terminal sends these docker commands to the docker daemon.

- It is possible for docker client to communicate with more than one daemon.

  ### Used commands by client
 - The command **docker build** builds a Docker image from a Dockerfile.
    ```bash
    docker build.
    ```
- The command **docker pull** is used to download an existing Docker image from a remote Docker registry.
    ```bash
   docker pull image_name
    ````
 - The command **docker run** is used to  run Docker containers.
   ```bash
   docker run container_name
   ```
# Docker Host

- Docker host is used to provide an environment to execute and run applications.

- It contains the docker daemon, images, containers, networks and storages.

# Docker Hub/Registry

- Docker registry manages and stores(private) the docker images.

- There are two-types of registries in the docker.

- Public Registry - It is also called as `Docker Hub`.

- Private Registry - It is used to share images within the enterprise.
  
# Architecture of Docker

![image](https://media.geeksforgeeks.org/wp-content/uploads/20221205115118/Architecture-of-Docker.png)

# Bacis Docker Command

1. Check docker version

```bash
$ docker --version
```

```bash
tanu@tanu-HP:~$ docker --version
Docker version 27.0.3, build 7d4bcd8
```
2.Pull images from docker hub
```bash
docker pull image
````
```bash
tanu@tanu-HP:~$ docker pull mysql
Using default tag: latest
latest: Pulling from library/mysql
d9a40b27c30f: Pull complete 
d948328c7651: Pull complete 
c1e267313ede: Pull complete 
7478f013875a: Pull complete 
9221a2250289: Pull complete 
d1f57baa52d5: Pull complete 
35c3d30e8624: Pull complete 
3d4d1dd0cca6: Pull complete 
08bfe3f7d1c5: Pull complete 
537e7daeeea3: Pull complete 
Digest: sha256:72a37ddc9f839cfd84f1f6815fb31ba26f37f4c200b90e49607797480e3be446
Status: Downloaded newer image for mysql:latest
docker.io/library/mysql:latest

```
3.List of Docker Images
```bash
docker images
```
```bash
tanu@tanu-HP:~$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
<none>       <none>    10732a27da3d   6 days ago    1.42GB
php          latest    4f9597754516   2 weeks ago   537MB
nginx        latest    fffffc90d343   4 weeks ago   188MB

```
4.Create Container
```bash
docker run -d --name my_container <image_name>:<tag>

```
```bash
tanu@tanu-HP:~$ docker run -d --name my_nginx_container nginx:latest
docker: Error response from daemon: Conflict. The container name "/my_nginx_container" is already in use by container "c90e667e462a16890f6ff38b8115bb8f5cad28cee63bd553c185e26f97613044". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
```
5.start Container
```bash
docker start container_name
```
```bash
tanu@tanu-HP:~$ docker start my_nginx_container
my_nginx_container

```
6.Shows only running containers.
```bash
docker ps
```
```bash
tanu@tanu-HP:~$ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED       STATUS         PORTS     NAMES
c90e667e462a   nginx:latest   "/docker-entrypoint.…"   3 hours ago   Up 4 seconds   80/tcp    my_nginx_containe
```
7.command shows both running and exited containers.
```bash
docker ps -a
```
```bash
f4d543db6a60   mongo:latest   "docker-entrypoint.s…"   About an hour ago   Exited (0) About an hour ago             my_mongo_container
6e1a47f34fd7   mysql:latest   "docker-entrypoint.s…"   About an hour ago   Exited (1) About an hour ago             my_mysql_container
2974755143e5   nginx:latest   "/docker-entrypoint.…"   2 hours ago         Exited (0) 2 hours ago                   nginx

```
8.Stop container
```bash
docker stop container name
```
```bash
tanu@tanu-HP:~$ docker stop  my_nginx_container
my_nginx_container
tanu@tanu-HP:~$ 
```
9.Image Remove
```bash
docker rmi <image_name>
```
```bash
tanu@tanu-HP:~$ docker rmi python
Untagged: python:latest
Untagged: python@sha256:b6f142bd70d2219c98c143094ad2a0b8cc882294a7fb2664377a7b68edfc5767
Deleted: sha256:d1d39f5c5b149a1e4b3b1b393351d635e3644b463825a7e194b41bf70b9904d6
Deleted: sha256:35c2d84b14e83517152f8bae7b947533427d8cc36028fb1a7c43565bc7e31796
Deleted: sha256:795e5215738ee487a9125a2258bd0e70f50c03346eab02cbe64f4826cb7048cd
Deleted: sha256:c052dc642d8e9772877bd6c12c8a6710d78d03666a1336dedc4c6db671617f64
Deleted: sha256:0646fafcfadb143cb4ef654685049dcd13e086012decdb48aecbda771c590ac2

```
10.Remove container
```bash
docker rm container_name

```
```bash
tanu@tanu-HP:~$ docker rm 97fd9b25021c
97fd9b25021c

```
# conclusion

Docker has revolutionized application development by using containerization to ensure consistency, simplify dependency management, and enhance scalability, making it crucial for modern DevOps and cloud integration.

# Reference link
 https://docs.docker.com
