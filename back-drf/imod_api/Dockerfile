# Use an official Python runtime as a parent image
FROM python:3.11

# Set environment variables
ENV PYTHONUNBUFFERED=1   

# Set the working directory in the container
WORKDIR /app

# Copy requirements file and install dependencies
COPY requirements.txt requirements.txt

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy the project files into the container
COPY . .

# Expose the application's port
EXPOSE 8000

# Set the command to run the application
CMD ["gunicorn", "imod_api.wsgi:application", "--bind", "0.0.0.0:8000"]
