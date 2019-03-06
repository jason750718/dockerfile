# Build Image
docker build --rm -t 192.168.5.61/jenkins-docker/jenkins .

# Run Container
docker run -d -p 8080:8080 -p 50000:50000 -p 8090:22 -v /var/run/docker.sock:/var/run/docker.sock -v /var/jenkins_home --name jenkins 192.168.5.61/jenkins-docker/jenkins

# SSH Service
1. Enter Container
docker exec -it jenkins bash

2. Start SSH Service
service ssh start

# Unlock Jenkins
1. Enter Container
docker exec -it jenkins bash
2. Print Password
cat /var/jenkins_home/secrets/initialAdminPassword