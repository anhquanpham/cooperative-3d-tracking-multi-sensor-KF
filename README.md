# Analysis and Improvements in 3D Multi-Object Cooperative Tracking for Autonomous Driving
**Video Demo:** [YouTube ▶️](https://www.youtube.com/watch?v=iMu7Uq024Tg)

---

## 📖 Overview

This repository re-implements and extends **DMSTrack** – a Differentiable Multi-Sensor Kalman Filter for 3D multi-object cooperative tracking. Our key contributions are:

* **Terminal ReLU on covariance residuals** to prevent negative-variance gradients.
* **Reduced initial covariance scale** for faster convergence.
* Achieve **> 43.61 % AMOTA** in just 4 epochs (80 % fewer training epochs than baseline) and markedly smoother training/validation losses.

---

## 🚀 Features

* End-to-end differentiable Kalman filter with learnable per-detection covariances.
* Modular PyTorch code for the ObservationCovarianceNet (with BEV + positional features).
* Support for:

  * **ReLU-clamped** covariance residuals.
  * **LeakyReLU** alternative.
  * **Constant covariance** baseline.


## 📊 Results

| Method                          | AMOTA ↑   | AMOTP ↑   | sAMOTA ↑  | MOTA ↑    | MT ↑      | ML ↓      |
| ------------------------------- | --------- | --------- | --------- | --------- | --------- | --------- |
| Constant covariance             | 41.51     | 55.87     | 89.37     | 88.68     | 66.67     | 13.67     |
| Default DMSTrack                | 43.52     | **57.94** | 91.50     | 88.32     | **68.35** | **13.19** |
| **DMSTrack with ReLU (ours)**   | **43.61** | 57.51     | **91.64** | **88.71** | 67.39     | 13.43     |
| DMSTrack with Leaky ReLU (ours) | 41.48     | 54.83     | 88.92     | 88.10     | 66.43     | 13.43     |

---

## 🎥 Demo Video

[![Watch the demo](https://img.youtube.com/vi/iMu7Uq024Tg/maxresdefault.jpg)](https://www.youtube.com/watch?v=iMu7Uq024Tg)

---

## 📝 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

