# Task 4 - Deploy a Docker Container on Cloud VM

## Objective
The objective of this task was to deploy a Docker-based web application (Nginx) on an AWS EC2 Virtual Machine and make it accessible over the internet.

---

# Services & Technologies Used

- AWS EC2
- Docker
- Nginx
- Ubuntu Server 24.04 LTS
- Linux Commands

---

# Instance Configuration

| Setting | Value |
|---|---|
| Instance Name | Docker-Web-Server |
| Operating System | Ubuntu Server 24.04 LTS |
| Instance Type | t2.micro |
| Web Server | Nginx |
| Container Platform | Docker |

---

# Step 1: Launching the AWS EC2 Instance

1. Logged into AWS Management Console
2. Opened the EC2 service
3. Clicked on:
   ```bash
   Launch Instance
   ```
4. Named the instance:
   ```bash
   Docker-Web-Server
   ```
5. Selected:
   ```bash
   Ubuntu Server 24.04 LTS
   ```
6. Chose instance type:
   ```bash
   t2.micro
   ```

---

# Step 2: Configuring Security Group

Configured inbound rules to allow:

| Type | Port | Source |
|---|---|---|
| SSH | 22 | Anywhere |
| HTTP | 80 | Anywhere |

This allowed:
- SSH access to the VM
- Public web access for Nginx

---

# Step 3: Connecting to the Instance

Connected to the EC2 instance using:
```bash
EC2 Instance Connect
```

---

# Step 4: Updating System Packages

Updated Ubuntu packages using:

```bash
sudo apt update -y
```

---

# Step 5: Installing Docker

Installed Docker Engine on Ubuntu VM.

## Commands Used

```bash
sudo apt install docker.io -y
```

Started Docker service:

```bash
sudo systemctl start docker
```

Enabled Docker service on boot:

```bash
sudo systemctl enable docker
```

---

# Step 6: Verifying Docker Installation

Checked Docker version:

```bash
docker --version
```

Example Output:

```bash
Docker version 24.x.x
```

---

# Step 7: Running Nginx Docker Container

Pulled and ran the official Nginx image from Docker Hub.

## Command Used

```bash
sudo docker run -d -p 80:80 --name my-web-server nginx
```

Explanation:
- `-d` → Run container in background
- `-p 80:80` → Map VM port 80 to container port 80
- `--name` → Assign container name

---

# Step 8: Verifying Running Container

Checked running Docker containers:

```bash
sudo docker ps
```

This confirmed that the Nginx container was running successfully.

---

# Step 9: Final Output

Copied the Public IPv4 Address of the EC2 instance and opened it in the browser.

## Public IP

```bash
http://3.107.12.249
```

The browser successfully displayed:

```bash
Welcome to nginx!
```

This confirmed successful deployment of the Docker container.

---

# Docker Commands Summary

| Command | Purpose |
|---|---|
| sudo apt install docker.io -y | Install Docker |
| sudo systemctl start docker | Start Docker |
| sudo systemctl enable docker | Enable Docker on boot |
| docker --version | Check Docker version |
| sudo docker run -d -p 80:80 nginx | Run Nginx container |
| sudo docker ps | List running containers |
| sudo docker stop container_id | Stop running container |

---

# Learning Outcomes

Through this task, I learned:
- Basics of Docker containerization
- Installing Docker on Linux VM
- Running containers on AWS EC2
- Port mapping in Docker
- Hosting web applications using Nginx
- Cloud VM management using AWS

---

# Status

✅ Task Completed Successfully

---

# Author

Shreya Mittal
```
