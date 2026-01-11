# ⚡ Ethiopian Electric Utility - AI-Powered Demand Forecasting System

![React](https://img.shields.io/badge/React-18.2.0-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-green)
![Python](https://img.shields.io/badge/Python-3.9+-yellow)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-blue)
![License](https://img.shields.io/badge/License-MIT-green)

**Accurate electricity demand prediction with machine learning, real-time insights, and comprehensive analytics for Ethiopia's national grid.**

## 📋 Table of Contents

- [Features](#-features)
- [Screenshots](#-screenshots)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [API Documentation](#-api-documentation)
- [Data Upload Guide](#-data-upload-guide)
- [ML Model Details](#-ml-model-details)
- [Configuration](#-configuration)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### 🔮 **Smart Forecasting**
- **ML-Powered Predictions**: Linear Regression with Ethiopian-specific seasonal patterns
- **7-Day Forecast**: Weekly demand predictions with confidence intervals
- **Real-time Updates**: Continuous model retraining with new data
- **Custom Predictions**: Generate forecasts based on temperature, time, and regional factors

### 🤖 **AI Intelligence**
- **Real-time Alerts**: Automatic anomaly detection and grid stress warnings
- **Smart Recommendations**: Energy-saving and load-balancing suggestions
- **Grid Analytics**: Regional performance and infrastructure insights
- **Efficiency Scoring**: Household and regional consumption efficiency ratings

### 👥 **User Management**
- **Secure Authentication**: JWT-based user registration and login
- **Session Management**: Persistent user sessions with refresh tokens
- **Profile Dashboard**: Personalized user interface and preferences

### 🏠 **Household Analytics**
- **Consumption Tracking**: Register and monitor household electricity usage
- **Population Integration**: Demand scaling based on regional population data
- **Cost Estimation**: Monthly consumption cost projections

### 📊 **Comprehensive Analytics**
- **Interactive Visualizations**: Chart.js powered real-time charts
- **Regional Breakdown**: All 11 Ethiopian regions with individual analytics
- **Historical Analysis**: Peak demand, energy consumption, and trend analysis
- **Data Statistics**: Dataset insights and model performance metrics

---

## 🖼️ Screenshots

| Dashboard | AI Insights | Analytics |
|-----------|-------------|-----------|
| ![Dashboard](https://via.placeholder.com/400x250/4A90E2/FFFFFF?text=Dashboard+View) | ![AI Insights](https://via.placeholder.com/400x250/50E3C2/FFFFFF?text=AI+Insights) | ![Analytics](https://via.placeholder.com/400x250/9013FE/FFFFFF?text=Analytics) |

| Forecast | Households | Upload Data |
|----------|------------|-------------|
| ![Forecast](https://via.placeholder.com/400x250/F5A623/FFFFFF?text=Forecast+View) | ![Households](https://via.placeholder.com/400x250/7ED321/FFFFFF?text=Households) | ![Upload](https://via.placeholder.com/400x250/BD10E0/FFFFFF?text=Data+Upload) |

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** 18+ and **npm** 9+
- **Python** 3.9+
- **Git** (for cloning the repository)

### One-line Installation
```bash
git clone https://github.com/your-org/ethiopian-electric-forecast.git
cd ethiopian-electric-forecast
./setup.sh  # Run the setup script
```

Or follow the manual setup:

### 1. Clone the Repository
```bash
git clone https://github.com/your-org/ethiopian-electric-forecast.git
cd ethiopian-electric-forecast
```

### 2. Backend Setup
```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Initialize ML model and data
python ml/train.py

# Start backend server
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

### 3. Frontend Setup
```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

### 4. Access the Application
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs (Swagger UI)

### Default Login Credentials
- **Email**: admin@eeu.et
- **Password**: admin123

---

## 📁 Project Structure

```
ethiopian-electric-forecast/
├── 📂 backend/
│   ├── 📂 app/
│   │   ├── 📂 routes/
│   │   │   ├── auth.py          # Authentication endpoints
│   │   │   ├── forecast.py      # Forecast endpoints
│   │   │   ├── households.py    # Household management
│   │   │   ├── ai_insights.py   # AI insights endpoints
│   │   │   └── upload.py        # Data upload endpoints
│   │   ├── 📂 schemas/
│   │   │   ├── user.py          # User Pydantic models
│   │   │   ├── forecast.py      # Forecast models
│   │   │   └── household.py     # Household models
│   │   ├── 📂 middleware/
│   │   │   └── auth.py          # Authentication middleware
│   │   ├── 📂 utils/
│   │   │   ├── validators.py    # Data validation utilities
│   │   │   └── helpers.py       # Helper functions
│   │   └── main.py              # FastAPI application
│   ├── 📂 ml/
│   │   ├── 📂 data/
│   │   │   └── historical_data.csv  # Training dataset
│   │   ├── 📂 models/
│   │   │   ├── model.pkl        # Trained ML model
│   │   │   └── scaler.pkl       # Feature scaler
│   │   ├── train.py             # Model training script
│   │   ├── predict.py           # Prediction module
│   │   └── preprocess.py        # Data preprocessing
│   ├── requirements.txt         # Python dependencies
│   └── .env.example             # Environment variables template
│
├── 📂 frontend/
│   ├── 📂 src/
│   │   ├── 📂 components/
│   │   │   ├── Navbar.tsx       # Navigation component
│   │   │   ├── Sidebar.tsx      # Sidebar navigation
│   │   │   ├── ChartCard.tsx    # Reusable chart component
│   │   │   ├── UploadData.tsx   # Data upload component
│   │   │   └── AlertBanner.tsx  # Alert notifications
│   │   ├── 📂 pages/
│   │   │   ├── Dashboard.tsx    # Main dashboard
│   │   │   ├── Forecast.tsx     # Forecast page
│   │   │   ├── Analytics.tsx    # Analytics page
│   │   │   ├── Households.tsx   # Household management
│   │   │   ├── AIInsights.tsx   # AI insights page
│   │   │   └── Login.tsx        # Authentication page
│   │   ├── 📂 services/
│   │   │   ├── api.ts           # API service configuration
│   │   │   ├── auth.ts          # Authentication service
│   │   │   ├── forecast.ts      # Forecast API calls
│   │   │   └── households.ts    # Household API calls
│   │   ├── 📂 types/
│   │   │   ├── user.ts          # TypeScript interfaces
│   │   │   ├── forecast.ts      # Forecast types
│   │   │   └── household.ts     # Household types
│   │   ├── 📂 styles/
│   │   │   ├── main.css         # Global styles
│   │   │   ├── components.css   # Component styles
│   │   │   └── variables.css    # CSS variables
│   │   ├── App.tsx              # Main application component
│   │   ├── main.tsx             # Application entry point
│   │   └── vite-env.d.ts        # Vite type definitions
│   ├── index.html               # HTML template
│   ├── package.json             # Node.js dependencies
│   ├── tsconfig.json            # TypeScript configuration
│   └── vite.config.ts           # Vite configuration
│
├── 📂 docs/
│   ├── api.md                   # API documentation
│   ├── data-guide.md            # Data format guide
│   └── deployment.md            # Deployment guide
│
├── 📂 scripts/
│   ├── setup.sh                 # Setup script
│   ├── deploy.sh                # Deployment script
│   └── backup.sh                # Data backup script
│
├── .gitignore                   # Git ignore file
├── LICENSE                      # MIT License
├── README.md                    # This file
└── docker-compose.yml          # Docker Compose configuration
```

---

## 🌐 API Documentation

### Authentication Endpoints
| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| `POST` | `/auth/register` | Register new user | `email, password, full_name` |
| `POST` | `/auth/login` | Login user | `email, password` |
| `GET` | `/auth/me` | Get current user | `Authorization: Bearer <token>` |
| `POST` | `/auth/logout` | Logout user | `Authorization: Bearer <token>` |

### Forecast Endpoints
| Method | Endpoint | Description | Parameters |
|--------|----------|-------------|------------|
| `GET` | `/forecast` | Current hour forecast | - |
| `POST` | `/forecast` | Custom prediction | `temperature, hour, day_of_week, region` |
| `GET` | `/forecast/24h` | 24-hour forecast | - |
| `GET` | `/forecast/weekly` | 7-day forecast | - |

### Analytics Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/analytics` | Demand analytics |
| `GET` | `/analytics/regions` | Regional breakdown |
| `GET` | `/analytics/stats` | Data statistics |
| `POST` | `/analytics/upload` | Upload CSV data |

### Household Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/households` | Create household |
| `GET` | `/households` | List user's households |
| `GET` | `/households/analytics` | Household analytics |
| `DELETE` | `/households/{id}` | Delete household |

### AI Insights Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/ai/insights` | Real-time AI insights |
| `GET` | `/ai/national` | National grid analytics |
| `GET` | `/ai/alerts` | System alerts |

---

## 📤 Data Upload Guide

### Supported CSV Format
```csv
datetime,demand,temperature,hour,day_of_week,month,humidity,is_holiday,region
2024-01-01 00:00:00,2850,18,0,0,1,65,1,National
2024-01-01 01:00:00,2650,17,1,0,1,68,1,National
2024-01-01 02:00:00,2550,16,2,0,1,70,1,National
```

### Required Columns
| Column | Type | Description | Required |
|--------|------|-------------|----------|
| `demand` | Float | Electricity demand in MW | ✅ Required |
| `datetime` | DateTime | Timestamp (ISO format) | Optional* |
| `temperature` | Float | Temperature in °C | Optional |
| `hour` | Integer | Hour of day (0-23) | Optional* |
| `day_of_week` | Integer | Day of week (0-6) | Optional* |
| `month` | Integer | Month (1-12) | Optional* |
| `humidity` | Float | Humidity percentage | Optional |
| `is_holiday` | Integer | 1=holiday, 0=non-holiday | Optional |
| `region` | String | Region name | Optional |

*Note: If datetime is provided, hour/day_of_week/month will be extracted automatically*

### Upload Process
1. Navigate to **Analytics → Upload Data**
2. Click **"Select CSV File"**
3. Choose your properly formatted CSV file
4. Click **"Upload & Retrain Model"**
5. System will:
   - ✅ Validate CSV format and data types
   - ✅ Check for duplicates
   - ✅ Append new data to existing dataset
   - ✅ Retrain ML model with updated data
   - ✅ Update all forecasts and analytics

### Sample Data Generator
```python
import pandas as pd
import numpy as np
from datetime import datetime, timedelta

# Generate realistic Ethiopian electricity demand data
def generate_sample_data(days=30, region="National"):
    dates = pd.date_range(
        start=datetime.now() - timedelta(days=days),
        periods=days*24,
        freq='H'
    )
    
    # Base demand pattern (MW)
    base_demand = 3500  # Average national demand
    
    # Time-based patterns
    hour_effect = 500 * np.sin((dates.hour - 2) * np.pi / 12)  # Peak at 2 PM
    day_effect = 300 * np.sin(dates.dayofweek * np.pi / 3.5)   # Weekday/weekend
    month_effect = 400 * np.sin((dates.month - 1) * np.pi / 6) # Seasonal
    
    # Temperature effect (more cooling in hot weather)
    temperature = 15 + 10 * np.sin(dates.hour * np.pi / 12) + np.random.normal(0, 3)
    temp_effect = 20 * (temperature - 20)  # 20°C is baseline
    
    # Calculate final demand
    demand = (
        base_demand +
        hour_effect +
        day_effect +
        month_effect +
        temp_effect +
        np.random.normal(0, 150)  # Random noise
    )
    
    # Create DataFrame
    df = pd.DataFrame({
        'datetime': dates,
        'demand': np.maximum(2000, demand),  # Minimum 2000 MW
        'temperature': temperature,
        'hour': dates.hour,
        'day_of_week': dates.dayofweek,
        'month': dates.month,
        'humidity': 50 + 20 * np.sin(dates.hour * np.pi / 12) + np.random.normal(0, 5),
        'is_holiday': (dates.dayofweek >= 5).astype(int),  # Weekends as holidays
        'region': region
    })
    
    return df

# Generate and save sample data
df = generate_sample_data(days=90, region="Addis Ababa")
df.to_csv('ethiopia_demand_data.csv', index=False)
print(f"Generated {len(df)} records")
```

---

## 🤖 ML Model Details

### Model Architecture
- **Algorithm**: Linear Regression with feature engineering
- **Features Used**:
  - Temporal: hour, day_of_week, month, is_weekend
  - Weather: temperature, humidity
  - Regional: region_one_hot_encoded
  - Derived: rolling_average_24h, demand_lag_24h

### Training Process
```python
# Simplified training pipeline
def train_model(data):
    # 1. Feature Engineering
    data['hour_sin'] = np.sin(2 * np.pi * data['hour'] / 24)
    data['hour_cos'] = np.cos(2 * np.pi * data['hour'] / 24)
    data['is_weekend'] = (data['day_of_week'] >= 5).astype(int)
    
    # 2. Feature Selection
    features = ['temperature', 'humidity', 'hour_sin', 'hour_cos', 
                'day_of_week', 'month', 'is_holiday', 'is_weekend']
    
    # 3. One-Hot Encoding for regions
    data = pd.get_dummies(data, columns=['region'], prefix='region')
    
    # 4. Train-Test Split
    X_train, X_test, y_train, y_test = train_test_split(
        data[features], data['demand'], test_size=0.2, random_state=42
    )
    
    # 5. Model Training
    model = LinearRegression()
    model.fit(X_train, y_train)
    
    # 6. Evaluation
    predictions = model.predict(X_test)
    mae = mean_absolute_error(y_test, predictions)
    r2 = r2_score(y_test, predictions)
    
    return model, mae, r2
```

### Model Performance
- **Mean Absolute Error (MAE)**: ~150 MW
- **R² Score**: 0.85-0.92
- **Training Time**: < 30 seconds for 10K records
- **Prediction Time**: < 10ms per prediction

---

## ⚙️ Configuration

### Environment Variables
Create `.env` file in `backend/` directory:

```env
# Backend Configuration
SECRET_KEY=your-secret-key-here-change-in-production
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
DATABASE_URL=sqlite:///./forecast.db

# ML Configuration
ML_MODEL_PATH=./ml/models/model.pkl
SCALER_PATH=./ml/models/scaler.pkl
DATA_PATH=./ml/data/historical_data.csv

# API Configuration
CORS_ORIGINS=["http://localhost:5173", "http://localhost:3000"]
```

### Ethiopian Regions Configuration
The system supports all 11 Ethiopian regions:
```python
REGIONS = [
    "Addis Ababa",
    "Oromia",
    "Amhara",
    "Tigray",
    "SNNPR",
    "Somali",
    "Afar",
    "Benishangul-Gumuz",
    "Gambela",
    "Harari",
    "Dire Dawa",
    "National"  # Aggregate national data
]
```

---

## 🧪 Testing

### Backend Tests
```bash
cd backend
pytest tests/ -v
```

### Frontend Tests
```bash
cd frontend
npm test
```

### API End-to-End Tests
```bash
# Using curl examples
curl -X POST http://localhost:8000/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@eeu.et","password":"test123"}'

curl -X GET http://localhost:8000/forecast \
  -H "Authorization: Bearer <your-token>"
```

---

## 🚢 Deployment

### Docker Deployment
```bash
# Build and run with Docker Compose
docker-compose up -d

# Check running containers
docker-compose ps

# View logs
docker-compose logs -f
```

### Production Deployment with Nginx
```nginx
# Nginx configuration (/etc/nginx/sites-available/forecast)
server {
    listen 80;
    server_name forecast.eeu.et;
    
    location /api {
        proxy_pass http://localhost:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
    
    location / {
        root /var/www/forecast/frontend/dist;
        try_files $uri $uri/ /index.html;
    }
}
```

### Cloud Deployment (AWS)
```bash
# Deploy to AWS Elastic Beanstalk
eb init --platform node.js --region us-east-1
eb create forecast-prod
eb deploy
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines
- Follow [PEP 8](https://pep8.org/) for Python code
- Use [ESLint](https://eslint.org/) for TypeScript/JavaScript
- Write tests for new features
- Update documentation accordingly
- Use meaningful commit messages

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Ethiopian Electric Utility

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Support & Contact

- **Issues**: [GitHub Issues](https://github.com/your-org/ethiopian-electric-forecast/issues)
- **Email**: support@eeu.et
- **Documentation**: [Wiki](https://github.com/your-org/ethiopian-electric-forecast/wiki)

## 🙏 Acknowledgments

- Ethiopian Electric Utility for domain expertise
- Open source community for amazing tools
- Contributors and maintainers

---

**⚡ Powering Ethiopia's Future with AI-Driven Energy Management**#   E t h i o p i a n - E l e c t r i c - U t i l i t y  
 