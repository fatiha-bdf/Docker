# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any libraries for Python (Flask and Redis) specified in requirements.txt 
RUN pip install --trusted-host pypi.python.org -r requirements.txt
##requirements.txt is present because of that Dockerfile’s COPY command

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]

##source https://docs.docker.com/get-started/part2/


## docker build --tag=my_python .

## docker run -p 4000:80 my_python

# check http://localhost:4000