# Comprehensive Docker Cheat Sheet for Developers

<img src="source/docker-cheat-sheet.png"></img>


## **Introduction**
Docker has revolutionized software development by offering an efficient and standardized method to deploy applications across various environments. As a versatile tool, it simplifies the process of containerization, allowing developers to focus on innovation rather than infrastructure. This cheat sheet is designed to assist both beginners and experienced professionals in navigating Docker's extensive capabilities. It highlights essential commands and their applications, providing a quick reference to enhance productivity in software development.

## **What is Docker?**
Docker is an open-source platform that automates the deployment of applications inside lightweight and portable containers. These containers encapsulate an application, its dependencies, and its environment, ensuring consistent behavior across different development, testing, and production environments. Docker's containerization technology offers numerous advantages, including faster deployment times, better resource utilization, and ease of scaling and updating applications.

## **1. Basic Commands**

1. **`docker run`**: Creates and starts a new container.
   - Example: `docker run -d --name myapp -p 5000:5000 myimage` runs a container in detached mode, maps port 5000 of the container to port 5000 on the host, and names the container `myapp`.

2. **`docker ps`**: Lists currently running containers.
   - Example: `docker ps` displays all running containers with details like container ID, image name, creation time, status, and ports.

3. **`docker ps -a`**: Lists all containers, both running and stopped.
   - Example: `docker ps -a` shows every container, including those that are not currently running.

4. **`docker stop`**: Stops a running container.
   - Example: `docker stop myapp` stops the container named `myapp`.

5. **`docker rm`**: Removes a container.
   - Example: `docker rm myapp` removes the container named `myapp`. Use `-f` to force removal of a running container.

6. **`docker start`**: Starts a stopped container.
   - Example: `docker start myapp` will start the previously stopped container named `myapp`.

7. **`docker restart`**: Restarts a container.
   - Example: `docker restart myapp` restarts the container named `myapp`.

8. **`docker pull`**: Pulls an image from a registry.
   - Example: `docker pull ubuntu` pulls the latest Ubuntu image from the Docker Hub.

9. **`docker push`**: Pushes an image to a registry.
   - Example: `docker push myusername/myimage` pushes the image `myimage` to your Docker Hub repository.

10. **`docker attach`**: Attaches to a running container.
    - Example: `docker attach myapp` will attach your terminal input/output/error streams to the `myapp` container.

11. **`docker logs`**: Fetches logs from a container.
    - Example: `docker logs myapp` shows logs of `myapp`. Use `-f` to follow the log output.

12. **`docker inspect`**: Returns detailed information on the container or image.
    - Example: `docker inspect myapp` returns low-level information about the container or image named `myapp`.

13. **`docker pause`**: Pauses a running container, freezing its processes.
    - Example: `docker pause myapp` pauses the processes in `myapp`.

14. **`docker unpause`**: Unpauses a paused container.
    - Example: `docker unpause myapp` resumes the processes in `myapp`.

15. **`docker exec`**: Runs a command in a running container.
    - Example: `docker exec -it myapp bash` opens a bash shell in the `myapp` container.

16. **`docker kill`**: Kills a running container by sending a SIGKILL signal.
    - Example: `docker kill myapp` immediately stops the container `myapp`.

These commands form the backbone of basic Docker container management and will be useful in various scenarios when working with Docker. Remember to replace placeholders like `[CONTAINER]` or `[IMAGE]` with actual container or image names.

---

## 2. **Image Management**

1. **`docker images`**: Lists all Docker images on the host.
   - Example: `docker images` will show all images, their repository names, tags, IDs, when they were created, and their sizes.

2. **`docker pull [IMAGE]`**: Downloads an image from a Docker registry.
   - Example: `docker pull nginx` will download the latest Nginx image from Docker Hub.

3. **`docker rmi [IMAGE]`**: Removes one or more images from local storage.
   - Example: `docker rmi nginx` removes the Nginx image. If the image is in use by a container, you might need to use the `-f` flag to force removal.

4. **`docker build -t [TAG] .`**: Builds a Docker image from a Dockerfile in the current directory.
   - Example: `docker build -t myapp:1.0 .` builds an image from the Dockerfile in the current directory and tags it as `myapp:1.0`.

5. **`docker tag [SOURCE_IMAGE] [TARGET_IMAGE]`**: Tags a local image with a new name.
   - Example: `docker tag myapp:1.0 myusername/myapp:latest` tags the `myapp:1.0` image for pushing to your Docker Hub repository.

6. **`docker push [IMAGE]`**: Pushes an image to a Docker registry.
   - Example: `docker push myusername/myapp:latest` pushes the image to your Docker Hub repository under the tag `latest`.

7. **`docker history [IMAGE]`**: Shows the history of an image.
   - Example: `docker history nginx` shows the layer history of the Nginx image.

8. **`docker save [IMAGE] > [TAR_FILE]`**: Saves an image to a tar archive.
   - Example: `docker save myapp > myapp.tar` saves the `myapp` image to a tar file named `myapp.tar`.

9. **`docker load < [TAR_FILE]`**: Loads an image from a tar archive.
   - Example: `docker load < myapp.tar` loads the image from `myapp.tar` into Docker.

10. **`docker image prune`**: Removes dangling images.
    - Example: `docker image prune` will remove all images without at least one container associated with them.

11. **`docker search [TERM]`**: Searches Docker Hub for images.
    - Example: `docker search nginx` searches for all images with 'nginx' in their name or description on Docker Hub.

These additional commands provide a more comprehensive overview of managing Docker images, from building and tagging to archiving and searching. Remember to replace placeholders like `[IMAGE]`, `[SOURCE_IMAGE]`, `[TARGET_IMAGE]`, and `[TAR_FILE]` with the appropriate names or paths.

---

## **3. Container Management**

1. **`docker exec -it [CONTAINER] [COMMAND]`**: Executes a command in a running container.
   - Example: `docker exec -it mycontainer bash` opens a bash shell in the `mycontainer`.

2. **`docker logs [CONTAINER]`**: Fetches the logs of a container.
   - Example: `docker logs mycontainer` shows the logs of `mycontainer`. Use `-f` to follow the log output.

3. **`docker cp [SRC_PATH] [CONTAINER]:[DEST_PATH]`**: Copies files from the host to a container.
   - Example: `docker cp ./myfile.txt mycontainer:/myfile.txt` copies `myfile.txt` from the host to `mycontainer`.

4. **`docker cp [CONTAINER]:[SRC_PATH] [DEST_PATH]`**: Copies files from a container to the host.
   - Example: `docker cp mycontainer:/myfile.txt ./myfile.txt` copies `myfile.txt` from `mycontainer` to the host.

5. **`docker inspect [CONTAINER]`**: Returns detailed information about a container.
   - Example: `docker inspect mycontainer` provides detailed information about the container `mycontainer`.

6. **`docker stats [CONTAINER]`**: Displays a live stream of container(s) resource usage statistics.
   - Example: `docker stats mycontainer` shows real-time resource usage for `mycontainer`.

7. **`docker rename [OLD_NAME] [NEW_NAME]`**: Renames a container.
   - Example: `docker rename mycontainer newcontainer` renames `mycontainer` to `newcontainer`.

8. **`docker pause [CONTAINER]`**: Pauses all processes within a container.
   - Example: `docker pause mycontainer` pauses processes in `mycontainer`.

9. **`docker unpause [CONTAINER]`**: Unpauses a paused container.
   - Example: `docker unpause mycontainer` resumes processes in `mycontainer`.

10. **`docker port [CONTAINER]`**: Lists port mappings or a specific mapping for the container.
    - Example: `docker port mycontainer` shows the port mappings for `mycontainer`.

11. **`docker top [CONTAINER]`**: Displays the running processes of a container.
    - Example: `docker top mycontainer` shows running processes in `mycontainer`.

12. **`docker diff [CONTAINER]`**: Inspects changes to files or directories on a container’s filesystem.
    - Example: `docker diff mycontainer` shows files that have been added, deleted, or modified in `mycontainer`.

13. **`docker commit [CONTAINER] [REPOSITORY[:TAG]]`**: Creates a new image from a container’s changes.
    - Example: `docker commit mycontainer myimage:latest` creates a new image `myimage` with the tag `latest` from the state of `mycontainer`.

14. **`docker restart [CONTAINER]`**: Restarts a container.
    - Example: `docker restart mycontainer` restarts `mycontainer`.

15. **`docker attach [CONTAINER]`**: Attaches local standard input, output, and error streams to a running container.
    - Example: `docker attach mycontainer` will attach to `mycontainer`, allowing interaction with the container.

These additional commands cover a wide range of container management tasks, providing greater control and insight into your Docker containers. As always, replace placeholders like `[CONTAINER]`, `[SRC_PATH]`, `[DEST_PATH]`, `[OLD_NAME]`, `[NEW_NAME]`, and `[REPOSITORY[:TAG]]` with actual container names, paths, or tags.

---

## **4. Networking**

1. **`docker network ls`**: Lists all networks on the Docker host.
   - Example: `docker network ls` will display all networks, showing details like network ID, name, and driver.

2. **`docker network create [OPTIONS] [NETWORK]`**: Creates a new network.
   - Example: `docker network create --driver bridge my_network` creates a new bridge network named `my_network`.

3. **`docker network rm [NETWORK]`**: Removes one or more networks.
   - Example: `docker network rm my_network` removes the network named `my_network`.

4. **`docker network connect [NETWORK] [CONTAINER]`**: Connects a container to a network.
   - Example: `docker network connect my_network mycontainer` connects `mycontainer` to `my_network`.

5. **`docker network disconnect [NETWORK] [CONTAINER]`**: Disconnects a container from a network.
   - Example: `docker network disconnect my_network mycontainer` disconnects `mycontainer` from `my_network`.

6. **`docker network inspect [NETWORK]`**: Displays detailed information on one or more networks.
   - Example: `docker network inspect my_network` provides detailed information about `my_network`.

7. **`docker network prune`**: Removes all unused networks.
   - Example: `docker network prune` will remove all networks not used by at least one container.

8. **`docker network create --subnet [CIDR] --gateway [IP] [NETWORK]`**: Creates a network with a specific subnet and gateway.
   - Example: `docker network create --subnet 192.168.1.0/24 --gateway 192.168.1.1 my_custom_network` creates a network with a specified subnet and gateway.

These expanded networking commands offer a more comprehensive understanding of managing networks within Docker. This includes connecting and disconnecting containers from networks, inspecting network configurations, and customizing network options such as subnets and gateways. Remember to replace placeholders like `[NETWORK]`, `[CONTAINER]`, `[CIDR]`, and `[IP]` with actual network names, container names, CIDR notation, or IP addresses as needed.

---

## **5. Volume Management**

1. **`docker volume ls`**: Lists all the volumes on the Docker host.
   - Example: `docker volume ls` will display all volumes, showing details like volume name, driver, and mount point.

2. **`docker volume create [OPTIONS] [VOLUME]`**: Creates a new volume.
   - Example: `docker volume create my_volume` creates a new volume named `my_volume`.

3. **`docker volume rm [VOLUME]`**: Removes one or more volumes.
   - Example: `docker volume rm my_volume` deletes the volume named `my_volume`.

4. **`docker volume inspect [VOLUME]`**: Displays detailed information on one or more volumes.
   - Example: `docker volume inspect my_volume` provides detailed information about `my_volume`.

5. **`docker volume prune`**: Removes all unused volumes.
   - Example: `docker volume prune` will remove all volumes not used by at least one container.

6. **`docker run -v [VOLUME]:[CONTAINER_PATH] [IMAGE]`**: Starts a new container and mounts a volume.
   - Example: `docker run -v my_volume:/data myimage` starts a container using `myimage` and mounts `my_volume` at `/data` inside the container.

7. **`docker run -v [HOST_PATH]:[CONTAINER_PATH] [IMAGE]`**: Mounts a bind mount, which maps a host path to a container path.
   - Example: `docker run -v /my/host/path:/container/path myimage` binds the host directory `/my/host/path` to `/container/path` inside the container.

8. **`docker run --mount type=volume,source=my_volume,target=/data [IMAGE]`**: Uses the `--mount` flag for more explicit volume mounting.
   - Example: `docker run --mount type=volume,source=my_volume,target=/data myimage` starts a container with `my_volume` mounted at `/data`.

These commands provide a solid foundation for managing Docker volumes. Volumes are essential for persistent data storage and sharing data between the container and the host system. This expanded set of commands includes creating, inspecting, removing, and using volumes in various scenarios. Remember to replace placeholders like `[VOLUME]`, `[CONTAINER_PATH]`, `[HOST_PATH]`, and `[IMAGE]` with actual volume names, container paths, host paths, or image names as applicable.

---

## **6. Docker Compose**

1. **`docker-compose up`**: Builds, (re)creates, starts, and attaches to containers for a service defined in `docker-compose.yml`.
   - Example: `docker-compose up` starts the entire application as defined. Use `-d` to run in detached mode.

2. **`docker-compose down`**: Stops and removes the containers, networks, volumes, and images created by `docker-compose up`.
   - Example: `docker-compose down` will stop and remove the resources specified in the `docker-compose.yml` file.

3. **`docker-compose build`**: Builds or rebuilds services defined in a `docker-compose.yml` file.
   - Example: `docker-compose build` rebuilds all the services in the file, ensuring that the latest configuration is used.

4. **`docker-compose logs [SERVICE]`**: View output from containers.
   - Example: `docker-compose logs web` shows the logs for the `web` service.

5. **`docker-compose restart [SERVICE]`**: Restarts all stopped and running services.
   - Example: `docker-compose restart` restarts all the services defined in the `docker-compose.yml` file.

6. **`docker-compose exec [SERVICE] [COMMAND]`**: Executes a command in a running container.
   - Example: `docker-compose exec web bash` opens a bash shell in the `web` service container.

7. **`docker-compose stop [SERVICE]`**: Stops running services without removing them.
   - Example: `docker-compose stop web` stops the `web` service but does not remove the container.

8. **`docker-compose start [SERVICE]`**: Starts existing containers for a service.
   - Example: `docker-compose start web` starts the previously stopped `web` service.

9. **`docker-compose run [SERVICE] [COMMAND]`**: Runs a one-time command against a service.
   - Example: `docker-compose run web npm test` runs `npm test` in a temporary container of the `web` service.

10. **`docker-compose pull [SERVICE]`**: Pulls service images.
    - Example: `docker-compose pull` pulls all images needed for the services defined in `docker-compose.yml`.

11. **`docker-compose ps`**: Lists containers.
    - Example: `docker-compose ps` shows the containers related to the services defined in the `docker-compose.yml` file.

12. **`docker-compose scale [SERVICE]=NUM`**: Scales a service to a specified number of containers.
    - Example: `docker-compose scale web=4` scales the `web` service to 4 containers.

These Docker Compose commands offer a comprehensive toolkit for managing multi-container Docker applications defined in a `docker-compose.yml` file. They allow you to control the lifecycle of your application's services, from building and starting services to scaling and stopping them. Remember to replace placeholders like `[SERVICE]` and `[COMMAND]` with actual service names or commands as needed.

---

## **7. Docker Security Best Practices**
1. **Use Trusted Base Images**: Always use official or verified images from trusted sources like Docker Hub.
2. **Keep Images Up-to-Date**: Regularly update your images to include the latest security patches.
3. **Minimize Runtime Privileges**: Run containers with the least privileges necessary.
4. **Secure Docker Daemon Socket**: Protect the Docker daemon socket, and use TLS authentication for Docker client-server communication.
5. **Implement Image Scanning**: Regularly scan images for vulnerabilities using tools like Clair or Trivy.
6. **Use Docker Bench for Security**: Employ Docker Bench for Security to check the host system and containers against Docker's security best practices.

---

## **8. Dockerfile Best Practices**
1. **Optimize Layering**: Minimize the number of layers and combine commands to reduce image size.
2. **Use Multi-Stage Builds**: Implement multi-stage builds to keep your final image clean and small.
3. **Specify a Non-Root User**: Avoid running containers as root; create a user and group in your Dockerfile.
4. **Leverage Build Cache**: Structure your Dockerfile to take advantage of Docker's caching mechanism.
5. **Use .dockerignore**: Include a .dockerignore file to prevent unnecessary files from being added to the image.
6. **Label Your Images**: Use LABEL to add metadata to your images, making them easier to identify and manage.

---

## **9. Docker Troubleshooting Tips**
1. **Inspecting Containers**: Use `docker inspect` to get detailed information about the configuration and state of a container.
2. **Viewing Logs**: Use `docker logs [CONTAINER]` to troubleshoot issues related to a container's operation.
3. **Monitoring Resource Usage**: Utilize `docker stats` to monitor the resource usage of containers.
4. **Checking Network Issues**: Use `docker network inspect` to diagnose network-related problems.
5. **Handling Stuck Containers**: If a container is stuck, try `docker stop` and `docker rm` commands to forcefully remove it.
6. **Debugging Dockerfile Issues**: For issues during build, carefully review the output of `docker build` and ensure all steps in your Dockerfile are correct.

---

## **Additional Commands**

1. **`docker inspect [OBJECT_NAME/ID]`**: Retrieves detailed information about containers, images, or volumes.
   - Example: `docker inspect mycontainer` provides detailed information about `mycontainer`, including its configuration and status.

2. **`docker login [SERVER]`**: Logs into a Docker registry server.
   - Example: `docker login` logs into Docker Hub, or `docker login myregistry.com` for a private registry.

3. **`docker logout [SERVER]`**: Logs out from a Docker registry server.
   - Example: `docker logout` logs out from Docker Hub, or `docker logout myregistry.com` for a private registry.

4. **`docker stats`**: Displays a live stream of resource usage statistics for running containers.
   - Example: `docker stats` shows the real-time resource usage for all running containers.

5. **`docker system prune`**: Removes all stopped containers, dangling images, and unused networks.
   - Example: `docker system prune` cleans up the system. Use `-a` to also remove unused images.

6. **`docker save [IMAGE] > [TAR_FILE]`**: Saves an image to a tar archive.
   - Example: `docker save myimage > myimage.tar` saves the `myimage` to a tar file.

7. **`docker load < [TAR_FILE]`**: Loads an image from a tar archive.
   - Example: `docker load < myimage.tar` loads the image from the tar file into Docker.

8. **`docker port [CONTAINER]`**: Lists port mappings of a specific container.
   - Example: `docker port mycontainer` lists the port mappings for `mycontainer`.

9. **`docker diff [CONTAINER]`**: Shows changes to files or directories in a container’s filesystem.
   - Example: `docker diff mycontainer` shows files that have been added, deleted, or modified in `mycontainer`.

10. **`docker top [CONTAINER]`**: Displays the running processes of a container.
    - Example: `docker top mycontainer` shows the running processes in `mycontainer`.

11. **`docker commit [CONTAINER] [REPOSITORY[:TAG]]`**: Creates a new image from a container's changes.
    - Example: `docker commit mycontainer mynewimage:1.0` creates a new image `mynewimage` with the tag `1.0` from `mycontainer`.

12. **`docker history [IMAGE]`**: Shows the history of an image.
    - Example: `docker history myimage` displays the layer history of the `myimage`.

13. **`docker search [TERM]`**: Searches Docker Hub for images.
    - Example: `docker search nginx` searches Docker Hub for images related to Nginx.

These additional commands provide a more nuanced control and insight into your Docker environment, covering aspects from image and container inspection to system maintenance and searching Docker Hub for images. Remember to replace placeholders like `[OBJECT_NAME/ID]`, `[SERVER]`, `[IMAGE]`, `[TAR_FILE]`, `[CONTAINER]`, and `[REPOSITORY[:TAG]]` with the appropriate names, paths, or tags as needed.

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

  
