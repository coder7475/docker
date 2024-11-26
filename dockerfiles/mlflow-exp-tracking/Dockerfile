FROM python:3.8-slim-buster

# Setting up work directory
WORKDIR /app/

# Install system dependencies
RUN apt-get update && apt-get install -y \
    gcc \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Install python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the training script
COPY train_model.py .

# Set up MLflow
ENV MLFLOW_TRACKING_URI=/mlflow 

# Create a start up script
RUN echo '#!/bin/bash\n\
mlflow server --host 0.0.0.0 --port 5000 --backend-store-uri /mlflow_data &\n\
sleep 5\n\
python train_model.py\n\
wait' > /app/start.sh && chmod +x /app/start.sh

# Run the startup script
CMD ["/app/start.sh"]