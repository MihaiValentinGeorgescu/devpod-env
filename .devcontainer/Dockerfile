# Use an official Python image from the Docker Hub as a base image
FROM python:3.9

# Install Git and sudo
RUN apt-get update && apt-get install -y git sudo

# Create a user called vscode with a home directory
RUN useradd -ms /bin/bash vscode \
    && echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/nopasswd \
    && chmod 0440 /etc/sudoers.d/nopasswd

# Set the working directory
WORKDIR /workspace

# Copy the current directory contents into the container at /workspace
COPY . /workspace

# Make port 80 available to the world outside this container
EXPOSE 80

# Set user to vscode
USER vscode

# Run a command (optional, here we just start a shell)
CMD ["bash"]
