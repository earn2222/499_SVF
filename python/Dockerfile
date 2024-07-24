FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:ubuntugis/ubuntugis-unstable && \
    apt-get update && \
    apt-get install -y gdal-bin libgdal-dev

# ติดตั้ง Python packages
RUN pip3 install --no-cache-dir \
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
