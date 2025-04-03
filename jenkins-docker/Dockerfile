# Use the official Jenkins LTS image as the base
FROM jenkins/jenkins:lts

# Switch to root user to install Docker
USER root

# Install Docker
RUN apt-get update && \
    apt-get install -y docker.io && \
    apt-get clean

# Add Jenkins user to the Docker group (check if the group exists first)
RUN getent group docker || groupadd -g 999 docker && \
    usermod -aG docker jenkins

# Switch back to the Jenkins user
USER jenkins
