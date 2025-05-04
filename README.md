# Docker Images

## Introduction
This project demonstrates the essential steps for working with Docker images, including pulling images, creating files, building images, tagging, pushing, and pulling images from a repository. It also focuses on containerizing a static web page using the Nginx image, exposing it on a web browser, and deploying it on an EC2 instance. The guide ensures that users understand the Docker workflow and its practical applications while meeting the instructor's requirements.

---

## Step 1: Setting Up the Environment
Before starting, create an EC2 instance to host your Docker containers. This instance provides the infrastructure needed to run and manage Docker containers. Ensure that the EC2 instance has Docker installed and is properly configured.

The following images show the process of setting up the EC2 instance:

1. **Launching the EC2 Instance:**  
   This image shows the EC2 instance being launched from the AWS Management Console. Ensure you select an appropriate instance type and configure the security group to allow necessary traffic.

   ![ec2](./img/16.%20EC2.jpg)

2. **Connecting to the EC2 Instance:**  
   This image demonstrates how to connect to the EC2 instance using SSH. Use the provided key pair to establish a secure connection.

   ![ec2](./img/18.%20Ec2%20connect.jpg)

3. **Successful Connection:**  
   This image confirms a successful connection to the EC2 instance. You are now ready to install Docker and proceed with the project.

   ![ec2](./img/19.%20Ec2%20connected.jpg)

---

## Step 2: Pulling the Nginx Docker Image
Pull the official Nginx Docker image from Docker Hub. Nginx is a lightweight and high-performance web server that will be used to serve the static web page in this project.

```bash
docker pull nginx
```

---

## Step 3: Verifying the Pulled Image
After pulling the image, verify its presence in your local Docker environment.

![3](./img/3U.%20Docker%20img.jpg)

---

## Step 4: Editing Files with Nano
Use a text editor like Nano to create or edit files required for your Docker container.

1. Create a file named `index.html`:

   ```bash
   nano index.html
   ```

   Add the following content to the `index.html` file:

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>My Static Web Page</title>
   </head>
   <body>
       <h1>Welcome to My Dockerized Web Page!</h1>
   </body>
   </html>
   ```

---

## Step 5: Creating a File
Create the necessary files for your Docker container. These files may include configuration files, Dockerfiles, or application code.

![5](./img/5U.%20Create%20file.jpg)

---

## Step 6: Building a Docker Image
Build a Docker image using the `docker build` command. This step packages your application and its dependencies into a single image.

![6](./img/6.%20build.jpg)

---

## Step 7: Configuring Inbound Rules
Set up inbound rules to allow traffic to your Docker container. This is essential for enabling external access to your application.

![7](./img/7u.%20inbound%20rule.jpg)

---

## Step 8: Verifying Output
Run your Docker container and verify the output to ensure everything is working as expected.

![8](./img/8.%20output.jpg)

---

## Step 9: Starting Docker
Start Docker to initialize your container and begin running your application.

![10](./img/10.%20start%20docker.jpg)

---

## Step 10: Accessing the Application
Access your application through the specified port (e.g., 8080) to confirm it is running correctly.

1. **Retrieve the EC2 Public IP Address:**  
   - Go to the AWS Management Console.
   - Navigate to the EC2 dashboard and select your instance.
   - Copy the "Public IPv4 address" from the instance details.

2. **Access the Application in a Browser:**  
   Open a browser and navigate to `http://<EC2_PUBLIC_IP>:8080`. Replace `<EC2_PUBLIC_IP>` with the public IP address of your EC2 instance.

The following images demonstrate this process:

- **Public IP Address:**  
  This image shows the public IP address of the EC2 instance, which is used to access the application.

  ![ec2](./img/17.%20public%20ip.jpg)

- **Browser Verification:**  
  This image confirms that the static web page is successfully served by the Nginx container and is accessible in a browser.

  ![11](./img/11u.%208080.jpg)

---

## Step 11: Logging into Docker Hub
Log in to Docker Hub to prepare for pushing your image to a repository.

![12](./img/12.%20Login.jpg)

---

## Step 12: Tagging the Docker Image
Tag your Docker image with a meaningful name and version to make it easier to identify in the repository.

![13](./img/13.%20tag.jpg)

---

## Step 13: Pushing the Docker Image
Push your Docker image to a repository, such as Docker Hub, to make it available for others to use.

![14](./img/14.%20Push.jpg)

---

## Step 14: Pulling the Docker Image
Finally, pull the Docker image from the repository to verify it was successfully uploaded and is accessible.

![15](./img/15.%20Pull.jpg)

---

# Docker Containers and Simple Commands

## Docker Commands and Troubleshooting

1. **Running a Docker Container**  
   This image demonstrates the `docker run` command, which is used to create and start a container from a specified image. The command can include options to map ports, set environment variables, and more.

   ![20](./img/20.%20Docker%20run.jpg)

2. **Starting a Container and Troubleshooting**  
   This image shows the process of starting a stopped container using the `docker start` command. It also highlights basic troubleshooting steps, such as checking container logs with `docker logs <container_id>` to identify issues if the container fails to start.

   ![21](./img/21.%20start%20plus%20trouble%20shoot.jpg)

   **Troubleshooting Process:**
   - Use `docker ps -a` to list all containers and identify the container ID or name.
   - Run `docker logs <container_id>` to view the logs and diagnose the issue.
   - If the issue persists, inspect the container using `docker inspect <container_id>` for detailed configuration and error information.
   - Restart the container with `docker restart <container_id>` after resolving the issue.

3. **Stopping a Docker Container**  
   This image illustrates the `docker stop` command, which gracefully stops a running container by sending a SIGTERM signal.

   ![22](./img/22.%20docker%20stop.jpg)

4. **Restarting a Docker Container**  
   This image shows the `docker restart` command, which stops and then starts a container in one step.

   ![23](./img/23.%20docker%20restart.jpg)

5. **Removing a Docker Container**  
   This image demonstrates the `docker rm` command, which is used to delete a stopped container. Ensure the container is not running before attempting to remove it.

   ![24](./img/24.%20docker%20remove.jpg)

---

## Project Summary

This project provided a comprehensive guide to working with Docker images and containers. It covered the following key steps:

1. Setting up an EC2 instance to host Docker containers.
2. Pulling and verifying the Nginx Docker image.
3. Creating and editing files for a static web page.
4. Building and tagging Docker images.
5. Pushing and pulling images from Docker Hub.
6. Running and managing Docker containers using essential commands.
7. Troubleshooting container issues using logs and inspection tools.

By following these steps, users gained hands-on experience with Docker's core functionalities, enabling them to containerize applications and deploy them effectively.

