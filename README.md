# Energy Consumption Estimation

Frontend-only ML app. React + Vite + Tailwind + TensorFlow.js + Recharts + PapaParse + jsPDF + html2canvas.
No backend, no external APIs. Dataset load, training, prediction, and PDF report all run in the browser.

## Run it

npm install
npm run dev

Open the printed local URL. First load: dataset loads, is processed, model trains (~50 epochs), then evaluates before the dashboard is ready.

## Structure

- public/data/energy_consumption.csv — 720 hourly synthetic records (30 days), statistically realistic
- src/ml/ — preprocessing, model definition, training/evaluation
- src/services/dataset.js — CSV loading + summary/trend/seasonal helpers
- src/pages/ — Dashboard, Estimate Consumption, Energy Analysis, Model Performance
- src/components/ — Sidebar, Header, StatCard, ChartCard, PredictionResult, ReportButton
- src/utils/reportGenerator.js — builds the downloadable PDF (jsPDF + html2canvas)

Swap in your own data by replacing public/data/energy_consumption.csv, keeping the same column names
(timestamp, previous_usage, temperature, humidity, hour, day_of_week, season, holiday, previous_period_usage, energy_consumption).

## Report download

On the Estimate Consumption page, after a prediction, "Download Report" generates
energy-consumption-report.pdf with the prediction, inputs, model metrics, a short analysis,
and a chart image — all pulled from the current session, nothing hardcoded.
