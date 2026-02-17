# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy requirements first (better caching)
COPY requirements.txt .

# Install needed packages
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app
COPY . .

# Make port 5000 available outside the container
EXPOSE 5000

# Run app.py when the container launches
CMD ["python", "app.py"]
