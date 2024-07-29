FROM continuumio/miniconda3

# Install system dependencies
RUN apt-get update && \
    apt-get install -y \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender-dev \
    libgl1-mesa-dev \
    libgtk2.0-dev \
    libcanberra-gtk-module && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Create a Conda environment and install Python and GDAL
RUN conda create -n myenv python=3.8 gdal

# Activate the environment
SHELL ["conda", "run", "-n", "myenv", "/bin/bash", "-c"]

# Copy requirements file and install Python dependencies
COPY requirements.txt /mnt/requirements.txt
RUN pip install --no-cache-dir -r /mnt/requirements.txt

# Set working directory
WORKDIR /mnt

# Copy application code
COPY app.py /mnt/app.py

# Set the default command to run when starting the container
CMD ["conda", "run", "-n", "myenv", "python", "/mnt/app.py"]
