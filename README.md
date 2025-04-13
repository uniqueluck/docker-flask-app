# 🐳 Dockerized Flask App - End-to-End Setup on AWS EC2

This project demonstrates how to build and run a simple Flask web application inside a Docker container on an AWS EC2 Ubuntu instance.
It also includes configuring SSH with GitHub and pushing the project to a GitHub repository.

---

## 🚀 What You’ll Learn

- Launching an EC2 instance (Ubuntu)
- Installing Docker
- Creating a Flask app
- Writing a Dockerfile
- Building and running a Docker container
- Setting up SSH keys to push to GitHub
- Hosting and accessing the app via browser

---

## 🏗️ Step-by-Step Setup

---

### 1️⃣ Launch an EC2 Ubuntu Instance

1. Go to the AWS Management Console.
2. Launch an EC2 instance using:
   - AMI: Ubuntu 22.04
   - Instance type: t2.micro (Free tier)
   - Key pair: Create new or use existing
   - Security group:
     - Allow **port 22** (SSH)
     - Allow **port 5000** (Flask)
       ![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/fe5db788c4f3282cc910c2590174a0b8065bf9b7/ec2_launch.jpg)

3. Connect using SSH:
   ```bash
   ssh -i your-key.pem ubuntu@<your-ec2-public-ip>

### 2️⃣ Install Docker

sudo apt update

sudo apt install docker.io -y

sudo systemctl start docker

sudo systemctl enable docker

sudo usermod -aG docker ubuntu


![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/Screenshot_install_docker.png)


### 3️⃣ Create Your Flask App
mkdir myapp && cd myapp
nano app.py
![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/app.py)


### 4️⃣ Add requirements.txt
![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/Screenshot_requr.png)

### 5️⃣ Create a Dockerfile
![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/Screenshot%20_DF.png)

### 6️⃣ Build and Run Docker Container
![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/Screenshot_Command.png)


docker build -t myapp .

docker run -p 5000:5000 myapp

✔️ App will be accessible at:
http://<your-ec2-public-ip>:5000
![App Screenshot](https://github.com/uniqueluck/docker-flask-app/blob/1bcfb2251791e563aab7ff222b63621b8f400ba0/Screenshot_output.png)


