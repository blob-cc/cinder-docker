# syntax=docker/dockerfile:1.4


# Base Image
# =============================================================================

# FROM ubuntu:latest
FROM ubuntu:24.04

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    git \
    libgl1-mesa-dev \
    libxi-dev \
    libxrandr-dev \
    libxinerama-dev \
    libxcursor-dev \
    libssl-dev \
    libasound2-dev \
    libpulse-dev \
    libudev-dev \
    libfreetype6-dev \
    libfontconfig1-dev \
    libexpat1-dev \
    python3 \
    python3-pip

# Set up working directory
WORKDIR /workspace

# Copy the Cinder code into the container
COPY . .

# Build Cinder
RUN mkdir build && cd build && cmake .. && make -j$(nproc)

# Default command
CMD [ "sleep", "infinity" ]