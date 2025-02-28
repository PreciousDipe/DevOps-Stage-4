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
EXPOSE 6379
ENV REDIS_HOST=redis \
    REDIS_PORT=6379 \
    REDIS_CHANNEL=log_channel
CMD ["python", "main.py"]
