Install Jenkins, configure Docker as agent, set up cicd, deploy applications to k8s and much more.

AWS EC2 Instance

  1. Go to AWS Console
  2. Instances(running)
  3. Launch instances

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/e3e433b8-13ac-43a3-9bf4-69e79b6dceba" />

## Install Jenkins.
  Pre-Requisites:
    Java (JDK)
    Run the below commands to install Java and Jenkins
    Install Java
      ```sudo apt update```
      ```sudo apt install openjdk-17-jre````

    Verify Java is Installed
    
      ```java --version```
      
    Now, you can proceed with installing Jenkins

    ```bash 
    curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins
    
**Note: ** By default, Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS. Open port 8080 in the 
inbound traffic rules as show below.

 1. EC2 > Instances > Click on
 2. In the bottom tabs -> Click on Security
 3. Security groups
 4. Add inbound traffic rules as shown in the image (you can just allow TCP 8080 as well, in my case, I allowed All traffic).

<img width="700" height="396" alt="image" src="https://github.com/user-attachments/assets/f84a5d6b-37f9-4b95-88f0-5c588c913ae7" />

## Login to Jenkins using the below URL:

http://:8080 [You can get the ec2-instance-public-ip-address from your AWS EC2 console page]

Note: If you are not interested in allowing All Traffic to your EC2 instance 1. Delete the inbound traffic rule for your instance 2. Edit the inbound traffic rule to only allow custom TCP port 8080

After you login to Jenkins, - Run the command to copy the Jenkins Admin Password - sudo cat /var/lib/jenkins/secrets/initialAdminPassword - Enter the Administrator password

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/fa2c8d86-afe5-4c24-895c-06fcb7d388d1" />



