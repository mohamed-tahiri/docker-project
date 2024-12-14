FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy requirements and application files
COPY requirements.txt .
COPY devops/ ./devops/

# Update system, install Python dependencies, and create a virtual environment
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r requirements.txt && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Activate virtual environment and set the default command to run the Django server
ENV PATH="/app/venv/bin:$PATH"
ENTRYPOINT ["python3"]
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]

