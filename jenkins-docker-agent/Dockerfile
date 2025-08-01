FROM maven:3.9.6-eclipse-temurin-17

# Install extra tools (optional for Jenkins use)
RUN apt-get update && \
    apt-get install -y git sudo unzip python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Create Jenkins user (optional)
RUN groupadd -g 1000 jenkins && \
    useradd -m -u 1000 -g jenkins -s /bin/bash jenkins && \
    echo "jenkins ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set working directory
WORKDIR /home/jenkins/app

# Change ownership
RUN chown -R jenkins:jenkins /home/jenkins

# Switch to jenkins user
USER jenkins

# # Create the /app directory
# RUN mkdir -p /app && \
#     chown -R jenkins:jenkins /app

# # Switch to jenkins user
# USER jenkins

# # Set workdir to /app
# WORKDIR /app

# CMD ["bash"]
