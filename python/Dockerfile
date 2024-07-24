# Use the GDAL image as a base
FROM osgeo/gdal:ubuntu-small-3.6.3

# Set the working directory
WORKDIR /mnt

# Install required system packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    software-properties-common \
    python3 \
    python3-pip \
    gdal-bin \
    python3-gdal \
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

# Install Python packages
RUN pip install --no-cache-dir \
    flask \
    pandas \
    requests \
    scipy \
    opencv-python-headless \
    torch \
    ultralytics \
    matplotlib \
    pillow \
    werkzeug \
    pybase64 \
    jsons \
    talisman \
    numpy \
    opencv-python \
    psycopg2-binary \
    flask-talisman

# Copy the application file into the container
COPY app.py /mnt/app.py

# Set the entry point to run the Flask application
ENTRYPOINT ["python3", "app.py"]
