# MLOps Heart Attack Detection

This repository provides a complete MLOps solution for heart attack detection using machine learning. The project showcases a robust end-to-end MLOps pipeline with various integrated tools for model development, tracking, monitoring, and deployment.

![MLOps Pipeline](https://via.placeholder.com/800x400?text=Heart+Attack+Detection+MLOps+Pipeline)

## Project Overview

This system demonstrates a production-grade machine learning pipeline for predicting heart attack risk using clinical data. The solution implements MLOps best practices including:

- Automated data ingestion and preprocessing
- Feature engineering and selection
- Reproducible model training
- Experiment tracking and model versioning
- Containerized deployment
- Performance monitoring and alerting

## Features

- **Data Pipeline**: Automated ETL processes for handling heart disease datasets
- **Model Training**: Machine learning pipeline for heart attack prediction
- **Experiment Tracking**: MLflow integration for tracking experiments and models
- **Model Registry**: Version control and management of ML models
- **Model Serving**: API endpoints for real-time predictions
- **Monitoring**: Grafana dashboards for model and system performance monitoring
- **Data Version Control**: Track changes to datasets over time
- **Containerization**: Docker-based deployment for consistency across environments

## Architecture

The system architecture includes the following components:

1. **Data Layer**: PostgreSQL database for storing heart disease datasets
2. **Storage Layer**: MinIO object storage for datasets and model artifacts
3. **Training Layer**: Jupyter notebooks for model development and experimentation
4. **Tracking Layer**: MLflow for experiment tracking and model registry
5. **Serving Layer**: FastAPI endpoints for real-time predictions
6. **Monitoring Layer**: Grafana dashboards for system and model performance visualization

## Quick Start

### Prerequisites
- Docker and Docker Compose installed on your system
- Git

### Installation & Setup

```bash
# Clone the repository
git clone https://github.com/naufalsutrisna/MLOPs-Heart-Attack-Detection.git

# Navigate to the project directory
cd MLOPs-Heart-Attack-Detection

# Build and start the Docker containers
docker-compose build
docker-compose up
```

## Initial Configuration

After starting the containers, you need to perform these initial setup steps:

### 1. Create MinIO Bucket
- Access MinIO at [http://localhost:9000](http://localhost:9000)
- Login with username: `mlflow` and password: `password`
- Create a new bucket named `mlflow`

### 2. Configure Database Connection
- The database will be automatically initialized with the required schema
- No manual configuration is needed as the system will handle this automatically

## Accessing Services

After running the containers, you can access the following services:

### Jupyter Notebook
- URL: [http://127.0.0.1:8888/lab](http://127.0.0.1:8888/lab)
- Password: `mlflow`

### MLflow
- URL: [http://localhost:5001/](http://localhost:5001/)
- Username: `mlflow`
- Password: `password`

### MinIO (Object Storage)
- URL: [http://localhost:9000](http://localhost:9000)
- Username: `mlflow`
- Password: `password`

### Grafana (Monitoring & Dashboards)
- URL: [http://localhost:3000](http://localhost:3000)
- Username: `admin`
- Password: `admin` or `mlflow`

#### Grafana Configuration
To set up Grafana with the PostgreSQL data source:
1. Navigate to Configuration > Data Sources
2. Add a new PostgreSQL data source with these settings:
   - **Host**: `pgsql:5432` *(Docker internal hostname and port)*
   - **Database**: `mlflow`
   - **User**: `mlflow`
   - **Password**: `secret`
   - **SSL Mode**: Disable
