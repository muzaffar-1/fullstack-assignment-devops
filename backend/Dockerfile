# 1. Use a slim version of Python to save space on your 12GB disk
FROM python:3.11-slim

# 2. Set environment variables to keep Python clean and fast
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# 3. Set the working directory inside the container
WORKDIR /app

# 4. Install system dependencies (needed for some Python packages)
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# 5. Copy ONLY the dependencies first to use Docker caching
COPY dependencies.txt .

# 6. Install Python packages
RUN pip install --no-cache-dir -r dependencies.txt

# 7. Copy the rest of the backend code
COPY . .

# 8. Expose the port Django/Uvicorn will run on
EXPOSE 8000

# 9. Start the server (Using the server.py we found earlier)
CMD ["python", "server.py"]
