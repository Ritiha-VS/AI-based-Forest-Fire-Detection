# AI-Based Forest Fire Detection using TinyML & ESP32

A lightweight, real-time forest fire detection system built on ESP32 using a Convolutional Neural Network (CNN) optimized with TensorFlow Lite for edge deployment — achieving **98.07% test accuracy** with a model size of just **0.13 MB**.

---

## Overview

Forest fires cause devastating environmental and economic damage. This project addresses the need for a **low-cost, low-power, real-time fire detection system** that can operate in remote areas without internet connectivity.

By deploying a CNN model directly on the ESP32 microcontroller using **TinyML techniques**, this system detects fire in real time at the edge — no cloud required.

---

## Tech Stack

| Category | Tools / Technologies |
|---|---|
| Microcontroller | ESP32 |
| ML Framework | TensorFlow Lite (TFLite) |
| Model Type | Convolutional Neural Network (CNN) |
| Optimization | TFLite Post-Training Quantization |
| Programming Language | C++, Python |
| Development Tools |  ESP-IDF, Visual Studio Code |

---

## How It Works

1. **Model Training** — A CNN model is trained on a labeled fire/no-fire image dataset using Python and TensorFlow.
2. **Model Optimization** — The trained model is quantized using TensorFlow Lite to reduce size and latency, making it suitable for microcontroller deployment.
3. **Edge Deployment** — The optimized `.tflite` model is deployed onto the ESP32.
4. **Real-Time Inference** — The ESP32 captures input data and runs inference locally, triggering alerts when fire is detected.
5. **Visualization** — Fire regions are highlighted using bounding box outlines and heatmaps for interpretability.

---

## Features

- ✅ Real-time fire detection at the edge (no internet needed)
- ✅ Lightweight CNN — only **35,372 parameters**, **0.13 MB** model size
- ✅ **98.07% test accuracy** with 98.13% precision and recall
- ✅ Fire region localization with bounding box outlines
- ✅ Heatmap visualization to highlight fire-prone areas
- ✅ Low latency inference on ESP32
- ✅ Scalable for deployment in remote forest locations

---

## Results

### Model Performance

| Metric | Value |
|---|---|
| ✅ Test Accuracy | **98.07%** |
| ✅ Precision | **98.13%** |
| ✅ Recall | **98.13%** |
| ✅ Total Parameters | **35,372** |
| ✅ Approx Model Size | **0.13 MB** |

---

### Training & Validation Accuracy

The model converges rapidly within 3 epochs and maintains stable accuracy above 96% throughout training — demonstrating no overfitting.

![Model Accuracy](images/model_accuracy.png)

---

### Confusion Matrix

Out of 829 test samples, the model correctly classified 814 images with only 15 misclassifications — 3 false positives and 12 false negatives.

![Confusion Matrix](images/confusion_matrix.png)

| | Predicted: No Fire | Predicted: Fire |
|---|---|---|
| **Actual: No Fire** | 397 ✅ | 3 ❌ |
| **Actual: Fire** | 12 ❌ | 417 ✅ |

---

### 🔥 Fire Detected — Sample Output

The model successfully detects fire regions, highlights them with bounding boxes, and generates a heatmap showing the intensity distribution.

![Fire Detected](images/fire_detected.png)

---

### 🌲 No Fire — Sample Output

For non-fire forest scenes, the model correctly classifies the image as safe, with no false fire regions triggered.

![No Fire](images/no_fire.png)


## Future Improvements

- Integrate a camera module (OV2640) for live image capture on ESP32
- Add GSM/LoRa module for remote alerts in areas without Wi-Fi
- Expand dataset with night-time and smoke-only fire images
- Deploy multiple sensor nodes for wide-area forest monitoring
- Explore MobileNet-based architectures for further accuracy gains

---

## 👤 Author

**Ritiha V S**  
B.E. ECE — Government College of Engineering, Bodinayakanur  



## 📄 License

This project is open source and available under the [MIT License](LICENSE).
