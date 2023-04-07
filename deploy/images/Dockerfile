FROM python:3.8-slim-buster

# Install required packages
RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /app

# Copy the application code to the container
COPY ../../src .

# Install the dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Set the environment variable to run Flask
ENV FLASK_APP=app.py

# Expose port 5000 for the Flask server
EXPOSE 5000

# Run the Flask application
CMD ["flask", "run", "--host", "0.0.0.0", "--port", "5000"]

