FROM python:3.8-slim
WORKDIR /app

RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install thriftpy2==0.4.16
RUN pip install -r requirements.txt

COPY . .
CMD ["python", "processor.py"]
EXPOSE 6379