FROM osgeo/gdal:ubuntu-small-3.6.3

# Install necessary packages
RUN apt-get update && \
    apt-get install -y python3 python3-pip gdal-bin python3-gdal libgl1-mesa-glx libglib2.0-0 libsm6 libxext6 libxrender-dev libgl1-mesa-dev libgtk2.0-dev libcanberra-gtk-module

# Install Python packages
RUN pip install flask pandas requests scipy opencv-python-headless torch ultralytics matplotlib pillow werkzeug pybase64 jsons talisman numpy opencv-python psycopg2-binary flask-talisman

WORKDIR /mnt

COPY app.py /mnt/app.py

ENTRYPOINT ["python3"]
CMD ["app.py"]
