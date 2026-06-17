# 🚗 Vehicle Insurance Data Pipeline

> An end-to-end **MLOps** project demonstrating production-ready machine learning infrastructure with a complete data pipeline, predictive modeling, and web-based deployment.

![Python](https://img.shields.io/badge/Python-3.10+-3776ab?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.110.0-009688?logo=fastapi&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS%20S3-Cloud%20Storage-FF9900?logo=amazon-aws&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?logo=mongodb&logoColor=white)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [API Endpoints](#api-endpoints)
- [MLOps Workflow](#mlops-workflow)
- [Docker Deployment](#docker-deployment)
- [Contributing](#contributing)

---

## 🎯 Overview

The **Vehicle Insurance Data Pipeline** is a comprehensive MLOps project that predicts customer willingness to purchase vehicle insurance. It combines data engineering, machine learning, and software engineering best practices to create a production-ready system.

### Problem Statement
Given customer and vehicle data, predict the likelihood of a customer responding positively to vehicle insurance offers. This enables targeted marketing campaigns and optimized resource allocation.

### Solution Approach
- **Data Pipeline**: Automated ETL with MongoDB integration
- **ML Model**: Trained classification model with scikit-learn
- **Prediction Engine**: Real-time inference API with FastAPI
- **Web Interface**: User-friendly form-based prediction dashboard
- **Cloud Integration**: AWS S3 for model storage and versioning
- **Containerization**: Docker for consistent deployment

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    DATA SOURCE                          │
│            (CSV → MongoDB → S3 Bucket)                  │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              DATA PROCESSING PIPELINE                   │
│  • Data Validation     • Feature Engineering            │
│  • Preprocessing       • Handling Missing Values        │
│  • Scaling & Encoding  • Class Imbalance (SMOTE)       │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│            MACHINE LEARNING TRAINING                    │
│  • Model Selection (Classification)                     │
│  • Hyperparameter Tuning                                │
│  • Cross-Validation & Metrics Evaluation                │
│  • Model Serialization & Versioning (S3)                │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│         PREDICTION & INFERENCE ENGINE                   │
│  • Real-time Model Loading                              │
│  • Input Validation & Transformation                    │
│  • Prediction Generation                                │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│            FASTAPI WEB APPLICATION                      │
│  • Interactive Web Interface (HTML/Jinja2)              │
│  • RESTful API Endpoints                                │
│  • CORS-enabled for Integration                         │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│            DOCKER CONTAINER DEPLOYMENT                  │
│  • Consistent Environment                               │
│  • Easy Scaling & Orchestration                         │
└─────────────────────────────────────────────────────────┘
```

---

## ✨ Key Features

### 1. **Complete Data Pipeline**
- Automated data ingestion from multiple sources
- MongoDB integration for data persistence
- AWS S3 connectivity for model and data artifacts
- Comprehensive data validation and quality checks

### 2. **Advanced ML Workflow**
- Multi-stage data preprocessing with handling for:
  - Missing values
  - Categorical encoding
  - Feature scaling (StandardScaler)
  - Class imbalance (SMOTE - Synthetic Minority Over-sampling)
- Robust model evaluation with multiple metrics
- Version control for models and datasets

### 3. **Production-Ready API**
- FastAPI framework for high-performance async operations
- Structured input validation with Pydantic models
- CORS middleware for cross-origin requests
- Error handling and logging
- Static file serving and HTML templating

### 4. **User-Friendly Interface**
- Interactive web form for data input
- Real-time prediction results
- Responsive design with custom CSS
- Form validation on client and server side

### 5. **Cloud Integration**
- AWS S3 for model persistence and artifact storage
- Boto3 integration for seamless AWS operations
- Environment configuration management

### 6. **Containerization**
- Dockerfile for consistent deployment
- Optimized Python 3.10 slim image
- Easy deployment to cloud platforms

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Backend Framework** | FastAPI 0.110.0, Starlette 0.36.3, Uvicorn |
| **ML/Data Processing** | scikit-learn, pandas, numpy |
| **Data Storage** | MongoDB, AWS S3 |
| **Data Visualization** | matplotlib, plotly, seaborn |
| **Utilities** | PyYAML, dill, certifi |
| **Templating** | Jinja2 |
| **Containerization** | Docker |
| **Programming Language** | Python 3.10+ |
| **Environment** | Jupyter Notebook (83%), Python (16.3%) |

---

## 📁 Project Structure

```
Vehicle-Insurance-Data-Pipeline/
│
├── 📓 notebook/                          # Jupyter notebooks for EDA & experimentation
│
├── 🔧 src/                              # Source code directory
│   ├── constants.py                     # Configuration constants
│   ├── pipline/
│   │   ├── training_pipeline.py         # End-to-end training workflow
│   │   ├── prediction_pipeline.py       # Inference engine
│   │   └── ...
│   ├── components/
│   │   ├── data_ingestion.py            # Data loading & preprocessing
│   │   ├── data_validation.py           # Quality checks
│   │   ├── data_transformation.py       # Feature engineering
│   │   ├── model_trainer.py             # Model training logic
│   │   └── model_evaluation.py          # Metrics & evaluation
│   ├── exception.py                     # Custom exception handling
│   ├── logger.py                        # Logging configuration
│   └── utils.py                         # Helper utilities
│
├── 🎨 templates/                        # HTML templates
│   └── vehicledata.html                 # Prediction form interface
│
├── 🖼️  static/                           # CSS, JavaScript, static assets
│   └── style.css                        # Custom styling
│
├── 📄 config/                           # Configuration files
│
├── 🐳 Dockerfile                        # Docker container definition
├── 🔒 .dockerignore                     # Docker ignore patterns
├── 📦 requirements.txt                  # Python dependencies
├── ⚙️  setup.py                          # Package setup configuration
├── 📋 pyproject.toml                    # Project metadata
│
├── 🚀 app.py                            # Main FastAPI application
├── 🎬 demo.py                           # Demo script
├── 📝 template.py                       # Project template structure
│
├── .gitignore                           # Git ignore patterns
└── .github/                             # GitHub workflows & CI/CD

```

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.10 or higher
- Docker (optional, for containerized deployment)
- Git

### Local Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/hetrank/Vehicle-Insurance-Data-Pipeline.git
   cd Vehicle-Insurance-Data-Pipeline
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   # Create .env file with your configuration
   MONGO_DB_URL=your_mongodb_connection_string
   AWS_ACCESS_KEY_ID=your_aws_access_key
   AWS_SECRET_ACCESS_KEY=your_aws_secret_key
   S3_BUCKET_NAME=your_s3_bucket_name
   ```

5. **Run the application**
   ```bash
   python app.py
   ```
   The application will start at `http://localhost:5000`

---

## 📖 Usage Guide

### Web Interface

1. Navigate to `http://localhost:5000/` in your browser
2. Fill in the vehicle data form with the following fields:
   - **Gender**: Customer gender
   - **Age**: Customer age
   - **Driving License**: Whether customer has driving license
   - **Region Code**: Geographic region code
   - **Previously Insured**: Previous insurance status
   - **Annual Premium**: Customer's annual premium
   - **Policy Sales Channel**: Sales channel used
   - **Vintage**: Customer tenure in days
   - **Vehicle Age**: Vehicle age categories
   - **Vehicle Damage**: Vehicle damage history

3. Submit the form to receive prediction results
   - **Response-Yes**: Customer likely to purchase insurance
   - **Response-No**: Customer unlikely to purchase insurance

### Python Integration

```python
from src.pipline.prediction_pipeline import VehicleData, VehicleDataClassifier

# Create vehicle data object
vehicle_data = VehicleData(
    Gender=1,
    Age=35,
    Driving_License=1,
    Region_Code=28.0,
    Previously_Insured=0,
    Annual_Premium=45000.0,
    Policy_Sales_Channel=152.0,
    Vintage=180,
    Vehicle_Age_lt_1_Year=0,
    Vehicle_Age_gt_2_Years=1,
    Vehicle_Damage_Yes=1
)

# Get prediction
df = vehicle_data.get_vehicle_input_data_frame()
predictor = VehicleDataClassifier()
prediction = predictor.predict(dataframe=df)[0]

print(f"Prediction: {'Response-Yes' if prediction == 1 else 'Response-No'}")
```

---

## 🔌 API Endpoints

### Root Endpoint

**GET** `/`
- Returns the prediction form interface
- Response: HTML page with interactive form

**POST** `/`
- Submits vehicle data and receives prediction
- Request Body: Form data from HTML form
- Response: JSON with prediction result or error message

### Example API Call

```bash
curl -X POST http://localhost:5000/ \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "Gender=1&Age=35&Driving_License=1&Region_Code=28&Previously_Insured=0&Annual_Premium=45000&Policy_Sales_Channel=152&Vintage=180&Vehicle_Age_lt_1_Year=0&Vehicle_Age_gt_2_Years=1&Vehicle_Damage_Yes=1"
```

---

## 🤖 MLOps Workflow

### Training Pipeline (`src/pipline/training_pipeline.py`)

```python
from src.pipline.training_pipeline import TrainPipeline

# Execute complete training workflow
train_pipeline = TrainPipeline()
train_pipeline.run_pipeline()
```

**Pipeline Steps:**
1. **Data Ingestion**: Load data from source
2. **Data Validation**: Verify data quality and schema
3. **Data Transformation**: 
   - Handle missing values
   - Encode categorical variables
   - Scale numerical features
   - Apply SMOTE for class imbalance
4. **Model Training**: Train classification model
5. **Model Evaluation**: 
   - Calculate accuracy, precision, recall, F1-score
   - Generate performance reports
6. **Model Serialization**: Save trained model to S3

### Prediction Pipeline (`src/pipline/prediction_pipeline.py`)

```python
from src.pipline.prediction_pipeline import VehicleDataClassifier

# Load model and make predictions
classifier = VehicleDataClassifier()
predictions = classifier.predict(dataframe=input_df)
```

**Pipeline Steps:**
1. Load preprocessor from artifact
2. Transform input data using fitted preprocessor
3. Load trained model from S3
4. Generate predictions
5. Return formatted results

---

## 🐳 Docker Deployment

### Build Docker Image

```bash
docker build -t vehicle-insurance-pipeline:latest .
```

### Run Container

```bash
docker run -p 5000:5000 vehicle-insurance-pipeline:latest
```

### Docker Compose (Optional)

```yaml
version: '3.8'
services:
  app:
    build: .
    ports:
      - "5000:5000"
    environment:
      - MONGO_DB_URL=${MONGO_DB_URL}
      - AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}
      - AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}
    volumes:
      - .:/app
```

Run with: `docker-compose up`

---

## 📊 Performance Metrics

The model is evaluated using standard classification metrics:

- **Accuracy**: Overall correctness
- **Precision**: True positives / predicted positives
- **Recall**: True positives / actual positives
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve

---

## 🔐 Error Handling & Logging

The project includes comprehensive error handling:

- **Custom Exceptions**: Specific error types for different scenarios
- **Logging**: Detailed logs for debugging and monitoring
- **Validation**: Input validation at API and model levels
- **Exception Middleware**: Graceful error responses

---

## 🧪 Testing

To validate the pipeline:

```python
# Test prediction with sample data
python demo.py
```

---

## 🚀 Deployment Strategies

### Local Development
```bash
python app.py
```

### Production with Gunicorn
```bash
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

### Cloud Deployment
- **AWS EC2**: Deploy containerized application
- **AWS ECS**: Container orchestration
- **Heroku**: Simple PaaS deployment
- **Google Cloud Run**: Serverless deployment

---

## 📚 Project Highlights

✅ **End-to-End MLOps Implementation**
- Complete pipeline from data to production prediction

✅ **Production-Ready Code**
- Error handling, logging, and validation throughout

✅ **Scalable Architecture**
- Modular design for easy extension and maintenance

✅ **Cloud Integration**
- AWS S3 for artifact storage and versioning

✅ **Modern API Framework**
- FastAPI for high-performance async operations

✅ **User-Friendly Interface**
- Interactive web form for non-technical users

✅ **Containerization**
- Docker support for consistent deployment

✅ **Best Practices**
- Configuration management, logging, exception handling

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

---

## 👤 Author

**Het Rank**
- 📧 Email: hetrank08@gmail.com
- 🐙 GitHub: [@hetrank](https://github.com/hetrank)

---

## 🙏 Acknowledgments

- scikit-learn for ML algorithms
- FastAPI for the web framework
- AWS for cloud services
- MongoDB for database solutions
- Open-source community for tools and libraries

---

## 📞 Support

For issues, questions, or suggestions, please:
- 🐛 Open an [Issue](https://github.com/hetrank/Vehicle-Insurance-Data-Pipeline/issues)
- 💬 Start a [Discussion](https://github.com/hetrank/Vehicle-Insurance-Data-Pipeline/discussions)
- 📧 Email the maintainer

---

<div align="center">

**Made with ❤️ by Het Rank**

⭐ If you found this helpful, please consider giving it a star!

</div>
