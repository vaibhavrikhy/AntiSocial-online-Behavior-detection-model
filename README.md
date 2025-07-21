# AntiSocial Online Behavior Detection

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![Python Version](https://img.shields.io/badge/python-3.8%2B-green.svg)](https://python.org)

**A robust hybrid deep-learning framework for detecting anti-social content in online text, combining CNN, RNN, and transformer-based models.**

---

## 🚀 Features

* **Hybrid Architectures**: CNN for n-gram feature extraction, RNN (LSTM/GRU/Bi-LSTM/Bi-GRU) for sequential patterns, and transformer fine-tuning (BERT).
* **End-to-End Pipeline**: Data ingestion, preprocessing, model training, evaluation, and inference scripts.
* **Benchmark Suite**: Compare multiple models side-by-side with consistent metrics (accuracy, precision, recall, F1).
* **Configurable & Extensible**: YAML-based configs for hyperparameters and model selection.
* **Reproducible**: Docker support for consistent environments.

---

## 🎯 Motivation

Online platforms suffer from toxic, hate-filled, and anti-social language that can harm communities. Automated detection enables:

1. **Real-time moderation** for safer conversations.
2. **Scalable review** of large volumes of user-generated content.
3. **Insights** into trends and patterns of abusive behaviour.

By leveraging multiple deep-learning paradigms, this project elevates detection performance beyond single-model baselines.

---

## 📦 Repository Structure

```
├── data/
│   ├── raw/           # Original unprocessed files
│   └── processed/     # Tokenized, padded CSV datasets
├── src/
│   ├── preprocess.py  # Data cleaning and tokenization
│   ├── train.py       # Model training script
│   ├── evaluate.py    # Evaluation and metrics
│   └── predict.py     # Inference on new samples
├── configs/           # YAML configs for each model
├── assets/            # Diagrams and visualizations
├── models/            # Saved checkpoints and training logs
├── Dockerfile         # Container environment setup
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

---

## 📖 Quick Start

Get up and running in minutes:

1. **Clone the repository**

   ```bash
   git clone https://github.com/anirudhavadhani70/AntiSocial-online-Behavior-detection-model.git
   cd AntiSocial-online-Behavior-detection-model
   ```

2. **Build & run with Docker** (optional)

   ```bash
   docker build -t aob-detector .
   docker run --rm -v "$(pwd)/data:/app/data" aob-detector \
     python src/train.py --config configs/cnn_rnn.yaml
   ```

3. **Or install dependencies locally**

   ```bash
   pip install -r requirements.txt
   ```

4. **Prepare your data**

   ```bash
   python src/preprocess.py \
     --input data/raw/dataset.csv \
     --output data/processed/
   ```

5. **Train a model**

   ```bash
   python src/train.py --config configs/bert_finetune.yaml
   ```

6. **Evaluate performance**

   ```bash
   python src/evaluate.py \
     --checkpoint models/bert_finetune.ckpt \
     --data data/processed/test.csv
   ```

7. **Run inference**

   ```bash
   python src/predict.py \
     --model models/bert_finetune.ckpt \
     --text "Your sample text here"
   ```

---

## 📈 Benchmark Results

| Model               | Accuracy | Precision |   Recall | F1‑Score |
| ------------------- | -------: | --------: | -------: | -------: |
| CNN                 |     0.87 |      0.85 |     0.84 |     0.84 |
| Bi-LSTM             |     0.91 |      0.90 |     0.89 |     0.89 |
| CNN + LSTM (Hybrid) |     0.92 |      0.91 |     0.90 |     0.90 |
| BERT (fine-tuned)   | **0.94** |  **0.93** | **0.92** | **0.92** |

*Transformer-based models lead the pack, demonstrating superior nuance in detecting abusive patterns.*

---

## 📊 Architecture Diagram

![Hybrid Model Architecture](assets/architecture.png)

---

## 🤝 Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to your branch (`git push origin feature-name`).
5. Open a Pull Request.

Please ensure all new code is covered by appropriate tests and add/update documentation as needed.

---

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

Maintainer: **Your Name**

* Email: [youremail@example.com](mailto:youremail@example.com)
* GitHub: [@USERNAME](https://github.com/USERNAME)

Feel free to open issues or reach out for discussions!
