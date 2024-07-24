FROM osgeo/gdal:ubuntu-small-3.6.3

# Install required dependencies in one layer to reduce image size and improve build speed
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository universe && \
    apt-get update && \
    apt-get install -y \
    python3 \
    gdal-bin python3-gdal \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libsm6 libxext6 libxrender-dev \
    libgl1-mesa-dev \
    libgtk2.0-dev libcanberra-gtk-module \
    python3-pip && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

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

# Set the working directory
WORKDIR /mnt

# Copy the application file into the container
COPY app.py /mnt/app.py

# Set the entry point to run the Flask application
ENTRYPOINT ["python3"]
CMD ["app.py"]