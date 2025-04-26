# Dockerfile
FROM python:3.7

ENV PORT=8080
ENV HOST=0.0.0.0

EXPOSE 8080

# system deps + upgrade pip
RUN apt-get update -y && \
    apt-get install -y python3-pip build-essential && \
    pip install --upgrade pip

WORKDIR /app

# copy & install Python deps
COPY requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# copy notebook (and any other scripts/assets)
COPY . /app

# serve the notebook as a web app
ENTRYPOINT ["voila", "--port", "8080", "--no-browser", "--ip", "0.0.0.0", "GitHub_Repos_Issues_Forecasting.ipynb"]
