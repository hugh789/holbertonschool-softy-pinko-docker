# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Set environment variable to avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package lists and upgrade existing packages
RUN apt-get update && \
    apt-get upgrade -y && \
    # Install Python 3 and development libraries
    apt-get install -y python3 python3-dev && \
    # Install pip for Python 3 package management
    apt-get install -y python3-pip

# Install Flask using pip, allowing installation even if conflicts exist
RUN pip install --break-system-packages flask

# Create a directory for the applicationß code
RUN mkdir -p /app

# Copy the Python script (api.py) to the application directory
COPY api.py /app/

# Change directory to the application directory
RUN cd /app && \
    # Set executable permission on the Python script
    chmod u+x api.py

# Set the working directory for the container
WORKDIR /app

# Define the command to run the Flask application
CMD python3 api.py