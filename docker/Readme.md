# Comprehensive Docker Cheat Sheet for Developers

<img src="source/docker-cheat-sheet.png"></img>

## **Introduction**
Docker has revolutionized software development by offering an efficient and standardized method to deploy applications across various environments. As a versatile tool, it simplifies the process of containerization, allowing developers to focus on innovation rather than infrastructure. This cheat sheet is designed to assist both beginners and experienced professionals in navigating Docker's extensive capabilities. It highlights essential commands and their applications, providing a quick reference to enhance productivity in software development.

## **What is Docker?**
Docker is an open-source platform that automates the deployment of applications inside lightweight and portable containers. These containers encapsulate an application, its dependencies, and its environment, ensuring consistent behavior across different development, testing, and production environments. Docker's containerization technology offers numerous advantages, including faster deployment times, better resource utilization, and ease of scaling and updating applications.

Introduction

#### 1. Basic Commands
- `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`: Run a new container. For instance, `docker run -d -p 80:80 nginx` starts a container in detached mode with port 80 exposed.
- `docker ps`: List running containers. Shows details like container ID, image used, when created, status, ports, and names.
- `docker ps -a`: List all containers, including stopped ones.
- `docker stop [CONTAINER]`: Stop a specific running container.
- `docker rm [CONTAINER]`: Remove a stopped container.

#### 2. Image Management
- `docker images`: List all images on the host. Shows repository, tag, image ID, creation time, and size.
- `docker pull [IMAGE]`: Download an image from a registry, like `docker pull ubuntu`.
- `docker rmi [IMAGE]`: Remove an image from the local storage.
- `docker build -t [TAG] .`: Build an image from a Dockerfile in the current directory. The `-t` tag allows naming the image.

#### 3. Container Management
- `docker exec -it [CONTAINER] [COMMAND]`: Run a command in a running container, like `docker exec -it my_container bash` to start a bash shell.
- `docker logs [CONTAINER]`: Fetch and follow the logs of a container.
- `docker cp [SRC_PATH] [CONTAINER]:[DEST_PATH]`: Copy files from the host to a container.
- `docker cp [CONTAINER]:[SRC_PATH] [DEST_PATH]`: Copy files from a container to the host.

#### 4. Networking
- `docker network ls`: List all networks on the Docker host.
- `docker network create [OPTIONS] [NETWORK]`: Create a new network, like `docker network create my_network`.
- `docker network rm [NETWORK]`: Remove a network.
- `docker network connect [NETWORK] [CONTAINER]`: Connects a container to a network.

#### 5. Volume Management
- `docker volume ls`: List all volumes. Useful for managing persistent data.
- `docker volume create [OPTIONS] [VOLUME]`: Create a new volume, like `docker volume create my_volume`.
- `docker volume rm [VOLUME]`: Delete a volume.
- `docker volume inspect [VOLUME]`: Displays detailed information on one or more volumes.

#### 6. Docker Compose
- `docker-compose up`: Start and run the entire app defined in a `docker-compose.yml` file.
- `docker-compose down`: Stop and remove containers, networks, images, and volumes created by `docker-compose up`.
- `docker-compose build`: Builds or rebuilds services defined in a `docker-compose.yml` file.
- `docker-compose logs [SERVICE]`: View output from containers.

#### **7. Docker Security Best Practices**
- `Use Trusted Base Images`: Always use official or verified images from trusted sources like Docker Hub.
- `Keep Images Up-to-Date`: Regularly update your images to include the latest security patches.
- `Minimize Runtime Privileges`: Run containers with the least privileges necessary.

#### **8. Dockerfile Best Practices**
- `Optimize Layering`: Minimize the number of layers and combine commands to reduce image size.
- `Use Multi-Stage Builds`: Implement multi-stage builds to keep your final image clean and small.
- `Specify a Non-Root User`: Avoid running containers as root; create a user and group in your Dockerfile.

#### **9. Docker Troubleshooting Tips**
- `Inspecting Containers`: Use `docker inspect` to get detailed information about the configuration and state of a container.
- `Viewing Logs: Use` `docker logs [CONTAINER]` to troubleshoot issues related to a container's operation.
- `**Monitoring Resource Usage`: Utilize `docker stats` to monitor the resource usage of containers.

#### Additional Commands
- `docker inspect [OBJECT_NAME/ID]`: Get detailed information on containers, images, or volumes.
- `docker login [SERVER]`: Log into a Docker registry server.
- `docker logout [SERVER]`: Log out from a Docker registry server.
- `docker stats`: Display a live stream of container(s) resource usage statistics.
- `docker system prune`: Remove all stopped containers, dangling images, and unused networks.

**Note**: Replace placeholders like `[CONTAINER]`, `[IMAGE]`, etc., with actual container names, image names, or other relevant information.

## **Conclusion**
Docker's versatility and efficiency in container management have made it an indispensable tool in modern software development. This cheat sheet serves as a quick reference guide to navigate the extensive capabilities of Docker, helping both novices and seasoned professionals to maximize their productivity in containerization.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## Contact

If you have any questions, comments, or suggestions about **Docker Cheat sheet**, please feel free to contact me:

- LinkedIn: [Halil Ibrahim Deniz](https://www.linkedin.com/in/halil-ibrahim-deniz/)
- TryHackMe: [Halilovic](https://tryhackme.com/p/halilovic)
- Instagram: [deniz.halil333](https://www.instagram.com/deniz.halil333/)
- YouTube: [Halil Deniz](https://www.youtube.com/c/HalilDeniz)
- Email: halildeniz313@gmail.com


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 💰 You can help me by Donating
  Thank you for considering supporting me! Your support enables me to dedicate more time and effort to creating useful **Cheat Sheet** and developing new projects. By contributing, you're not only helping me improve existing tools but also inspiring new ideas and innovations. Your support plays a vital role in the growth of this project and future endeavors. Together, let's continue building and learning. Thank you!"<br>
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/halildeniz)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/denizhalil) 

  