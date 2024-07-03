# Use an official Python image from the Docker Hub as a base image
FROM python:3.9

# Install Git and sudo
RUN apt-get update \
    && apt-get install -y git sudo \
    && rm -rf /var/lib/apt/lists/*

# Create a non-root user and switch to it
RUN useradd -rm -d /home/vscode -s /bin/bash -g root -G sudo -u 1001 vscode
USER vscode
WORKDIR /home/vscode

# Copy the current directory contents into the container at /home/vscode
COPY . /home/vscode

# Set the default shell to bash
SHELL ["/bin/bash", "-c"]

# Expose port 80
EXPOSE 80

# Run a command (optional, here we just start a shell)
CMD ["bash"]
