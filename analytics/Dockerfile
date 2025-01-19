FROM python:3.12-slim

USER root 

# Update the local package index with the latest packages from the repositories
RUN apt update -y

# Install a couple of packages to successfully install postgresql server locally
RUN apt install -y build-essential libpq-dev

# Update python modules to successfully build the required modules
RUN pip install --upgrade pip setuptools wheel

WORKDIR src

# Copy requirements
COPY requirements.txt .

# Instal modules required by the aplication
RUN pip install -r requirements.txt

# Copy application
COPY . .

CMD python app.py
