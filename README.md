# Network Intrusion Detection System (NIDS)

## Overview
This project is a **Network Intrusion Detection System (NIDS)** that uses a hybrid detection approach combining **signature-based detection** for known threats and **anomaly-based detection** for unknown or evolving threats. The system is designed to enhance network security by identifying and reporting suspicious activities in network traffic.

The project also includes a **Streamlit-based web interface** for user interaction, allowing users to upload network data, analyze it, and view detected intrusions in real time.

---

## Features

- **Hybrid Detection**:
  - **Signature-Based Detection**: Identifies known attacks using predefined patterns (e.g., SQL injection, XSS).
  - **Anomaly-Based Detection**: Detects deviations from normal behavior using the Isolation Forest algorithm.

- **Streamlit Interface**:
  - Allows CSV file uploads.
  - Provides a preview of the dataset.
  - Displays detected intrusions with key details (e.g., source IP, destination IP, attack type).

- **Customizable Detection**:
  - Add new signature patterns for specific attack types.
  - Adjust anomaly detection thresholds.

---

## Project Structure

```
NIDS_Project/
|
├── data/
│   └── kddcup.data_10_percent_corrected.csv  # Example dataset
│
├── nids_final.ipynb       # Main code file with preprocessing, training, and evaluation
├── intrusion_detection.py # Streamlit app for real-time intrusion detection
|
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
```

---

## Installation

### Prerequisites
- Python 3.8 or higher
- Streamlit
- Required libraries (listed in `requirements.txt`)

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/NIDS.git
   cd NIDS
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Streamlit app:
   ```bash
   streamlit run intrusion_detection.py
   ```

---

## Usage

### Streamlit Interface
1. Open the web interface by running the Streamlit app.
2. Upload a CSV file containing network traffic data.
3. The app will:
   - Display a preview of the uploaded data.
   - Run both signature-based and anomaly-based detection.
   - Display detected intrusions with details (source IP, destination IP, attack type, payload).

### Jupyter Notebook
1. Use `nids_final.ipynb` for exploratory data analysis and model training.
2. Adjust parameters and retrain the model as needed.

---

## Detection Approach

### Signature-Based Detection
Uses predefined regular expressions to detect specific patterns in network traffic data (e.g., SQL injection, FTP root access attempts).

### Anomaly-Based Detection
- **Algorithm**: Isolation Forest
- **Features Used**: Numerical features such as `duration`, `src_bytes`, `dst_bytes`, `count`, and `srv_count`.
- **Training**: Trains on normal traffic data to learn the patterns of legitimate behavior.
- **Prediction**: Flags deviations as potential intrusions.

---

## Results

### Signature-Based Detection
- Detected known attack patterns (e.g., SQL injection, XSS) in the uploaded dataset.

### Anomaly-Based Detection
- Identified anomalies based on deviations from normal behavior using numerical features.

### Example Output (Streamlit)
- **Source IP**: 192.168.1.12
- **Destination IP**: 10.0.0.5
- **Detection Type**: Anomaly-based attack
- **Payload**: Anomalous data point

---

## Dataset

The project uses a sample dataset (`kddcup.data_10_percent_corrected.csv`) for training and testing. Ensure your dataset contains the following key features:

- `duration`
- `src_bytes`
- `dst_bytes`
- `count`
- `srv_count`
- `label` (optional, for supervised evaluation)

---

## Future Scope

- Add real-time traffic analysis capabilities.
- Improve anomaly detection using advanced algorithms like Autoencoders.
- Enhance the web interface with interactive visualizations.
- Include support for additional datasets and traffic types.

---

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

---


