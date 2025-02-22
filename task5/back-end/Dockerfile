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

# Install Flask using pip, allowing installation even if conflicts exist; # Install Flask-CORS using pip for Python 3
RUN pip install --break-system-packages flask && \
    pip install --break-system-packages flask-cors

# Create a directory for the application code
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