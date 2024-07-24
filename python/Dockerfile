FROM osgeo/gdal:ubuntu-small-3.6.3

# Update package list
RUN apt-get update

# Install essential packages in steps to identify the problematic one
RUN apt-get install -y python3 python3-pip
RUN apt-get install -y gdal-bin python3-gdal
RUN apt-get install -y libgl1-mesa-glx libglib2.0-0
RUN apt-get install -y libsm6 libxext6 libxrender-dev
RUN apt-get install -y libgl1-mesa-dev libgtk2.0-dev libcanberra-gtk-module

# Clean up package lists
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

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

WORKDIR /mnt

COPY app.py /mnt/app.py

ENTRYPOINT ["python3"]
CMD ["app.py"]
