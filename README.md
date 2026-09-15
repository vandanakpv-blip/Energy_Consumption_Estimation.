# Energy_Consumption_Estimation.
A frontend-based energy consumption estimation and analysis application using React, TensorFlow.js, Recharts, and Tailwind CSS. Includes real-time ML prediction, energy analytics, model performance metrics, and PDF report generation.
#  Energy Consumption Estimation

A frontend-based machine learning application that analyzes historical energy usage and predicts future energy consumption based on environmental and usage-related factors.

The application uses **React, TensorFlow.js, Vite, Tailwind CSS, and Recharts** to provide an interactive dashboard for energy analysis and ML-based consumption estimation.

##  Features

*  **Energy Consumption Dashboard**

  * Total number of records
  * Average, highest, and lowest consumption
  * Average temperature and humidity
  * Historical consumption trends

* **Energy Consumption Prediction**

  * Predict energy consumption based on user-provided conditions
  * Uses previous energy usage, temperature, humidity, hour, day of week, season, holiday status, and previous-period usage
  * Classifies predicted consumption as Low, Moderate, High, or Very High

*  **Energy Analysis**

  * Hourly consumption analysis
  * Seasonal consumption comparison
  * Temperature vs. consumption relationship
  * Historical consumption trends

* 🤖 **Machine Learning Model**

  * TensorFlow.js regression model
  * Feed-forward neural network
  * 80/20 training and testing split
  * 50 training epochs
  * Model evaluation using MAE, MSE, RMSE, and R² score

*  **PDF Report Generation**

  * Generates a downloadable energy consumption report
  * Includes prediction results, input conditions, model metrics, analysis, and charts

*  **Fully Client-Side**

  * No backend server required
  * No external APIs
  * Dataset processing, model training, prediction, and report generation run directly in the browser

##  Technologies Used

* **React** – User interface
* **Vite** – Frontend development and build tool
* **TensorFlow.js** – Machine learning and prediction
* **Tailwind CSS** – Styling and responsive UI
* **Recharts** – Data visualization
* **PapaParse** – CSV dataset parsing
* **jsPDF** – PDF report generation
* **html2canvas** – Chart/image capture for reports
* **JavaScript (ES6+)** – Application logic

## Machine Learning

The application uses a simple feed-forward neural network for energy consumption regression.

### Model Architecture

```text
Input Layer (8 features)
        ↓
Dense Layer (16 neurons, ReLU)
        ↓
Dense Layer (8 neurons, ReLU)
        ↓
Output Layer (1 neuron, Linear)
```

The model is trained using the **Adam optimizer** with **Mean Squared Error (MSE)** as the loss function.

### Input Features

The model uses:

* Previous energy usage
* Temperature
* Humidity
* Hour
* Day of week
* Season
* Holiday status
* Previous period usage

The numerical features are normalized before training, while categorical values such as season and holiday are encoded numerically.

##  Project Structure

```text
energy-consumption/
│
├── public/
│   └── data/
│       └── energy_consumption.csv
│
├── src/
│   ├── components/
│   │   ├── ChartCard.jsx
│   │   ├── Header.jsx
│   │   ├── StatCard.jsx
│   │   ├── ReportButton.jsx
│   │   ├── PredictionResult.jsx
│   │   └── Sidebar.jsx
│   │
│   ├── ml/
│   │   ├── model.js
│   │   ├── preprocessing.js
│   │   └── training.js
│   │
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── EstimateConsumption.jsx
│   │   ├── EnergyAnalysis.jsx
│   │   └── ModelPerformance.jsx
│   │
│   ├── services/
│   │   └── dataset.js
│   │
│   ├── utils/
│   │   └── reportGenerator.js
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── index.html
├── package.json
├── tailwind.config.js
├── vite.config.js
└── README.md
```

##  Dataset

The project includes a synthetic dataset containing **720 hourly energy consumption records covering 30 days**.

Each record contains:

```text
timestamp
previous_usage
temperature
humidity
hour
day_of_week
season
holiday
previous_period_usage
energy_consumption
```

The dataset can be replaced with another dataset as long as the same column structure is maintained.

##  Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd energy-consumption
```

### 2. Install dependencies

```bash
npm install
```

### 3. Start the development server

```bash
npm run dev
```

Open the local URL provided by Vite in your browser.

##  How It Works

```text
CSV Dataset
     ↓
Data Loading & Processing
     ↓
Feature Normalization & Encoding
     ↓
80/20 Train-Test Split
     ↓
TensorFlow.js Model Training
     ↓
Model Evaluation
     ↓
Interactive Dashboard
     ↓
User Input
     ↓
Energy Consumption Prediction
     ↓
Prediction Visualization & PDF Report
```

##  Project Purpose

The project demonstrates how machine learning can be integrated into a modern web application to analyze energy consumption patterns and generate consumption estimates without requiring a separate backend or external ML service.

It combines **data analysis, machine learning, visualization, and frontend development** into a single interactive application.

##  Future Improvements

* Use larger real-world energy datasets
* Add more advanced ML algorithms
* Improve prediction accuracy through hyperparameter tuning
* Add daily, weekly, and monthly forecasting
* Include energy-saving recommendations
* Add user authentication and personalized energy profiles
* Connect the application to real-time smart-meter data
* Deploy the application as a production web application

## License

This project is intended for educational and academic purposes.
