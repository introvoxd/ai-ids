# NsecureX

An AI-powered Intrusion Detection System (IDS) designed for IoT networks using ESP32, Machine Learning, Spring Boot, and Python Flask. The system captures network traffic, detects malicious activities in real time using an XGBoost model, and visualizes security events through an interactive web dashboard.

## Features

- Real-time IoT network intrusion detection
- ESP32-based edge packet monitoring
- XGBoost machine learning model for attack classification
- Spring Boot backend services
- Python Flask inference server
- Interactive web dashboard
- Live attack visualization
- Offline CSV/PCAP analysis
- Explainable AI (XAI) insights
- Telegram alert notifications

---

## Tech Stack


### Backend
- Spring Boot (Java)
- Python Flask
- XGBoost
- MQTT
- WebSocket

### Frontend
- HTML
- CSS
- JavaScript

### Machine Learning
- XGBoost
- Scikit-learn
- Pandas
- NumPy

---

## Dataset

The machine learning model was trained and evaluated using the **CICIoT2023** dataset developed by the Canadian Institute for Cybersecurity (CIC), University of New Brunswick.

Dataset:
https://www.unb.ca/cic/datasets/iotdataset-2023.html

---

## Deployment

### Frontend
**Vercel**

### Backend
**Render**

---

## Project Structure

```
AI-IDS/
├── 2_Backend_Core/
├── 3_Frontend_Dashboard/
├── model/
└── README.md
```

---

## Live Demo

Frontend:
https://ai-ids-five.vercel.app

Backend:
https://ai-ids-iot-8y4f.onrender.com

---

## Future Improvements

- Support additional attack classes
- Mobile application
- Cloud database integration
- Role-based authentication
- Advanced threat analytics

---



## License

This project is licensed under the MIT License.
