# ⚡ Wind Power Generation Forecasting

This project is all about predicting wind power generation using weather data. I wanted to build something that takes in real-time weather inputs like wind speed, humidity, temperature, and gives you a solid estimate of how much wind energy would be produced.

---

## 🔍 What’s going on here?

I trained a deep learning model (just a clean feedforward neural net using TensorFlow/Keras) on a dataset with over **43,000 hourly records** of weather and actual wind power data.

The goal: **predict the “Power” output from weather features.**

The inputs include:
- Windspeed at 10m and 100m
- Wind direction
- Wind gusts
- Temperature, humidity, dewpoint
- Time-based features like hour, day of week, and month

---

## 🧠 How it works

### Data Prep:
- Cleaned and scaled the dataset (used `StandardScaler`)
- Engineered time features (because wind patterns vary by time of day and season)
- No missing data drama — it was handled early

### Model:
- Simple but effective neural network
- 3 hidden layers, ReLU activations
- Output layer predicts wind power for a given hour

### Evaluation:
- **MAE**: ~0.12
- **RMSE**: ~0.15
- **R² Score**: ~0.69  
  (which means the model explains ~69% of the variance in power output — not bad for a first version)

---

## 📊 Visuals

I added a bunch of plots to better understand and explain:
- Actual vs Predicted values (line + scatter)
- Error over time
- Where the model performed best and worst
- Correlation heatmap of input features

---

## 🔮 Real-Time Prediction

Once trained, the model can take in any weather input and tell you the expected power output.

Example:

```python
input_weather = {
    'temperature_2m': 30.2,
    'relativehumidity_2m': 88,
    'dewpoint_2m': 27,
    'windspeed_10m': 3.54,
    'windspeed_100m': 6.89,
    'winddirection_10m': 74,
    'winddirection_100m': 81,
    'windgusts_10m': 5.8,
    'hour': 8,
    'dayofweek': 0,
    'month': 1
}

# Output → 🔋 Predicted Power Output: 0.1452
```

---

## 🔧 Next Steps / Ideas

I’m already thinking of upgrades:
- Try LSTM or GRU models for better time-series predictions
- Add lag features (previous hour’s power output)
- Deploy this as a live Streamlit app or API
- Use forecasted weather to predict future energy output

---

## 🛠 Tools Used

- Python, pandas, numpy
- TensorFlow / Keras
- Matplotlib + Seaborn
- scikit-learn

---

## 📬 Get in Touch

If you're into renewable energy forecasting or just curious, feel free to reach out or fork this and play around with it. Always open to collabs and cool ideas.

---

*Thanks for reading — wind power for the win 💨⚡*
