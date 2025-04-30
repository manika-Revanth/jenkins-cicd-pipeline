# Use the official Maven image as the base
FROM maven:3.8.5-openjdk-17-slim

# Set environment variables for Maven
ENV MAVEN_HOME /usr/share/maven
ENV PATH $MAVEN_HOME/bin:$PATH

# Switch to root to install dependencies
USER root

# Install Docker CLI and other useful tools
RUN apt-get update && apt-get install -y \
    git \
    curl \
    vim \
    docker.io \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /workspace

# Add the Jenkins agent user (if not already)
RUN groupadd -r jenkins && useradd -r -g jenkins jenkins

# (Optional) Switch back to non-root user
USER jenkins

# Entry point
CMD ["tail", "-f", "/dev/null"]
