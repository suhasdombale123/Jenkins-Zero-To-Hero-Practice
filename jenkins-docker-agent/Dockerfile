FROM maven:3.9.6-eclipse-temurin-17-alpine

# Install dependencies with Alpine's package manager
RUN apk add --no-cache \
    git \
    curl \
    bash \
    sudo \
    unzip \
    shadow  # for useradd and groupadd

RUN apk add --no-cache docker-cli

# Create Jenkins user
RUN groupadd -g 119 jenkins && \
    useradd -m -u 114 -g jenkins -s /bin/bash jenkins && \
    echo "jenkins ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set working directory
USER jenkins
WORKDIR /home/jenkins/app

CMD ["bash"]
