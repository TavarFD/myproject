# Use official Python image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy requirements first for caching
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy app code
COPY app.py .

# Expose the port Flask will run on
EXPOSE 5000

# Run app with Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app", "--workers", "2", "--timeout", "120"]
