# 🌤️ Smart Weather Monitoring and Prediction System

An IoT-based intelligent weather monitoring system that collects real-time weather parameters using Arduino and IoT sensors, visualizes data on ThingSpeak, and performs predictive analysis using machine learning in Python.

---

## 📌 About

The Smart Weather Monitoring and Prediction System is an integrated IoT solution designed to monitor and forecast weather conditions in real-time. The system captures critical weather parameters (temperature, pressure, and humidity) using advanced sensors and transmits the data to ThingSpeak cloud platform for visualization. Additionally, the system includes Python-based machine learning analysis for weather prediction using Jupyter Notebook, enabling users to identify trends and forecast future weather patterns.

**Key Objectives:**
- Real-time weather parameter monitoring
- Cloud-based data visualization on ThingSpeak
- Historical weather data analysis
- Weather prediction using machine learning
- Multi-sensor data aggregation
- Accessible remote monitoring

---

## 🛠️ Technology & Hardware Stack

| Hardware Components | Software Tools | IoT & Cloud | Analysis & ML |
|:---:|:---:|:---:|:---:|
| Arduino Uno | Arduino IDE | ThingSpeak | Python 3.x |
| ESP8266 WiFi Module | Jupyter Notebook | WiFi Connectivity | Pandas |
| DHT11 Sensor | Git | RESTful API | NumPy |
| BMP180 Sensor | Code Editor | MQTT Ready | Scikit-learn |
| Breadboard | USB Cable | Cloud Storage | Matplotlib |
| Connecting Wires | Serial Monitor | Data Logging | Seaborn |

**Key Libraries & Dependencies:**
- `DHT11` - Temperature & Humidity sensor library
- `BMP180` - Barometric pressure sensor library
- `ESP8266WiFi` - WiFi connectivity
- `ThingSpeak API` - Cloud data transmission
- `pandas` - Data manipulation and analysis
- `scikit-learn` - Machine learning algorithms
- `matplotlib` - Data visualization
- `jupyter` - Interactive Python notebooks

---

**Key Components:**
- **Hardware Setup** - Arduino Uno with DHT11 and BMP180 sensors
- **IoT Module** - ESP8266 for WiFi connectivity
- **Cloud Integration** - ThingSpeak for real-time data visualization
- **Data Analysis** - Jupyter Notebook for Python-based analysis
- **ML Models** - Predictive algorithms for weather forecasting

---

## 🚀 Quick Start

### Hardware Prerequisites
- Arduino Uno microcontroller
- ESP8266 WiFi module
- DHT11 Temperature & Humidity sensor
- BMP180 Barometric pressure sensor
- Breadboard and connecting wires
- USB cable for Arduino programming

### Software Prerequisites
- Arduino IDE (latest version)
- Python 3.7 or higher
- Jupyter Notebook
- pip (Python package manager)
- Git

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/komal-30/Smart-Weather-Monitoring-and-Prediction-System.git
   cd Smart-Weather-Monitoring-and-Prediction-System
   ```

2. **Hardware Setup**
   - Connect DHT11 sensor to Arduino pin D2
   - Connect BMP180 sensor via I2C (SDA to A4, SCL to A5)
   - Connect ESP8266 to Arduino serial pins (RX/TX)
   - Use breadboard to organize connections
   - Refer to `Documentation/Circuit_Connections.md` for detailed wiring

3. **Configure Arduino**
   - Open `Hardware/Arduino_Sketches/main.ino` in Arduino IDE
   - Update WiFi SSID and password
   - Update ThingSpeak API key (get from https://thingspeak.com)
   - Select board: Arduino Uno
   - Select correct COM port
   - Upload the sketch to Arduino

4. **Setup ThingSpeak Account**
   - Create account at https://thingspeak.com
   - Create a new channel
   - Configure fields:
     - Field 1: Temperature (°C)
     - Field 2: Humidity (%)
     - Field 3: Pressure (hPa)
   - Copy API Write Key and update in Arduino code
   - Note Channel ID for Python analysis

5. **Setup Python Environment**
   ```bash
   pip install -r requirements.txt
   ```

6. **Run Data Analysis**
   - Open `Analysis/IOE_Final.ipynb` in Jupyter Notebook
   ```bash
   jupyter notebook Analysis/IOE_Final.ipynb
   ```
   - Update ThingSpeak Channel ID in the notebook
   - Run cells to fetch data and perform analysis

7. **Monitor in Real-Time**
   - Visit ThingSpeak channel dashboard
   - View live sensor readings and graphs
   - Monitor temperature, humidity, and pressure trends

### Configuration Notes
- Adjust sensor reading intervals in Arduino code (default: 15 seconds)
- Configure ThingSpeak API rate limits
- Set Python analysis parameters in Jupyter Notebook
- Calibrate sensors for accuracy if needed

---

## 📊 Sensors & Parameters

### DHT11 Sensor
- **Measures:** Temperature and Humidity
- **Temperature Range:** 0°C to 50°C
- **Humidity Range:** 20% to 90%
- **Accuracy:** ±2°C, ±5% RH
- **Connection:** Digital pin (D2)

### BMP180 Sensor
- **Measures:** Barometric Pressure and Altitude
- **Pressure Range:** 300 hPa to 1100 hPa
- **Accuracy:** ±1 hPa
- **Connection:** I2C interface (SDA, SCL)

---

## 🔄 System Architecture

```
┌─────────────────────────────────────────┐
│     Arduino Uno + Sensors               │
│  (DHT11, BMP180 Data Collection)       │
└────────────────────┬────────────────────┘
                     │
                     ▼
        ┌────────────────────────┐
        │   ESP8266 WiFi Module  │
        │  (Data Transmission)   │
        └────────────┬───────────┘
                     │
                     ▼
        ┌────────────────────────┐
        │   ThingSpeak Cloud     │
        │  (Real-time Dashboard) │
        └────────────┬───────────┘
                     │
        ┌────────────┴────────────┐
        │                         │
        ▼                         ▼
    Live Graphs            API Data Access
    & Visualization         (Python/Jupyter)
        │                         │
        └────────────┬────────────┘
                     │
                     ▼
         ┌──────────────────────────┐
         │  Python Analysis (ML)    │
         │  • Data Preprocessing    │
         │  • Exploratory Analysis  │
         │  • Weather Prediction    │
         │  • Visualizations        │
         └──────────────────────────┘
```

---

## 💡 Use Cases

| Use Case | Description |
|----------|-------------|
| **Home Weather Station** | Monitor household microclimate and comfort levels |
| **Agricultural Monitoring** | Track weather conditions for crop planning and irrigation |
| **Weather Forecasting** | Use ML models to predict short-term weather changes |
| **Air Quality Control** | Correlate weather parameters with air quality |
| **Educational Project** | Learn IoT, sensors, cloud platforms, and ML |
| **Weather Alerts** | Generate alerts for extreme weather conditions |

---

## 📈 Machine Learning Analysis

The Jupyter Notebook (`IOE_Final.ipynb`) includes:

- **Data Fetching** - Retrieve weather data from ThingSpeak API
- **Data Cleaning** - Handle missing values and outliers
- **Exploratory Analysis** - Statistical analysis and distributions
- **Visualizations** - Temperature, humidity, pressure trends
- **Correlation Analysis** - Relationships between parameters
- **Predictive Models:**
  - Linear Regression for temperature prediction
  - Time series analysis for trend forecasting
  - Classification for weather pattern recognition

---

## 📊 Data Visualization

ThingSpeak provides:
- Real-time line graphs for each parameter
- Customizable dashboard layouts
- Historical data analysis tools
- API for external visualization tools
- Mobile-friendly interface

Python visualization includes:
- Matplotlib plots for trends
- Seaborn statistical visualizations
- Correlation heatmaps
- Distribution plots

---

## 🔐 Security Considerations

- Store ThingSpeak API keys securely (use environment variables)
- Use HTTPS for cloud communication
- Limit API access with rate limiting
- Keep Arduino firmware updated
- Use strong WiFi credentials
- Monitor data privacy for long-term storage

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Arduino not uploading code** | Check USB drivers, select correct COM port and board |
| **Sensor not reading values** | Verify wiring, check sensor connections, run calibration |
| **WiFi connection fails** | Verify WiFi credentials, check ESP8266 firmware |
| **No data on ThingSpeak** | Verify API key, check internet connection, test API endpoint |
| **Python notebook errors** | Install all dependencies, update Channel ID in code |
| **Data not syncing** | Check upload interval, verify ThingSpeak quota limits |

---

## 📈 Future Enhancements

- [ ] 🌍 **GPS Integration** - Track weather by location
- [ ] 🔔 **Push Notifications** - Alerts for weather anomalies
- [ ] 🤖 **Advanced ML** - Deep learning for accurate predictions
- [ ] 📊 **Advanced Analytics** - Real-time big data processing

---

## 🔗 Additional Resources

- [Arduino Official Documentation](https://www.arduino.cc/en/main/software)
- [DHT11 Sensor Guide](https://www.adafruit.com/product/386)
- [BMP180 Sensor Guide](https://www.adafruit.com/product/1603)
- [ESP8266 WiFi Module](https://www.espressif.com/en/products/modules)
- [ThingSpeak IoT Platform](https://thingspeak.com/)
- [Python Data Science](https://www.python.org/)
- [Scikit-learn ML Library](https://scikit-learn.org/)
- [Jupyter Notebook](https://jupyter.org/)
