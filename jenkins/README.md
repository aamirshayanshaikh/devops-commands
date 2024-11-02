# Jenkins Commands
## Setting Up Jenkins

This section outlines the steps to set up Jenkins on an Amazon EC2 instance running Amazon Linux 2.

## Steps to Install Jenkins

1. **Create EC2 Instance**
    - Launch an EC2 instance using the Amazon Linux 2 AMI.

2. **Switch to Root User**
   ```bash
   sudo -i

3. **Install Java 17**
   ```bash
   yum install git fontconfig java-17 -y

4. **Verify Java Installation**
   ```bash
   java --version

5. **Add Jenkins Repository**
   ```bash
   sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

6. **Import Jenkins GPG Key**
   ```bash
   sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

7. **Install Jenkins**
   ```bash
   yum install jenkins -y

8. **Check Jenkins Status**
   ```bash
   systemctl status jenkins

9. **Start Jenkins**
   ```bash
   systemctl start jenkins
9. **Enable Jenkins to Start on Boot**
   ```bash
   systemctl enable jenkins  # Jenkins will start automatically when EC2 is restarted
   
10. **Switch to Root User**
   ```bash
   cat /var/lib/jenkins/secrets/initialAdminPassword
