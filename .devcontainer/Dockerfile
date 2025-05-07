# .devcontainer/Dockerfile
FROM nvidia/cuda:12.1.1-cudnn8-runtime-ubuntu22.04

# Basic OS deps
RUN apt-get update && \
    apt-get install -y git curl build-essential && \
    rm -rf /var/lib/apt/lists/*

# Python + ML stack
RUN apt-get update && \
    apt-get install -y python3.10 python3-pip && \
    pip3 install --upgrade pip

# Copy dependency list (create this next)
COPY requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

ENV PYTHONUNBUFFERED=1
WORKDIR /workspace
