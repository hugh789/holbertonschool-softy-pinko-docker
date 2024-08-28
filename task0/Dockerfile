# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Update package lists
RUN apt-get update

# Upgrade existing packages
RUN apt-get upgrade -y

# Install required packages (e.g., bash, coreutils)
RUN apt-get install -y bash coreutils

# Define the command to be executed when the container starts
CMD echo "Hello, World!"