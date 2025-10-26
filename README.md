# SRIR: F1 Rival Radio Intelligence System

🏎️ **SRIR: F1 Rival Radio Intelligence.** Full-stack AI portfolio project. Transcribes & analyzes F1 radio sentiment using local Whisper (CUDA) + NLP Transformers. ⚡ Stack: FastAPI (Python) & React (JS).

---

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-05998b?logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?logo=pytorch&logoColor=white)
![NVIDIA CUDA](https://img.shields.io/badge/NVIDIA-CUDA-76B900?logo=nvidia&logoColor=white)

Este es un proyecto personal de portfolio que demuestra una aplicación full-stack de IA, diseñada para el análisis estratégico de la Fórmula 1.

## 🚀 Características Principales

* **Transcripción de Audio:** Utiliza **OpenAI Whisper** para convertir las comunicaciones de radio (con ruido, acentos y jerga técnica) en texto.
* **Análisis de Sentimiento:** Emplea un modelo NLP de **Hugging Face Transformers** (BERT) para detectar el tono del piloto (pánico, calma, frustración).
* **Dashboard Interactivo:** Una interfaz en **React** que muestra las transcripciones y análisis clave en un formato fácil de digerir.
* **Procesamiento Local:** Todo el pipeline de IA se ejecuta en hardware local (desarrollado sobre una NVIDIA RTX 3050), demostrando la capacidad de usar PyTorch y CUDA.

## 🛠️ Stack Tecnológico

* **Backend:** **FastAPI** (Python)
* **Frontend:** **React** (JavaScript/Vite)
* **Núcleo de IA:**
    * **PyTorch** (con soporte CUDA)
    * **OpenAI Whisper** (para Speech-to-Text)
    * **Hugging Face Transformers** (para NLP/Análisis de Sentimiento)

## 🏎️ ¿Cómo Funciona?

1.  El usuario (simulando un estratega) carga un archivo de audio de una carrera.
2.  El frontend **React** envía este audio a la API de **FastAPI**.
3.  El backend utiliza **Whisper** (corriendo en la GPU) para transcribir el audio.
4.  El texto transcrito se pasa al modelo **BERT** para un análisis de sentimiento.
5.  La API devuelve un JSON con el texto, *timestamp* y sentimiento.
6.  El frontend muestra esta información en un *dashboard* claro y accionable.

## ⚙️ Ejecución Local

Este proyecto está dividido en dos carpetas: `/backend` y `/frontend`.

### Requisitos Previos

* Python 3.10+
* Node.js 18+
* GPU NVIDIA con **CUDA Toolkit** instalado.
* `ffmpeg` (para que Whisper pueda procesar los audios).

### 1. Backend (FastAPI)

```bash
# Navega a la carpeta del backend
cd backend

# (Recomendado) Crea y activa un entorno virtual
python -m venv venv

# Activa el entorno virtual:
# En Windows:
.\venv\Scripts\activate
# En Unix/Linux/macOS:
source venv/bin/activate

# Instala las dependencias
pip install -r requirements.txt

# Inicia el servidor
uvicorn main:app --reload
# La API estará en http://localhost:8000