FROM osgeo/gdal:ubuntu-small-3.6.3
# Install python3 
RUN apt-get update && apt-get install -y python3
# RUN apt-get update && apt-get install -y gdal-bin python3-gdal
RUN apt-get update && apt-get install -y libgl1-mesa-glx
RUN apt-get update && apt-get install -y libglib2.0-0
RUN apt-get update && apt-get install -y libsm6 libxext6 libxrender-dev
RUN apt-get update && apt-get install -y libgl1-mesa-dev
RUN apt-get update && apt-get install -y libgtk2.0-dev libcanberra-gtk-module
# RUN apt-get update && apt-get install libpq-dev 
# RUN apt update && apt-get install -y apt-get clean
RUN apt-get update && apt-get install python3-pip -y
RUN pip install flask
RUN pip install pandas
RUN pip install requests
RUN pip install scipy
RUN pip install opencv-python-headless
RUN pip install torch
RUN pip install ultralytics
RUN pip install matplotlib
RUN pip install pillow
RUN pip install werkzeug
RUN pip install pybase64
RUN pip install jsons
RUN pip install talisman
RUN pip install numpy
RUN pip install opencv-python
# RUN pip install psycopg2
RUN pip install psycopg2-binary
RUN pip install flask-talisman




WORKDIR /mnt

COPY app.py /mnt/app.py

ENTRYPOINT ["python3"]
CMD ["app.py"]