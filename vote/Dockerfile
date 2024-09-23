FROM python:3.11-slim AS base

RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/app

COPY . .

COPY requirements.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

RUN pip install watchdog
ENV FLASK_ENV=development
CMD ["python", "app.py"]