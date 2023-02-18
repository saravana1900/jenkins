# jenkins

### Setup Jenkins Using Docker With a Host Mount (Linux)

1. Create a home directory for Jenkins in the host.
 ```sudo mkdir /opt/jenkins_home ```

2. Make jenkins container user as the owner of the jenkins_home directory using its UUID.
 ``` sudo chown -R 1000:1000 /opt/jenkins_home```
3. Run the latest jenkins container using the following command.
 ``` docker run  -d --name jenkins -p 8080:8080 -p 50000:50000 -v /opt/jenkins_home:/var/jenkins_home jenkins/jenkins ```
4. Execute the following command and copy the Initial Admin password
   ```docker exec -it jenkins sh -c "cat /var/jenkins_home/secrets/initialAdminPassword" ```
5. Launch http://localhost:8080/ in your browser.
6. Login with the password obtained in above previous step.
7. proceed with installing the pluggins and setup users.



 docker volume create jenkins
 docker run --name jenkins -it jenkins

 docker run -p 9090:8080 -p 50000:50000 -v jenkins:/var/jenkins_home jenkins/jenkins:lts-jdk11

