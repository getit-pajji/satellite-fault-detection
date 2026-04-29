# satellite-fault-detection
Satellite AI: LSTM Autoencoder for Fault Detection

A real-time multivariate telemetry monitoring system designed for Low Earth Orbit (LEO) satellites. This prototype uses an LSTM-based Autoencoder architecture to detect operational anomalies in thermal, power, and propulsion subsystems.

🛰️ Project Overview

Satellite telemetry is complex, sequential, and highly correlated. Traditional threshold-based monitoring often fails to catch "soft" or "evolving" faults. This project implements a Deep Learning approach where an LSTM Autoencoder learns the "Normal" operational state and identifies deviations through Reconstruction Error analysis.

Key Features

Real-time Inference Simulation: Live dashboard showing reconstruction error vs. dynamic thresholds.

Multichannel Telemetry: Monitoring of Thermal (C), EPS Voltage (V), and Propulsion Pressure (PSI).

Advanced Metrics: Real-time Confusion Matrix (TP, TN, FP, FN) with Accuracy and F1-Score calculation.

Expert Systems Log: Actionable insights for mission control based on model output.

Research Integrated: Full documentation and literature survey accessible within the application.

🧠 Technical Architecture

1. LSTM Autoencoder Model

The model acts as a "compression-decompression" engine:

Encoder: Compresses 60-step temporal windows of multivariate data into a low-dimensional bottleneck (Latent Space).

Decoder: Attempts to reconstruct the original 60-step sequence from the compressed state.

Logic: During training on "Normal" data, the model learns the inherent patterns of the satellite. When an "Anomaly" occurs, the model cannot reconstruct it correctly, leading to a spike in Mean Squared Error (MSE).

2. Detection Logic

$$Reconstruction Error (e) = ||X_{input} - X_{reconstructed}||^2$$

If $e > \tau$ (Threshold), flag as Anomaly.

If $e \le \tau$, flag as Normal.

🛠️ Tech Stack

Framework: React.js

Styling: Tailwind CSS (Monochromatic NASA-spec theme)

Visualizations: Recharts (D3-based responsive charts)

Icons: Lucide-React

🚀 How to Run Locally

Clone the repository:

git clone [https://github.com/getit-pajji/satellite-fault-detection.git](https://github.com/getit-pajji/satellite-fault-detection.git)


Install dependencies:

npm install


Run the development server:

npm run dev


🌐 Deployment

This project is optimized for deployment on Vercel or Netlify. Simply connect your GitHub repository to Vercel, and it will automatically build and deploy the index.jsx file.

Author: Computer Science Engineering Student

Context: Bachelor of Engineering Project Report


done by 
vaibhav rustagi 
raj mangalam gupta 
arpan dixit
