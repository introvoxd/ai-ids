# AI-IDS

AI-IDS is an AI-powered intrusion detection system built for IoT and edge-network security. The project combines a Java Spring Boot API, a Python Flask ML inference service, and a real-time dashboard to monitor network traffic, classify attacks, and visualize malicious activity.

It is designed around a multi-layer IDS workflow for IoT environments using ESP32 telemetry, CIC-IoT 2023-based attack modeling, XGBoost classification, and live web monitoring.

## Overview

This repository contains three major components:

- 2_Backend_Core/spring_boot_backend
  - Spring Boot backend service for the dashboard, REST APIs, WebSockets, packet simulation, and data orchestration.
- 2_Backend_Core/python_flask_inference
  - Flask service that loads the trained ML model and classifies traffic features for inference.
- 3_Frontend_Dashboard
  - Static web dashboard for live monitoring, attack visualization, simulation lab, settings and offline analysis.

## Key Features

- Real-time IoT traffic monitoring
- ESP32-based edge packet collection and telemetry
- XGBoost-based multi-class intrusion detection
- Spring Boot backend with WebSocket push updates
- Flask inference service for ML prediction
- Live dashboard with attack alerts and metrics
- Offline CSV/PCAP analysis workflow
- Telegram alert integration
- MITRE ATT&CK-inspired attack categorization

## Architecture

The system follows a practical edge-to-dashboard workflow:

1. ESP32 or simulated network traffic generates packet/flow features.
2. The Spring Boot backend ingests and forwards telemetry.
3. The Python Flask inference service scores the features using the trained XGBoost model.
4. The dashboard receives real-time updates through WebSocket/MQTT streams.
5. Threat events are surfaced in the UI, logs, and alert channels.

## Tech Stack

### Backend
- Java 22
- Spring Boot 3.3
- Maven
- WebSocket / REST APIs

### Inference Engine
- Python 3
- Flask
- NumPy
- scikit-learn-compatible XGBoost model pipeline
- MQTT client support

### Frontend
- HTML
- CSS
- JavaScript
- Chart.js
- MQTT client for live updates

## Repository Structure

```text
AI-IDS/
├── README.md
├── .gitignore
├── docs/
│   └── PROJECT_STRUCTURE.md
├── 2_Backend_Core/
│   ├── python_flask_inference/
│   │   ├── ids_inference_server.py
│   │   ├── requirements.txt
│   │   ├── model_multi.pkl
│   │   ├── scaler_multi.pkl
│   │   ├── Dockerfile
│   │   ├── Procfile
│   │   └── runtime.txt
│   └── spring_boot_backend/
│       ├── pom.xml
│       ├── Dockerfile
│       ├── START.bat
│       └── src/
│           ├── main/java/com/ids/
│           ├── main/resources/
│           └── main/resources/static/
├── 3_Frontend_Dashboard/
│   ├── index.html
│   ├── css/
│   ├── js/
│   ├── vercel.json
│   └── assets/ (if present in your local setup)
└── model
```

## Dataset

The ML model is based on the CIC-IoT 2023 dataset from the Canadian Institute for Cybersecurity.

Official dataset:
https://www.unb.ca/cic/datasets/iotdataset-2023.html

## Local Development

### 1) Start the Python inference service

```bash
cd 2_Backend_Core/python_flask_inference
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python ids_inference_server.py
```

The service exposes health and inference endpoints and defaults to port 5000 locally.

### 2) Start the Spring Boot backend

```bash
cd 2_Backend_Core/spring_boot_backend
mvn clean install
mvn spring-boot:run
```

The backend runs the dashboard API and WebSocket layer, usually on port 8080.

### 3) Start the frontend dashboard

You can serve the frontend locally using any static server:

```bash
cd 3_Frontend_Dashboard
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Environment Variables

Some components use environment variables for integration:

- BOT_TOKEN
- CHAT_ID
- PORT

Example:

```bash
export PORT=5000
export BOT_TOKEN="your_token_here"
export CHAT_ID="your_chat_id_here"
```

## Demo Access

Frontend demo:
https://ai-ids-five.vercel.app

Default login credentials:
- Username: admin
- Password: admin

## Deployment

### Frontend
- Vercel

### Backend
- Render

### Inference Service
- Render or any Python hosting service

## Future Improvements

- Add more attack classes and richer feature extraction
- Improve data persistence and historical reporting
- Add secure authentication and role-based access control
- Integrate a cloud database for long-term retention
- Expand explainable AI and threat intelligence reporting
- Add mobile-friendly admin views

## Project Status

This repository is a functional AI IDS prototype showcasing a complete edge-to-dashboard IoT intrusion detection workflow with live monitoring, model inference, and attack visualization.

## License

This project is licensed under the MIT License.

## Contributing

Contributions are welcome. If you want to improve the detection pipeline, UI, documentation, or deployment setup, open a pull request with a clear description of the changes.

---

For more detail on the repo layout and responsibilities of each component, see:
- docs/PROJECT_STRUCTURE.md
