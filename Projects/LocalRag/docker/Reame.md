Docker Installation:
====================

FROM nvidia/cuda:11.8.0-base-ubuntu22.04

    This line starts your Docker image based on an NVIDIA CUDA image with Ubuntu 22.04. Think of it as the foundation - 
    it gives you Ubuntu with NVIDIA GPU drivers pre-installed.

RUN apt-get update && apt-get install -y python3 python3-pip


    This runs commands inside the container to:

    Update package lists (apt-get update)
    Install Python 3 and pip (apt-get install -y python3 python3-pip)
    Example: Similar to if you ran these commands on a fresh Ubuntu machine to install Python.


WORKDIR /app

    This creates a directory called /app inside the container and sets it as the working directory. All subsequent commands will run from this directory.
    Example: Similar to running mkdir -p /app && cd /app in Linux.



COPY . /app/


    This copies all files from your build context (the directory where you run docker build) into the /app directory in the container.
    Example: If you run docker build from C:\workspace\original-rag-master, all files in that folder (like app.py, requirements.txt, etc.)
    get copied to /app inside the container.

RUN pip3 install -r requirements.txt

    This installs Python packages listed in your requirements.txt file.
    Example: If your requirements.txt contains tensorflow==2.9.0, this would be like running pip3 install tensorflow==2.9.0 inside the container.


ENV CUDA_VISIBLE_DEVICES=0

    This sets an environment variable to tell the application which GPU(s) to use.
    Example: Similar to running export CUDA_VISIBLE_DEVICES=0 in Linux, which makes only the first GPU visible to your application.

CMD ["python3", "app.py"]

    This specifies the command that runs when the container starts. It will execute python3 app.py in the /app directory.
    Example: Similar to running python3 app.py in the terminal when you're in the project directory.
    Now for a concrete end-to-end example of using this Dockerfile:
    
    You have your project at C:\workspace\original-rag-master containing:
    
    app.py (your main application)
    requirements.txt (list of Python packages)
    some data files
    
    
    You save the Dockerfile in C:\workspace\original-rag-master
    Open command prompt and run:

cd C:\workspace\original-rag-master
docker build -t rag-app .


    Docker will:
    
    Download the nvidia/cuda base image
    Install Python and pip
    Create /app directory
    Copy all your files from C:\workspace\original-rag-master to /app
    Install your Python requirements
    Set up the environment variable
    Configure the container to run app.py when started

docker run --gpus all rag-app

  
  Docker creates a container from your image and runs your Python application with GPU support.
