# Use an official Python runtime as a parent image
FROM python:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app


COPY clouds.yml /app/clouds.yml

RUN apt-get update && apt-get install -y git
# Install any needed packages specified in requirements.txt
RUN pip install openstacksdk tqdm pyquery
#RUN pip install --trusted-host pypi.python.org pyquery tqdm 

# Install otcextensions from GitHub
RUN pip install git+https://github.com/dantepawn/python-otcextensions/#egg=otcextensions

RUN git clone https://github.com/PanosAI/html2json.git


# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python3", "./html2json/node_html2json.py"]

# Use a Python base image
# Set working directory