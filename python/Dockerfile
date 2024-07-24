FROM osgeo/gdal:ubuntu-small-3.6.3

# Install system dependencies and python3 with pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip gdal-bin python3-gdal libgl1-mesa-glx \
    libglib2.0-0 libsm6 libxext6 libxrender-dev libgl1-mesa-dev \
    libgtk2.0-dev libcanberra-gtk-module && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the default Python and Pip to Python 3 versions
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 1

# Install Python packages
RUN pip install --no-cache-dir \
    flask pandas requests scipy opencv-python-headless torch ultralytics \
    matplotlib pillow werkzeug pybase64 jsons talisman numpy \
    opencv-python psycopg2-binary flask-talisman

WORKDIR /mnt

COPY app.py /mnt/app.py

ENTRYPOINT ["python"]
CMD ["app.py"]
