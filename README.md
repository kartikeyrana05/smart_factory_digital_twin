
  # AI-Driven Digital Twin for Smart Factory Operations

A virtual smart factory platform simulating industrial equipment and production operations in real time with end-to-end telemetry streaming, AI/ML-driven anomaly detection, multi-dimensional operational risk scoring, digital twin state management, and an interactive FastAPI modern web visualizer dashboard.

---

## 🏗️ Architecture Flow

```
[Virtual Factory Simulation (M01, M02, M03)]
                    │
                    ▼
[MQTT Telemetry Publisher] (Mosquitto / HiveMQ Cloud)
                    │
                    ▼
[MQTT Telemetry Subscriber & Pipeline]
                    │
      ┌─────────────┴───────────────────────────────┐
      ▼                                             ▼
[SQLite Database Engine]              [PyTorch AI/ML Anomaly Detector]
(data/smart_factory.db)                             │
      ▲                                             ▼
      │                               [Rule & AI Machine Health Evaluator]
      │                                             │
      │                                             ▼
      │                               [Operational Risk & OEE Engine]
      │                                             │
      │                                             ▼
      │                               [Industrial Alert & Cooldown Engine]
      │                                             │
      │                                             ▼
      └───────────────────────────────[Digital Twin In-Memory State Model]
                                                    │
                                                    ▼
                                      [FastAPI REST & WebSocket Server]
                                                    │
                                                    ▼
                                      [Interactive Web Dashboard Visualizer]
                                      (http://localhost:8000)
```

---

## 📂 Project Directory Structure

```
DigitalTwin/
│
├── config/
│   ├── __init__.py           # Dynamic configuration & environment variable loader
│   └── config.yaml           # Factory baselines, machine thresholds, topics & weights
│
├── simulator/
│   ├── __init__.py           # Physics simulation package
│   ├── machine.py            # Machine state machine with noise & degradation curves
│   └── factory_simulator.py  # Synchronized factory line simulator (M01, M02, M03)
│
├── mqtt/
│   ├── __init__.py           # MQTT networking package
│   ├── publisher.py          # Telemetry & status publisher (TLS & Auth support)
│   └── subscriber.py         # Telemetry ingestion, schema validation & routing
│
├── database/
│   ├── __init__.py           # SQLite database persistence layer
│   ├── schema.sql            # Relational tables, time-series views & indices
│   └── database.py           # Thread-safe DatabaseManager with WAL mode
│
├── ai/
│   ├── __init__.py           # Deep Learning package
│   ├── models/               # PyTorch model weights (.pt) & scaler parameters (.json)
│   ├── anomaly_model.py      # Deep Autoencoder architecture
│   ├── preprocessing.py      # Feature normalization & scaling
│   ├── train.py              # Model training routine
│   └── inference.py          # Real-time anomaly scoring & prediction engine
│
├── analytics/
│   ├── __init__.py           # Industrial analytics package
│   ├── health.py             # Multi-sensor weighted health scoring (0-100%)
│   ├── risk.py               # Operational risk evaluation matrix
│   ├── maintenance.py        # Prescriptive diagnostics & overhaul recommendations
│   └── oee.py                # Overall Equipment Effectiveness calculator
│
├── alerts/
│   ├── __init__.py           # Industrial alert package
│   └── alert_manager.py      # Alert deduplication, sliding cooldown & multi-channel dispatch
│
├── digital_twin/
│   ├── __init__.py           # Virtual digital twin state synchronization package
│   └── twin.py               # Synchronized in-memory factory & machine twin models
│
├── api/
│   ├── __init__.py           # Web API backend package
│   └── main.py               # FastAPI REST endpoints, WebSockets, & HTML5/CSS3 Dashboard
│
├── tests/
│   ├── test_phase2.py to test_phase10.py  # Phase-by-phase test suites
│   ├── test_database_queries.py          # Database schema & query validation
│   └── test_hivemq_config.py             # HiveMQ Cloud TLS & credential tests
│
├── data/
│   └── smart_factory.db      # SQLite local database
│
├── main_pipeline.py          # Master end-to-end integration orchestrator
├── requirements.txt          # Python dependencies
├── .env                      # Local environment configuration
├── .env.example              # Configuration template
└── README.md
```

---

## 🚀 Execution & Verification Guide

### 1. Prerequisites (Windows)
* Python 3.10+ (tested on Python 3.14)
* Mosquitto MQTT Broker running on `localhost:1883` (`Start-Service mosquitto`) or HiveMQ Cloud cluster

### 2. Environment Activation
```powershell
.\.venv\Scripts\Activate.ps1
```

### 3. Run the Master End-to-End Factory Integration Pipeline
```powershell
python main_pipeline.py
```
This runs the complete simulation, PyTorch AI anomaly inference, health/risk calculations, alert engine, digital twin synchronization, and SQLite persistence.

### 4. Start the Interactive FastAPI Digital Twin Server & Web Dashboard
```powershell
uvicorn api.main:app --reload --port 8000
``

### 5. Run Complete Automated Test Suite
```powershell
pytest -v
```
LIVE DASHBOARD
URL="https://digitaltwin-smartfactory-1.onrender.com/"
 ## 📸 Project Dashboard & Screenshots

### 1. Smart Factory Digital Twin – Main Dashboard

<img width="100%" alt="Smart Factory Main Dashboard"
src="<img width="1861" height="687" alt="Screenshot 2026-10-31 102431" src="https://github.com/user-attachments/assets/27123942-58f3-4918-aa4a-b6348bb9bfe6" />
" />

### 2. Real-Time Machine Health Monitoring

<img width="100%" alt="Real-Time Machine Health Monitoring"
src="<img width="1861" height="687" alt="Screenshot 2026-10-31 102431" src="https://github.com/user-attachments/assets/cbd4a212-ec30-42e3-9bd6-8a993c017b81" />
" />

### 3. AI-Based Machine Analytics & Telemetry

<img width="100%" alt="AI Machine Analytics and Telemetry"
src="<img width="1858" height="903" alt="Screenshot 2026-10-31 102411" src="https://github.com/user-attachments/assets/273e9497-f5d5-4d1f-b702-764ffe110a96" />
" />
