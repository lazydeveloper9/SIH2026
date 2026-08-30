# 🚀 Smart India Hackathon 2026 — Dual Solution Repository

[![SIH 2026](https://img.shields.io/badge/SIH-2026-orange.svg?style=for-the-badge&logo=target)](https://sih.gov.in)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-brightgreen.svg?style=for-the-badge&logo=python)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/Docker-Enabled-2496ED.svg?style=for-the-badge&logo=docker)](https://www.docker.com/)

This repository hosts the source code, technical documentation, architectural blueprints, and presentation decks for two mission-critical solutions developed for **Smart India Hackathon 2026**.

---

## 📑 Table of Contents

- [Problem Statement 1: MineNav-Vision (Open Cast Mines)](#-ps-1-safenav-mines)
  - [Overview](#ps-1-overview)
  - [Key Features](#ps-1-key-features)
  - [Tech Stack](#ps-1-tech-stack)
  - [System Architecture](#ps-1-system-architecture)
- [Problem Statement 2: SovereignAgent Workbench (Industrial AI)](#-ps-2-sovereignagent-workbench)
  - [Overview](#ps-2-overview)
  - [Key Features](#ps-2-key-features)
  - [Tech Stack](#ps-2-tech-stack)
  - [System Architecture](#ps-2-system-architecture)
- [📂 Repository Structure](#-repository-structure)
- [⚡ Quick Start & Installation](#-quick-start--installation)
- [📊 Documentation & Deliverables](#-documentation--deliverables)
- [👥 Team Details](#-team-details)

---

## 🚜 PS-1: Safe Navigation of Mines
**"Safe and Efficient Operation of Mine Vehicles in Fog and Low-Visibility Conditions in Open Cast Iron Ore Mines"**

### PS-1 Overview
In open-cast iron ore mining, severe fog, suspended particulate dust ($PM_{10}/PM_{2.5}$), and heavy rain drastically reduce visibility, causing fatal haul truck collisions, edge drop-offs, and operational shutdowns. **SafeNav-Mines** is a multimodal sensor-fusion edge computing system delivering real-time obstacle detection, dynamic path guidance, and collision avoidance without relying on external cloud connectivity.

### PS-1 Key Features
- **Multi-Spectral Sensor Fusion:** Fuses Thermal IR, Millimeter-Wave (mmWave) Radar, and LiDAR point clouds to penetrate dense fog and red dust clouds.
- **Dehazing & Contrast Enhancement Pipeline:** Hardware-accelerated zero-DCE and cycle-consistent generative networks for real-time video dehazing.
- **Dynamic Digital Twin & Geo-Fencing:** UWB/RTK-GPS localized terrain map with proximity alerts for haul-road benches and berm edges.
- **V2X Proximity & Collision Alert:** Ultra-low latency $(<30\text{ ms})$ acoustic and visual HUD warnings for heavy dumpers and light utility vehicles.

### PS-1 Tech Stack
- **Vision & Edge AI:** YOLOv10 / RT-DETR (Fine-tuned on thermal/synthetic fog datasets), OpenCV, TensorRT, ROS 2 (Robot Operating System)
- **Hardware Target:** NVIDIA Jetson Orin AGX / Jetson Orin Nano, TI IWR6843 mmWave Radar, FLIR Thermal Cameras
- **Backend & Telemetry:** FastAPI, Mosquitto MQTT Broker, InfluxDB, WebRTC for low-latency cab feeds

---

## 🛡️ PS-2: Sovereign Agent Workbench
**"Sovereign On-Premise Agentic AI Workbench using Open-Weight Multimodal LLMs for Confidential Industrial Work"**

### PS-2 Overview
Critical infrastructure and manufacturing industries generate highly confidential schematics, telemetry, and proprietary SOPs that cannot leave the internal network. **SovereignAgent** is an air-gapped, on-premise agentic orchestration platform powered by quantized open-weight Multimodal Foundation Models (VLMs/LLMs). It automates industrial diagnostics, schematic QA, and root-cause analysis with zero external data telemetry.

### PS-2 Key Features
- **Strict 100% Air-Gapped Operation:** Runs completely on local compute infrastructure with zero external API dependencies or telemetry callbacks.
- **Autonomous Multi-Agent Workflows:** Specialized autonomous sub-agents (CAD Parser, Telemetry Analyst, Compliance Checker, Code Interpreter) collaborating via ReAct and planning loops.
- **Multimodal Document & Diagram Intelligence:** Reads complex P&ID diagrams, electrical schematics, and tabular telemetry logs using open-weight Vision-Language Models.
- **Role-Based Access & Local RAG:** Hierarchical Vector DB with attribute-based access control (ABAC) and cryptographic audit trails for all agent actions.

### PS-2 Tech Stack
- **LLM/VLM Core:** DeepSeek-R1 / Llama-3.3-70B (Quantized via GGUF/AWQ), Qwen2.5-VL, vLLM / Ollama Runtime
- **Agentic Framework:** LangGraph / CrewAI, Custom ReAct orchestrator, Local Python sandbox (Dockerized/gVisor)
- **RAG & Search:** Qdrant / Milvus (Vector Search), BGE-M3 (Hybrid Sparse/Dense Embeddings)
- **Frontend & App:** Next.js / React, TailwindCSS, FastAPI, PostgreSQL

---

## 📂 Repository Structure

```text
├── .github/                      # CI/CD pipelines & issue templates
├── Documents/                         # Common documentation and guidelines
│   ├── SIH2026_Idea_Brief.pdf
│   └── architecture_diagrams/
│
├── PS007/            # PROBLEM STATEMENT 1
│   ├── src/                      # Perception & Fusion source code
│   │   ├── dehazing/             # Vision enhancement algorithms
│   │   ├── sensor_fusion/        # Radar + Thermal + LiDAR fusion
│   │   └── collision_warning/    # Proximity & path trajectory tracking
│   ├── hardware/                 # Schematics, BOM, Jetson deployment scripts
│   ├── tests/                    # Simulation & benchmark test suites
│   ├── docs/                     # Detailed PS-1 Documentation & API specs
│   │   └── PS1_Technical_Report.pdf
│   ├── ppt/                      # Presentation deck for PS-1
│   │   └── SafeNav_Mines_Pitch.pptx
│   ├── Dockerfile
│   └── requirements.txt
│
├── PS117/           # PROBLEM STATEMENT 2
│   ├── backend/                  # Agent orchestrator & API service
│   │   ├── agents/               # Multi-agent system definitions
│   │   ├── rag_engine/           # Air-gapped document ingestion & RAG
│   │   └── sandbox/              # Isolated code execution environment
│   ├── frontend/                 # Web workbench UI
│   ├── models/                   # Model quant/setup scripts (GGUF/vLLM)
│   ├── docs/                     # Detailed PS-2 Documentation & Security audit
│   │   └── SovereignAgent_Whitepaper.pdf
│   ├── ppt/                      # Presentation deck for PS-2
│   │   └── SovereignAgent_Pitch.pptx
│   ├── docker-compose.yml
│   └── requirements.txt
│
├── LICENSE
└── README.md
```
# 👥 Team Details
Team Name: [ijjat se team ka naam soch ke batao]

Institution: BHILAI INSTITUTE OF TECHNOLOGY DURG
|Name|Role|Core Contributions|Contact|
|----|----|------------------|-------|
|Yogendra K Narmada|	Team Lead |	Synthetic Datasets & Testing Benchmarks|	[GitHub / Email]|
|Rupesh Kumar Sahu|	Operational Lead|	System Architecture & Model Optimization|	[GitHub / Email]|
|Pari Roy|	Edge AI & Embedded Dev|	Sensor Fusion & Hardware Interfacing (PS-1)|	[GitHub / Email]|
|Akshat Agrawal|	Research & QA Lead|	Compliance, Documentation & PPT Decks|	[GitHub / Email]|
|Sejal Sahu|	Backend & Agentic Systems|	Agent Orchestration & Local RAG (PS-2)|	[GitHub / Email]|
|Manasvi Chanchal|	Full-Stack Developer|HUD Cab Interface & Workbench UI|	[GitHub / Email]|
