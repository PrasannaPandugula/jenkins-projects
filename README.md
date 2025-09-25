Install Jenkins, configure Docker as agent, set up cicd, deploy applications to k8s and much more.

AWS EC2 Instance

  1. Go to AWS Console
  2. Instances(running)
  3. Launch instances

<img width="1000" height="800" alt="image" src="https://github.com/user-attachments/assets/e3e433b8-13ac-43a3-9bf4-69e79b6dceba" />

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
    




