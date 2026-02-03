# 🩻 X-Ray Lung Disease Diagnosis (Pneumonia Detection)

A deep learning–based **chest X-ray classification system** that predicts whether a patient is suffering from **Pneumonia** or not.
The system is built using a **custom CNN in PyTorch**, exposed via a **FastAPI REST API**, and deployed to the cloud using **Render**.

---

## 🚀 Live API (Render)

Your model is now deployed as a cloud service.

**Base URL**

```
https://<your-render-app>.onrender.com
```

**Swagger Docs**

```
https://<your-render-app>.onrender.com/docs
```

**Prediction Endpoint**

```
POST /predict
```

Upload a chest X-ray and receive the diagnosis instantly.

---

## 📌 Problem Statement

Pneumonia is an inflammatory condition of the lungs affecting the alveoli.
Symptoms include cough, fever, chest pain, and difficulty breathing.
Diagnosis is often confirmed using **Chest X-rays**.

Our goal is to build an **AI-powered API** that can automatically classify X-ray images as:

* **Normal**
* **Pneumonia**

to assist doctors in faster diagnosis.

---

## 💡 Solution Overview

* Custom **CNN model built with PyTorch**
* Image preprocessing with TorchVision
* Inference through a **FastAPI REST service**
* Dockerized & cloud-ready
* **Deployed on Render** with dynamic port binding

---

## 🧠 Model Architecture

![xray\_arch](https://user-images.githubusercontent.com/71321529/216753362-aeb34400-d21d-4b21-b2ce-63b86a47b594.jpg)

---

## 📊 Dataset

The dataset was provided by **Apollo Diagnostic Center** for research purposes.
This project is a **Proof of Concept (POC)** based on that data.

---

## 🧩 Tech Stack

* **Python**
* **FastAPI**
* **PyTorch**
* **TorchVision**
* **Docker**
* **AWS**
* **Azure**
* **Render (Cloud Hosting)**

---

## 📂 Project Structure

```
Lungs-Disease-Diagnosis/
├── app.py
├── xray_model.pth
├── xray/
│   └── ml/model/arch.py
├── requirements.txt
├── runtime.txt
└── README.md
```

---

## ⚙️ Run Locally

### 1️⃣ Activate environment

```powershell
.venv\Scripts\activate
```

### 2️⃣ Start API server

```powershell
uvicorn app:app --host 0.0.0.0 --port 8001
```

### 3️⃣ Open Swagger

```
http://127.0.0.1:8001/docs
```

Use **POST /predict** to upload X-ray images.

---

## ☁️ Render Deployment

### Required Files

Create a file called:

`runtime.txt`

```
python-3.10.13
```

---

### Render Commands

| Field          | Value                                         |
| -------------- | --------------------------------------------- |
| Root Directory | `.`                                           |
| Build Command  | `pip install -r requirements.txt`             |
| Start Command  | `uvicorn app:app --host 0.0.0.0 --port $PORT` |

Then click:

> **Manual Deploy → Clear Build Cache & Deploy**

---

## 🧪 Example Response

```json
{
  "prediction_index": 1,
  "prediction_label": "Pneumonia"
}
```

---

## ⚠️ Important Notes

* Do NOT commit `.venv/` or `genai-env/` folders.
* Always bind to `$PORT` in production.
* Torch requires Python ≤ 3.10.

---

## 🔮 Future Enhancements

* Multi-class lung disease detection
* Grad-CAM heatmaps
* Video & batch inference
* Doctor dashboard UI

---

## 🎯 Conclusion

This system demonstrates how **AI + Cloud + APIs** can support medical diagnosis.
It provides fast, accurate predictions that can assist healthcare professionals in real-world decision-making.

