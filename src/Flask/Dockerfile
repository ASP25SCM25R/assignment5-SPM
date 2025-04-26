FROM python:3.10-slim

ENV PORT=8080 \
    HOST=0.0.0.0

EXPOSE 8080

# install build tools (if you compile any C extensions) and upgrade pip
RUN apt-get update -y && \
    apt-get install -y build-essential && \
    pip install --upgrade pip

WORKDIR /app

# install Python deps
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# copy your Flask app
COPY . .

# run it!
ENTRYPOINT ["python", "app.py"]
