End-to-End DevOps Automation with Jenkins + Ansible
Objective: Automate infrastructure setup and app deployment using IaC.
Tools & Technologies: Jenkins, Ansible, Docker, Git, Linux
  # Deliverables:
  1. Jenkins pipeline integrated with Ansible
  2. Playbook for app deployment
  3. Continuous delivery demo
# Architecutre Diagram
<img width="576" height="324" alt="architture" src="https://github.com/user-attachments/assets/d90e93c9-722e-4007-9086-74a152a996c0" />

🚀 Quick Start

Deploy Two EC2 Instances (Ubuntu) one for Jenkins, Docker, and Ansible.
One for Production Server
Instances:
t2.medium for jenkins, docker, Ansible.
t2.micro for Prod server

🚀 Quick Start

Deploy Two Server in vm (Linux) one for Jenkins, Docker, and Ansible.
One for Production Server

Install Jenkins

sudo yum update -y
sudo yum  upgrade -y
sudo yum update -y
sudo yum install java-17-amazon-corretto -y
java -version
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum install jenkins -y

Install Docker
sudo dnf update -y
sudo dnf install docker -y


After the Installation is done start and enable the services

systemctl start docker
systemctl start Jenkins
systemctl start ansible
systemctl enable docker
systemctl enable jenkins

Install Ansible
sudo yum update -y
sudo yum install ansible -y
ansible --version

<img width="906" height="404" alt="image" src="https://github.com/user-attachments/assets/82b1c8c8-9786-430c-9b7c-b7b05134a3cb" />

Give permissions for docker and Jenkins
sudo usermod -aG docker ubuntu
sudo usermod -aG docker jenkins
newgrp docker
sudo getent group docker

# Set jenkins password
<img width="1813" height="942" alt="image" src="https://github.com/user-attachments/assets/f561a9de-4938-41db-b86c-798ff083b892" />


sudo cat /var/lib/jenkins/secrets/initialAdminPassword
XXXXXXXX

# copy the password and paste in jenkins

<img width="1651" height="909" alt="image" src="https://github.com/user-attachments/assets/16a1fae8-fe9c-484f-94d3-bbafad2f0370" />

Install plugins in jenkins maven and ansible
# Install plugins in jenkins maven and ansible
<img width="1914" height="599" alt="image" src="https://github.com/user-attachments/assets/ad5a36bc-d6fc-4f5e-b3da-fa12b78fa8b5" />

# Install maven and ansible in Jenkins
<img width="1702" height="568" alt="image" src="https://github.com/user-attachments/assets/73bd0efe-2315-4cee-af6e-e916a233fd6e" />

<img width="1592" height="552" alt="image" src="https://github.com/user-attachments/assets/a31eb774-dc3e-441d-9a7d-003bf6114ad3" />

Create a Job and write a pipeline
 <img width="885" height="378" alt="image" src="https://github.com/user-attachments/assets/f46cb59e-f886-4184-aa12-81e2d199860c" />

 Setting up webhooks
Click on settings on github repo
<img width="929" height="425" alt="image" src="https://github.com/user-attachments/assets/db312ce4-f10f-4a35-a960-6b74abbd002d" />
Select Webhook and add webhook
<img width="940" height="433" alt="image" src="https://github.com/user-attachments/assets/2e0228a3-f9da-452c-b339-551c2bc3d768" />
<img width="901" height="407" alt="image" src="https://github.com/user-attachments/assets/25cf005b-61b2-4648-91e2-e9dd6ba3617b" />
<img width="927" height="404" alt="image" src="https://github.com/user-attachments/assets/00f2049f-3e66-40c1-a0c4-d2574a063db4" />


Create a Ansible Playbook and Inventory file in the github repo
  deploy-docker.yml
  dev.inv
CI/CD Flow
Once a commit is pushed to GitHub:
  The webhook triggers Jenkins
  Jenkins builds the app with Maven
  Docker image is built and pushed to DockerHub
  Ansible deploys the container to the production server
  ✅ Output
🖥️ Application Running on Production Server
<img width="503" height="285" alt="image" src="https://github.com/user-attachments/assets/f18d31f8-2fc9-4433-8bf5-fca48dc3a4eb" />
Docker images
<img width="844" height="191" alt="image" src="https://github.com/user-attachments/assets/8b4f9040-be51-4871-9706-0cb38023fd32" />
DockerHub Upload
<img width="953" height="286" alt="image" src="https://github.com/user-attachments/assets/13e8dd71-46b1-473e-a7de-45b7be5f182e" />
 Summary
 This project demonstrates a complete CI/CD pipeline using Jenkins, Docker, and Ansible — enabling automated build, deployment, 
and delivery with minimal manual intervention
Author: [Ruqiya]

https://github.com/ruqiyabangar/End-to-End-DevOps-Automation-with-Jenkins-Ansible
