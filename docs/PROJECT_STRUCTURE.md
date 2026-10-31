# AI-IDS Repository Structure

This project is organized around a practical three-layer architecture:

- Frontend: user-facing dashboard and control panel
- Backend: Java Spring Boot API and real-time messaging layer
- Inference engine: Python ML service that classifies IoT traffic

## Top-level structure

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
│   │   ├── Dockerfile
│   │   ├── Procfile
│   │   ├── runtime.txt
│   │   ├── model_multi.pkl
│   │   └── scaler_multi.pkl
│   └── spring_boot_backend/
│       ├── pom.xml
│       ├── Dockerfile
│       ├── START.bat
│       └── src/
│           └── main/
│               ├── java/com/ids/
│               ├── resources/
│               └── resources/static/
├── 3_Frontend_Dashboard/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── vercel.json
└── model/
```

## Why this structure works

The repo is intentionally split so each component has a focused role:

### 2_Backend_Core/python_flask_inference
Responsible for:
- model loading
- feature classification
- inference endpoints
- Telegram/MQTT alert hooks

### 2_Backend_Core/spring_boot_backend
Responsible for:
- REST APIs
- dashboard orchestration
- WebSocket events
- packet simulation and monitoring services
- Java-side management of live IDS data

### 3_Frontend_Dashboard
Responsible for:
- live monitoring UI
- attack charts and event tables
- simulation lab
- file analysis workflow
- settings and dashboard overview

## Suggested future improvement

A cleaner long-term project structure would be:

```text
AI-IDS/
├── backend/
│   ├── spring-boot/
│   └── python-inference/
├── frontend/
│   └── dashboard/
├── docs/
├── notebooks/
├── data/
├── tests/
├── README.md
├── .gitignore
└── LICENSE
```

This would make the repo easier to navigate as the project grows.
