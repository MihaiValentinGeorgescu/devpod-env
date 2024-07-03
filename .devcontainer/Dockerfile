# Use an official Python image from the Docker Hub as a base image
FROM python:3.9

# Install Git
RUN apt-get update && apt-get install -y git

# Set the working directory
WORKDIR /workspace

# Copy the current directory contents into the container at /workspace
COPY . /workspace

# Install Python dependencies if any (optional)
# RUN pip install -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Run a command (optional, here we just start a shell)
CMD ["bash"]
