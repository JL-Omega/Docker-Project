# Use the Python 3.8 image based on Debian Buster
FROM python:3.8-buster

# Set maintainer information
LABEL MAINTAINER="Jean-Luc Mpande - mpandejl1@gmail.com"

# Set working directory inside the container
WORKDIR /app

# Add the Python script to the working directory
ADD student_age.py /app/

# Copy the requirements file into the working directory
COPY requirements.txt /app/

# Define a volume for persistent data storage
VOLUME [ "/data" ]

# Update package list and install necessary dependencies
RUN apt update -y && \
    apt install -y \
        python-dev \
        python3-dev \
        libsasl2-dev \
        libldap2-dev \
        libssl-dev && \
    pip3 install -r /app/requirements.txt 

# Expose port 5000 for the application
EXPOSE 5000

# Command to run the application
CMD [ "python", "./student_age.py" ]
