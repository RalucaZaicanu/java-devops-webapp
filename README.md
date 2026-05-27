# Java Spring Boot Task Manager - DevOps CI/CD Pipeline

This project is a **Java Spring Boot Task Manager web application** deployed through an automated DevOps CI/CD pipeline using **GitHub, Jenkins, Docker, Docker Hub, Ansible, and Kubernetes**.

The application allows users to create and manage tasks from a simple web interface. The main goal of this project is to demonstrate a complete deployment workflow where code changes pushed to GitHub automatically trigger a Jenkins pipeline, build and push a Docker image, and deploy the latest application version to a Kubernetes server.

---

## Project Overview

The project has two main parts:

1. **Task Manager Web Application**
   - Built with Java and Spring Boot
   - Uses Spring MVC for request handling
   - Uses Thymeleaf for server-side HTML rendering
   - Provides a simple interface for managing tasks

2. **DevOps CI/CD Pipeline**
   - GitHub stores the source code
   - Jenkins is triggered automatically through a GitHub webhook
   - Jenkins connects to the Ansible server using SSH
   - The Ansible server builds the Docker image
   - The image is pushed to Docker Hub
   - The Ansible server connects to the Kubernetes server
   - Kubernetes pulls the Docker image from Docker Hub and runs the application

---

## Application Features

The Task Manager application includes:

- Add new tasks with title, description, and priority
- View all tasks in a web interface
- Filter tasks by status: all, active, or completed
- Mark tasks as completed
- Delete tasks
- Display task statistics such as total, active, and completed tasks
- Styled frontend using HTML, CSS
- Server-side rendering using Thymeleaf

---

## Technologies Used

### Application

- Java
- Spring Boot
- Spring MVC
- Maven
- Thymeleaf
- HTML
- CSS

### DevOps and Deployment

- Git
- GitHub
- Jenkins
- Docker
- Docker Hub
- Ansible
- Kubernetes
- AWS EC2


---

## CI/CD Architecture

```text
Developer
   |
   | Push code
   v
GitHub Repository
   |
   | Webhook trigger
   v
Jenkins Server
   |
   | SSH connection
   v
Ansible Server
   |
   | Builds Docker image
   | Pushes Docker image to Docker Hub
   | Connects to Kubernetes server using SSH
   v
Kubernetes Server
   |
   | Pulls Docker image from Docker Hub
   | Runs the application inside a pod
   | Exposes the application using NodePort
   v
Browser
