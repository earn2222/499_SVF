FROM osgeo/gdal:ubuntu-small-3.6.3

# Install system dependencies
RUN apt-get update && \
    apt-get install -y \
    python3 \
    gdal-bin \
    python3-gdal \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender-dev \
    libgl1-mesa-dev \
    libgtk2.0-dev \
    libcanberra-gtk-module \
    python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Copy requirements file and install Python dependencies
COPY requirements.txt /mnt/requirements.txt
RUN pip install --no-cache-dir -r /mnt/requirements.txt

# Set working directory
WORKDIR /mnt

# Copy application code
COPY app.py /mnt/app.py


