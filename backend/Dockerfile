# Use an official Python runtime as a parent image
FROM python:3.9-slim    

# Set the working directory in the container to /app
WORKDIR /app

# Copy the current directory contents into the container
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container
COPY . .

# Expose port 5000 for the backend service
EXPOSE 5000

# Define the command to run the application using Gunicorn
RUN pip install gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app.main:app"]
