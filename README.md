# AI-IDS

An AI-powered Intrusion Detection System (IDS) for IoT networks that detects malicious traffic using machine learning and provides real-time monitoring through a web dashboard.

## Features

- Machine Learning based intrusion detection
- Real-time traffic monitoring
- Interactive dashboard
- Backend REST APIs
- Threat visualization and analytics
- Modular architecture for easy extension

## Project Structure

```
AI-IDS/
├── 2_Backend_Core/
│   └── Backend services and ML inference
├── 3_Frontend_Dashboard/
│   └── Dashboard and visualization
└── README.md
```

## Tech Stack

### Backend
- Python
- Machine Learning
- REST APIs

### Frontend
- HTML
- CSS
- JavaScript
## Dataset

This project is trained and evaluated using the **CICIoT2023** dataset developed by the Canadian Institute for Cybersecurity (CIC), University of New Brunswick.

**Dataset:** CICIoT2023

The dataset contains both benign and malicious IoT network traffic covering a wide range of attack types, making it suitable for training and evaluating machine learning based Intrusion Detection Systems (IDS).

**Source:**
https://www.unb.ca/cic/datasets/iotdataset-2023.html



## Getting Started

### Clone the repository

```bash
git clone https://github.com/itsUjjwal1010/ai-ids.git
cd ai-ids
```

### Backend

```bash
cd 2_Backend_Core
# Install dependencies
pip install -r requirements.txt

# Run the backend
python app.py
```

### Frontend

```bash
cd 3_Frontend_Dashboard
# Open index.html
```

## Demo

Live Demo:
https://ai-ids-five.vercel.app

## Future Improvements

- Additional attack detection models
- Cloud deployment
- Authentication
- Alert notifications
- Performance optimization



## License

This project is licensed under the MIT License.
