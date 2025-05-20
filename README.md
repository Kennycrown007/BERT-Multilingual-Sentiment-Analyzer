# 🧠 BERT Multilingual Sentiment Analyzer

[![Python](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![HuggingFace Model](https://img.shields.io/badge/model-nlptown/bert--base--multilingual--uncased--sentiment-blue)](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment)

This project leverages a pre-trained multilingual BERT model from HuggingFace to analyze the sentiment of interview responses stored in an Excel file. It outputs sentiment scores (1–5) for each response and appends them to the original dataset.

---

## 📂 Table of Contents

- Overview
- Installation
- Usage
- Input Format
- Output Format
- Features
- Dependencies
- Examples
- Troubleshooting
- Contributing
- License

---

## 📋 Overview

This tool:
- Loads participant responses from an Excel spreadsheet.
- Analyzes each textual response using a BERT-based sentiment classifier.
- Outputs sentiment scores (1 = very negative, 5 = very positive).
- Saves the augmented dataset for reporting or further analysis.

---

## ⚙️ Installation

1. Clone the repository:
   git clone https://github.com/yourusername/multilingual-sentiment-analysis.git
   cd multilingual-sentiment-analysis

2. Install dependencies:
   pip install -r requirements.txt

3. Prepare your Excel file:
   Ensure the file `Interview Data.xlsx` is present in the root directory, or modify the path in the script accordingly.

---

## 🚀 Usage

Run the Python script:
   python sentiment_analysis.py

To export the results:
Uncomment and update the last line in the script:
   # output_df.to_excel("path/to/save/output.xlsx", index=False)

---

## 📥 Input Format

- Excel file named `Interview Data.xlsx`
- The first column should be labeled `Participant`
- Subsequent columns should contain textual responses

Example:

| Participant | Response1           | Response2           |
|-------------|---------------------|---------------------|
| Alice       | I loved the session | It was very helpful |
| Bob         | Not very engaging   | Could be improved   |

---

## 📤 Output Format

Each response gets an additional sentiment column (1 to 5):

| Participant | Response1           | Response1_Sentiment | Response2           | Response2_Sentiment |
|-------------|---------------------|----------------------|---------------------|----------------------|
| Alice       | I loved the session | 5                    | It was very helpful | 5                    |
| Bob         | Not very engaging   | 2                    | Could be improved   | 3                    |

---

## ✨ Features

- 🌍 Multilingual support
- 🧠 Pre-trained BERT sentiment model
- 📊 Easy Excel input/output
- 🔌 Plug-and-play implementation

---

## 📦 Dependencies

- transformers
- torch
- pandas
- numpy
- openpyxl

Install them all using:
   pip install -r requirements.txt

---

## 🧪 Examples

Python code snippet:

def sentiment_score(text):
    tokens = tokenizer.encode(text, return_tensors='pt', truncation=True)
    result = model(tokens)
    return int(torch.argmax(result.logits)) + 1

---

## ❗ Troubleshooting

- FileNotFoundError: Double-check the filename and path of your Excel input.
- Slow Inference: Try batching requests or using GPU acceleration.
- Model Download Issues: Ensure internet access on first run (for downloading model).

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork this repository and submit a pull request.

---

## 📝 License

This project is licensed under the MIT License.

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://www.datascienceportfol.io/KehindeAromona)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kehinde-gabriel-aromona-808578119/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/kennycrown7)

