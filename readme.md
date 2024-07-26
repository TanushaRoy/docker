# Docker

1.  What is Docker
2.  Why we need Docker
3.  Docker Installation on Linux
4.  What is a Dockerfile
5.  What are Docker Images
6.  What is a Docker Container
7.  Flow of Docker
8.  Docker Daemon
9.  Docker Client
10. Docker Host
11. Docker Hub/Registry
12. Architecture of Docker
13. Basic Docker Commands
14. Conclusion
15. Reference Links

# What is Docker?
Docker is a tool that makes developer's task easier to create, deploy, and run applications by using containers. Containers allows a developer to package an application's code with all the dependencies it needs, like libraries and other dependencies, and ship it all out as one package. This ensures that the application runs consistently across different computing environments.

![image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSPohD640FmYsp7JfKZ5kv1MgeyCowXRdeImQ&s)

# Why we need Docker?

## Simplified Deployment:

Docker allows for an easy and consistent application deployment, reducing the complexity of setting up an environment.

## Dependency Management:

Docker containers include all necessary dependencies, libraries, ensuring the application runs correctly without any missing dependencies.

## Improved Collaboration:

Teams can share Docker images, ensuring everyone is working with the same setup and reducing discrepancies between development and production environments.

## Rapid Prototyping:

Docker allows developers to quickly create and test new features or applications without setting up complex environments.

# Docker Installation on Linux
Prerequisite for Installation,

- Ubuntu 22.04.4 LTS Desktop (64-bit) or compatible Linux distribution.
- At least 2 GB of RAM.
- At least 2 CPU.
- At least 2 GB space for Docker images and containers.

#### Step 1. Check if the system is up-to-date using following command :
```bash
 sudo apt-get update
```
**Note** - You might face an dependency error for "curl" command. 
If required, you can use the use the ` sudo apt-get install curl ` command, to install curl.

#### Step 2. Set up Docker's `apt` repository.
```bash sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

#### Step 3. Add the repository to `apt` sources:
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
#### Step 4. Update the `apt` repository using following command :
```bash
 sudo apt-get update
```
#### Step 5. To install the latest version of Docker and Docker Tools :
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### Step 6. Check the version of Docker :

```bash
sudo docker --version
```
```bash
tanu@tanu-HP:~$ sudo docker --version
Docker version 27.0.3, build 7d4bcd8
```
#### Step 7. Verify the installation of Docker :
* Verify the Docker is running correctly by running a "hello-world" container.
  
```bash
 sudo docker run hello-world
```
```bash
tanu@tanu-HP:~$  sudo docker run hello-world

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

#### Step 8. Check the status of Docker service :
```bash
sudo systemctl status docker
```
```bash
tanu@tanu-HP:~$ sudo systemctl status docker
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

# What is a Dockerfile?

- A Dockerfile is a text file containing a series of instructions that define how to build a docker image. Each instruction in a Dockerfile specifies a step to create the image, such as setting a base image, copying files, installing dependencies, and running commands. When docker builds an image from this Dockerfile, the same image can be used to run a containerir across different operating systems.

# What are Docker Images?

- Docker images are the read-only binary templates used to create docker containers.
- Single file with all dependencies and configurations required to run a program.

### Way to get and create Images
- Get an image from Docker Hub.
- Create an image from Dockerfile.
- Create images from exiting docker container.

# What is a Docker Container?

- A docker container is a light weight and executable environment that packages and runs applications with all their dependencies, ensuring consistent behavior across different systems.
- In other words, we can say that, the image is a template and the container is an instance of that template.
- Containers are created and managed by docker engine.

![images](https://gatling.io/hs-fs/hubfs/docker-containers.png?width=450&height=374&name=docker-containers.png)

# Flow of Docker
![image](https://suresoft.gitlab-pages.rz.tu-bs.de/workshop-website/_images/about-dockerworking.JPG)
# Docker Daemon

- Docker Daemon runs on the `Host O.S.`

- It is responsible for running containers to manage docker services.

- It can communicate with other `daemons`.

# Docker Client

- Docker users can interact with `Docker Daemon` through a `Command Line Interface (CLI)`.

- Docker client uses commands & rest `API` to communicate with docker daemon.

- When a client runs any command on the docker client terminal, the client terminal sends these docker commands to the docker daemon.

- It is possible for docker client to communicate with more than one daemon.

  ### Used commands by client
 - The command **docker build** builds a Docker image from a Dockerfile. 
  
   Note - `"."` represents the path to the `Dockerfile`.
    ```bash
    docker build .
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

- Docker registry manages and stores the docker images.

- There are two-types of registries in the docker.

- Public Registry - It is also called as `Docker Hub`.

- Private Registry - It is used to share images within the enterprise.
  
# Architecture of Docker

![image](https://media.geeksforgeeks.org/wp-content/uploads/20221205115118/Architecture-of-Docker.png)

# Bacis Docker Commands

1. Check Docker Version.

```bash
sudo docker --version
```

```bash
tanu@tanu-HP:~$ sudo docker --version
Docker version 27.0.3, build 7d4bcd8
```
2. Pull images from Docker Hub.
```bash
sudo docker pull image_name
````
```bash
tanu@tanu-HP:~$ sudo docker pull mysql
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
3. List Docker Images.
```bash
sudo docker images
```
```bash
tanu@tanu-HP:~$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
<none>       <none>    10732a27da3d   6 days ago    1.42GB
php          latest    4f9597754516   2 weeks ago   537MB
nginx        latest    fffffc90d343   4 weeks ago   188MB

```
4. Create a Container.
```bash
sudo docker run -d --name my_container <image_name>:<tag>

```
```bash
tanu@tanu-HP:~$ sudo docker run -d --name my_nginx_container nginx:latest
docker: Error response from daemon: Conflict. The container name "/my_nginx_container" is already in use by container "c90e667e462a16890f6ff38b8115bb8f5cad28cee63bd553c185e26f97613044". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
```
5. Start an Existing Container.
```bash
sudo docker start container_name
```
```bash
tanu@tanu-HP:~$ sudo docker start my_nginx_container
my_nginx_container

```
6. Shows only Running Containers.
```bash
sudo docker ps
```
```bash
tanu@tanu-HP:~$ sudo docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED       STATUS         PORTS     NAMES
c90e667e462a   nginx:latest   "/docker-entrypoint.…"   3 hours ago   Up 4 seconds   80/tcp    my_nginx_containe
```
7. Command shows both Running and Exited Containers.
```bash
sudo docker ps -a
```
```bash
f4d543db6a60   mongo:latest   "docker-entrypoint.s…"   About an hour ago   Exited (0) About an hour ago             my_mongo_container
6e1a47f34fd7   mysql:latest   "docker-entrypoint.s…"   About an hour ago   Exited (1) About an hour ago             my_mysql_container
2974755143e5   nginx:latest   "/docker-entrypoint.…"   2 hours ago         Exited (0) 2 hours ago                   nginx

```
8. Stop a Container.
```bash
sudo docker stop container_name
```
```bash
tanu@tanu-HP:~$ sudo docker stop  my_nginx_container
my_nginx_container
tanu@tanu-HP:~$ 
```
9. Remove an Image.
```bash
sudo docker rmi <image_name>
```
```bash
tanu@tanu-HP:~$ sudo docker rmi python
Untagged: python:latest
Untagged: python@sha256:b6f142bd70d2219c98c143094ad2a0b8cc882294a7fb2664377a7b68edfc5767
Deleted: sha256:d1d39f5c5b149a1e4b3b1b393351d635e3644b463825a7e194b41bf70b9904d6
Deleted: sha256:35c2d84b14e83517152f8bae7b947533427d8cc36028fb1a7c43565bc7e31796
Deleted: sha256:795e5215738ee487a9125a2258bd0e70f50c03346eab02cbe64f4826cb7048cd
Deleted: sha256:c052dc642d8e9772877bd6c12c8a6710d78d03666a1336dedc4c6db671617f64
Deleted: sha256:0646fafcfadb143cb4ef654685049dcd13e086012decdb48aecbda771c590ac2

```
10. Remove a Container.
```bash
sudo docker rm container_name

```
```bash
tanu@tanu-HP:~$ sudo docker rm 97fd9b25021c
97fd9b25021c

```
# Conclusion

Docker has revolutionized application development by using containerization to ensure consistency, simplify dependency management, and enhance scalability, making it crucial for modern DevOps and cloud integration.

# Reference Link
 https://docs.docker.com
