# 🌾 Harvestify - Smart Crop Prediction System

An intelligent agricultural assistant that uses machine learning to recommend optimal crops based on soil nutrients, weather conditions, and pH levels.

## 🚀 Features

- **AI-Powered Crop Recommendations** - Advanced ML model with 99.32% accuracy
- **Real-time Analysis** - Instant predictions with confidence scores
- **Professional UI** - Modern, responsive design with intuitive interface
- **Data-Driven Insights** - Analyzes soil nutrients (N, P, K), weather, and pH

## 🛠️ Tech Stack

### Backend
- **Framework:** FastAPI (Python)
- **ML Library:** scikit-learn
- **Model:** RandomForest Classifier and others
- **Database:** SQLite with SQLModel
- **Server:** Uvicorn

### Frontend
- **Framework:** React 18 with TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **Icons:** Font Awesome
- **Font:** Poppins

### Machine Learning
- **Algorithm:** RandomForest Classifier and others
- **Features:** N, P, K, temperature, humidity, pH, rainfall
- **Dataset:** Kaggle Crop Recommendation Dataset
- **Accuracy:** 99.32% (test set)
- **F1-Score:** 99.32% (macro)

## 📊 Model Details

### Dataset
- **Source:** [Kaggle Crop Recommendation Dataset](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset)
- **Size:** 2,200+ samples
- **Features:** 7 numerical features
- **Classes:** 22 different crops

### Model Performance
- **Training Accuracy:** 99.32%
- **Test Accuracy:** 99.32%
- **Macro F1-Score:** 99.32%
- **Cross-validation:** Stratified split (80/20)

### Features Used
- **N (Nitrogen):** Soil nitrogen content
- **P (Phosphorus):** Soil phosphorus content  
- **K (Potassium):** Soil potassium content
- **Temperature:** Average temperature (°C)
- **Humidity:** Relative humidity (%)
- **pH:** Soil pH level
- **Rainfall:** Annual rainfall (mm)

## 🏗️ Project Structure

```
Harvestify/
├── backend/
│   ├── app/
│   │   ├── main.py              # FastAPI app entry
│   │   ├── schemas.py           # Pydantic models
│   │   ├── db.py               # Database models
│   │   ├── routers/            # API endpoints
│   │   └── services/           # ML services
│   ├── train/
│   │   └── train_model.py      # Model training script
│   └── requirements.txt        # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── components/         # React components
│   │   ├── pages/             # Page components
│   │   └── lib/               # API client
│   ├── package.json           # Node dependencies
│   └── tailwind.config.js     # Tailwind config
├── data/
│   └── Crop_recommendation.csv # Dataset (you provide)
├── models/                    # Trained model artifacts
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Node.js 16+
- npm or yarn

### 1. Clone & Setup
```bash
git clone <your-repo-url>
cd Harvestify
```

### 2. Dataset Setup
Download the Kaggle dataset and place it at:
```
data/Crop_recommendation.csv
```

### 3. Backend Setup
```bash
# Navigate to backend
cd backend

# Install Python dependencies
pip install -r requirements.txt

# Train the model (creates models/ folder)
python -m train.train_model --data_path ../data/Crop_recommendation.csv --out_dir ../models
```

### 4. Start Backend Server
```bash
# Set environment variables (PowerShell)
$env:MODEL_DIR = "../models"
$env:DB_PATH = "./data/harvestify.db"

# Start FastAPI server
uvicorn app.main:app --reload --port 8000
```

### 5. Frontend Setup
```bash
# Open new terminal, navigate to frontend
cd frontend

# Install Node dependencies
npm install

# Start development server
npm run dev
```

### 6. Access Application
- **Frontend:** http://localhost:5173
- **Backend API:** http://localhost:8000
- **API Docs:** http://localhost:8000/docs

## 📡 API Endpoints

### Health Check
```bash
GET /api/v1/healthz
```

### Crop Prediction
```bash
POST /api/v1/crops/predict
Content-Type: application/json

{
  "N": 50,
  "P": 50, 
  "K": 50,
  "temperature": 25,
  "humidity": 60,
  "ph": 6.5,
  "rainfall": 100,
  "top_k": 3
}
```

### Get Available Crops
```bash
GET /api/v1/crops/labels
```

## 🎯 Usage

1. **Visit the landing page** - Learn about the system
2. **Navigate to Crop Prediction** - Enter your parameters
3. **Fill the form** with your soil and weather data
4. **Get instant recommendations** with confidence scores
5. **View detailed results** with nutrient analysis

## 🔧 Development

### Backend Development
```bash
cd backend
# Install in development mode
pip install -e .

# Run with auto-reload
uvicorn app.main:app --reload --port 8000
```

### Frontend Development
```bash
cd frontend
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build
```

### Model Retraining
```bash
cd backend
python -m train.train_model --data_path ../data/Crop_recommendation.csv --out_dir ../models


## 🐛 Troubleshooting

### Common Issues

**Backend won't start:**
- Ensure model files exist in `models/` folder
- Check environment variables are set correctly
- Verify dataset path is correct

**Frontend build fails:**
- Clear node_modules and reinstall: `rm -rf node_modules && npm install`
- Check Node.js version compatibility

**API calls fail:**
- Ensure both servers are running
- Check CORS settings
- Verify API endpoints in browser dev tools

### Environment Variables
```bash
# Backend
MODEL_DIR=../models          # Path to model artifacts
DB_PATH=./data/harvestify.db # SQLite database path
CORS_ORIGINS=http://localhost:5173 # Frontend URL
```

## 📈 Model Performance

The RandomForest model achieves excellent performance:
- **High Accuracy:** 99.32% on test set
- **Balanced Performance:** 99.32% macro F1-score
- **Robust Predictions:** Handles various input ranges
- **Fast Inference:** Sub-second prediction times

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Kaggle for the crop recommendation dataset
- FastAPI and React communities
- Agricultural experts for domain knowledge

---

**Built with ❤️ for sustainable agriculture**
