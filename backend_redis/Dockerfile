# Step 1: Use an official Python runtime as a parent image
FROM python:3.9-slim

# Step 2: Set the working directory in the container
WORKDIR /app

# Step 3: Install system dependencies and Redis client libraries
# This installs the necessary packages for interacting with Redis and building Python packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    gcc \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Step 4: Copy the requirements file into the container
COPY requirements.txt .

# Step 5: Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Step 6: Copy the rest of the application code into the container
COPY . .

# Step 7: Expose the port your application will run on (adjust if needed)
EXPOSE 8001

# Step 8: Set environment variables (if needed)
ENV PYTHONUNBUFFERED=1

# Step 9: Define the command to run your application
# If you're using a web framework like Django or Flask, adjust accordingly.
CMD ["python", "manage.py", "runserver", "0.0.0.0:8001"]
