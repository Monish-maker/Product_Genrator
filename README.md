# 🧠📄 Product Description Generator using T5 (Transformers + TensorFlow)

This project fine-tunes a pre-trained **T5 (Text-to-Text Transfer Transformer)** model to generate detailed product descriptions from a given **title** and **set of keywords**. Ideal for e-commerce platforms, marketing automation, and AI content writing.

---

## 🚀 Features

- ✅ Fine-tunes `t5-base` on a custom product dataset
- ✅ Generates creative, domain-specific product descriptions
- ✅ TensorFlow & HuggingFace integration
- ✅ Trained model and dataset hosted on Google Drive

---

## 📁 Dataset Format

Your CSV file should include these columns:

| title             | keyword                           | description             |
|-------------------|------------------------------------|--------------------------|
| Apple MacBook Pro | laptop, high performance, design   | A high-end laptop with...|

---

## 📦 Download Links (Google Drive)


💾 **Fine-tuned T5 Model with Dataset:**  
👉 [Download the zip file that contain the model and the data set used](https://drive.google.com/file/d/1sCZ1-RpULz2j9is_U8DWI-pgOgmRpekT/view?usp=sharing)

> Note: Unzip the model before loading it with `TFAutoModelForSeq2SeqLM.from_pretrained()`.

---

## 🛠️ Tech Stack

- Python
- TensorFlow (Keras API)
- HuggingFace Transformers
- HuggingFace Datasets
- scikit-learn
- Google Colab

---

## 🔧 Training Workflow

1. Load & split the dataset (80% train, 20% validation)
2. Tokenize inputs (`title + keywords`) and outputs (`description`)
3. Fine-tune `t5-base` with masked padding
4. Save model and tokenizer for reuse
5. Generate descriptions with inference API

---

## 🔍 Example Usage

test_title = "Apple MacBook Pro"
test_keywords = "laptop, high performance, sleek design"

description = generator.generate_description(test_title, test_keywords)
print(description)

🖨️ Output:

A high-performance laptop designed for professionals with a sleek design and powerful specs.

💾 Save & Load Model

Save:

generator.save_model("./fine_tuned_t5_model")

Load later:

from transformers import TFAutoModelForSeq2SeqLM, AutoTokenizer

model = TFAutoModelForSeq2SeqLM.from_pretrained('./fine_tuned_t5_model')
tokenizer = AutoTokenizer.from_pretrained('./fine_tuned_t5_model')
