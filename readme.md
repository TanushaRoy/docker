# Docker

1.  What is Docker
2.  Why we need Docker
3.  Docker Installation Linux
4.  Flow of Docker
5.  What is Docker File
6.  What is Dcoker Image
7.  What is Docker Containers
8.  Docker Daemon
9.  Docker Client
10. Docker Host
11. Docker Hub/Registry
12. Architecture of Docker
13. Basic Command of Docker
14. conclusion

# What is Docker?

Docker is a containerization platform that helps package, deploy, and run applications within containers. Containers are different from virtual machines because they are lightweight and include only the necessary features required by the application. Docker enables developers to efficiently run applications in a consistent manner across different computing environments.
![image](https://github.com/user-attachments/assets/d8c7162f-b7aa-4171-a26b-ac94f80e3289)


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
$ sudo apt-get update
```
#### Step 2. Set up Docker's `apt` repository.
```bash
$ sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

#### Step 3. Add the repository to Apt sources:
```bash
$  echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### Step 4. To install the latest version of Docker Engine:
```bash
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### Step 5. check the version of Docker :

```bash
$ docker version
tanu@tanu-HP:~$ docker --version
Docker version 27.0.3, build 7d4bcd8

```
# Flow of Docker
![images](https://suresoft.gitlab-pages.rz.tu-bs.de/workshop-website/_images/about-dockerworking.JPG)

# what is Docker file

- A Dockerfile is a text file containing a series of instructions that define how to build a Docker image. Each instruction in a Dockerfile specifies a step to create the image, such as setting a base image, copying files, installing dependencies, and running commands. When Docker processes this Dockerfile, it creates an image that can be used to run a containerized application consistently across different environments.

# What is Docker Image

- A Docker image is a complete and executable software package that includes all dependencies and configurations needed to run an application

# what is Docker Container

A Docker container is a lightweightand executable environment that packages and runs applications with all their dependencies, ensuring consistent behavior across different systems.
(![image](https://github.com/user-attachments/assets/1823789a-297f-4df1-9f5b-a2c729e2c18b)


# Docker Daemon

- Docker Daemon runs on the `Host O.S`.

- It is responsible for running containers to manage docker services.

- It can communicate with other `daemons`.

# Docker Client

- Docker users can interact with `Docker Daemon` through a client `(CLI)`.

- Docker client uses commands(CLI) & rest `API` to communicate with docker daemon.

- When a client runs any command on the docker client terminal, the client terminal sends these docker commands to the docker daemon.

- It is possible for docker client to communicate with more than one daemon.

# Docker Host

- Docker host is used to provide an environment to execute and run applications.

- It contains the docker daemon, images, containers, networks and storages.

# Docker Hub/Registry

- Docker registry manages and stores(private) the docker images.

- There are two-types of registries in the docker.

- Public Registry - It is also called as `Docker Hub`.

- Private Registry - It is used to share images within the enterprise.

# Bacis Docker Command

1. Check docker version

```bash
$ docker --version
```

```bash
tanu@tanu-HP:~$ docker --version
Docker version 27.0.3, build 7d4bcd8
```

2.docker build command is used to create a Docker image from a Dockerfile and a context.

```bash
$ docker build
```

3.The docker pull command is used by a client to download an image from a Docker registry (such as Docker Hub) to their local system.

```bash
$ docker pull
```

4.docker run command is used to start a new container from a Docker image.

```bash
$ docker run
```

5. Create Docker Image

```bash
docker iamge -t (image name)
```

6.Check Docker Image Details

```bash
Docker image ls
```

7. Start Container

```bash
$ sudo docker run -itd --name (container name) (Image name)
```

8 . Stop the Container

```bash
$ sudo docker stop (container name)
```

9.Remove the Container

```bash
$ sudo docker stop (container name)
```

```bash
$ sudo docker rm (container name)
```

10.Remove Container

```bash
$ sudo docker rm (container name)
```

11.Check the container on the machine

```bash
$ sudo docker ps
```

12.Pull image from docker hub

```bash
$ sudo docker pull (image name)
```

13.Push image from docker hub

```bash
sudo docker push (image name)
```
![image](https://media.geeksforgeeks.org/wp-content/uploads/20221205115118/Architecture-of-Docker.png)

### conclusion

Docker has revolutionized application development by using containerization to ensure consistency, simplify dependency management, and enhance scalability, making it crucial for modern DevOps and cloud integration.
