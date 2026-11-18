# Web Threat Analysis (Cyber Security)

A data-analysis project on web traffic logged by AWS CloudWatch. It explores the traffic and trains models that flag traffic detected by web-application-firewall (WAF) rules.

## What the notebook does

`web_threat_analysis.ipynb` (in `Web-Threat-Analysis-Cyber-Security-main/`):

1. **Cleaning:** removes duplicate rows, converts timestamps, standardises country codes
2. **Feature engineering:** adds connection duration, scales numeric features, one-hot encodes source country
3. **Exploration:** correlation heatmap, detection types by country, bytes in and out over time, and a network graph of source → destination IPs
4. **Modelling:** labels each record as suspicious if it matched a WAF rule, then trains:
   - a Random Forest classifier (scikit-learn)
   - two small dense neural networks and a 1D CNN (TensorFlow/Keras)

## Data

`CloudWatch_Traffic_Web_Attack.csv`: about 280 records of web traffic (bytes in and out, source and destination IP, country, protocol, port, detection type), from a public sample dataset of AWS CloudWatch / VPC flow logs.

## Tech

Python 3, pandas, scikit-learn, TensorFlow/Keras, seaborn, Matplotlib, NetworkX, Jupyter

## How to run

```bash
pip install pandas scikit-learn tensorflow seaborn matplotlib networkx notebook
jupyter notebook
```

Open the notebook and change the `pd.read_csv(...)` path in the second cell to the CSV in this folder. It was written for Google Colab, so it points at `/content/...`.

## Results

The notebook was saved without its outputs, so accuracy figures and charts appear only when you run it.
