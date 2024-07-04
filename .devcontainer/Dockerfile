# Use a base image with Ubuntu
FROM ubuntu:latest

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && \
    apt-get install -y \
        curl \
        unzip \
        wget \
        apt-transport-https \
        ca-certificates \
        software-properties-common \
        gnupg \
        lsb-release \
        python3 \
        python3-pip \
        python3-venv  # Install Python virtual environment package

# Install kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" && \
    chmod +x kubectl && \
    mv kubectl /usr/local/bin/kubectl

# Install Terraform
RUN wget -q "https://releases.hashicorp.com/terraform/1.0.0/terraform_1.0.0_linux_amd64.zip" -O /tmp/terraform.zip && \
    unzip -o /tmp/terraform.zip -d /usr/local/bin/ && \
    rm /tmp/terraform.zip

# Set up Python environment with virtual environment
RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Upgrade pip inside the virtual environment
RUN /opt/venv/bin/python -m pip install --upgrade pip

# Set the working directory
WORKDIR /workspace

# Default command to run when the container starts
CMD ["bash"]
