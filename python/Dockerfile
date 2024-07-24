# Use the official GDAL image as the base
FROM osgeo/gdal:ubuntu-small-3.6.3

# Update package manager and install system dependencies
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y python3 python3-pip gdal-bin python3-gdal libgl1-mesa-glx \
    libglib2.0-0 libsm6 libxext6 libxrender-dev libgl1-mesa-dev \
    libgtk2.0-dev libcanberra-gtk-module && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set Python3 and Pip3 as default
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1

# Install Python packages
RUN pip install --no-cache-dir \
    flask pandas requests scipy opencv-python-headless torch ultralytics \
    matplotlib pillow werkzeug pybase64 jsons talisman numpy \
    opencv-python psycopg2-binary flask-talisman

# Set the working directory
WORKDIR /mnt

# Copy application files
COPY app.py /mnt/app.py

# Expose the port Flask will run on
EXPOSE 5000

# Define entrypoint
ENTRYPOINT ["python"]
CMD ["app.py"]