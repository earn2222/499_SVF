FROM osgeo/gdal:ubuntu-small-3.6.3

# ติดตั้งแพ็กเกจที่ระบบต้องการ
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
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
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# คัดลอกไฟล์ requirements และติดตั้งแพ็กเกจ Python
COPY requirements.txt /mnt/requirements.txt
RUN pip install --no-cache-dir -r /mnt/requirements.txt

# กำหนดไดเรกทอรีการทำงาน
WORKDIR /mnt

# คัดลอกโค้ดของแอปพลิเคชัน
COPY app.py /mnt/app.py

# กำหนดคำสั่งเริ่มต้นเมื่อเริ่มคอนเทนเนอร์
CMD ["python3", "/mnt/app.py"]
