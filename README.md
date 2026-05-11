# 🍎 Fruit Image Classification using CNN

A Deep Learning image classification project built with **TensorFlow** and **Keras** using a **Convolutional Neural Network (CNN)** architecture to classify fruit images into multiple categories.

---

# 🚀 Project Overview

This project implements a CNN-based image classification model capable of recognizing different fruit categories from image inputs.

The model was trained, evaluated, and exported into multiple deployment formats including:

- TensorFlow SavedModel
- TensorFlow Lite (TFLite)
- TensorFlow.js (TFJS)

---

# 🧠 Model Architecture

The model was developed using a Sequential CNN architecture consisting of:

- Conv2D Layers
- Batch Normalization
- MaxPooling2D
- Dense Layers
- Dropout Regularization
- Softmax Output Layer

---

# 📂 Dataset Classes

The dataset contains 3 image classes:

- 🍎 Apple
- 🍊 Orange
- 🍐 Pear

---

# 📈 Model Performance

| Metric | Score |
|---|---|
| Training Accuracy | > 95% |
| Validation Accuracy | > 95% |
| Testing Accuracy | > 95% |

---

# 🛠 Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn

---

# 📦 Model Export Formats

This project provides the trained model in multiple formats:

- `SavedModel`
- `TensorFlow Lite (.tflite)`
- `TensorFlow.js`

---

# 🔑 Kaggle API Setup

To download the dataset from Kaggle, you need a Kaggle API token.

## 1️⃣ Create Kaggle API Token

1. Open Kaggle
2. Go to **Account Settings**
3. Scroll to the **API** section
4. Click **Create New Token**
5. A file named `kaggle.json` will be downloaded automatically

---

## 2️⃣ Upload kaggle.json to Google Colab

```python
from google.colab import files
files.upload()
```

---

## 3️⃣ Move kaggle.json to Kaggle Directory

```python
!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json
```

---

## 4️⃣ Download Dataset from Kaggle

```python
!kaggle datasets download -d moltean/fruits
```

Extract dataset:

```python
!unzip fruits.zip
```

> ⚠️ Do not upload `kaggle.json` to GitHub because it contains a private Kaggle API key.

---

# ▶️ How to Run the Project

## 1️⃣ Clone Repository

```bash
git clone https://github.com/eko-hrn/Fruit-Image-Classification-with-CNN.git
cd Fruit-Image-Classification-with-CNN
```

---

## 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 3️⃣ Run Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
Submission.ipynb
```

Or run using Google Colab.

---

# 🚀 Model Deployment

## 🔹 TensorFlow SavedModel

Load and use the SavedModel format:

```python
import tensorflow as tf

model = tf.keras.models.load_model("saved_model")

prediction = model.predict(data)

print(prediction)
```

---

## 🔹 TensorFlow Lite (TFLite)

Run inference using TensorFlow Lite Interpreter:

```python
import tensorflow as tf
import numpy as np

interpreter = tf.lite.Interpreter(
    model_path="tflite/model.tflite"
)

interpreter.allocate_tensors()

input_details = interpreter.get_input_details()
output_details = interpreter.get_output_details()

input_data = np.array(data, dtype=np.float32)

interpreter.set_tensor(
    input_details[0]['index'],
    input_data
)

interpreter.invoke()

output_data = interpreter.get_tensor(
    output_details[0]['index']
)

print(output_data)
```

---

## 🔹 TensorFlow.js (TFJS)

Install TensorFlow.js:

```bash
npm install @tensorflow/tfjs
```

Load model in JavaScript:

```javascript
import * as tf from "@tensorflow/tfjs";

const model = await tf.loadLayersModel(
  "tfjs_model/model.json"
);

const prediction = model.predict(inputTensor);

prediction.print();
```

---

# 🧪 Inference Example

The prediction workflow:

1. Load image
2. Resize image
3. Normalize pixel values
4. Convert image into tensor
5. Predict image class
6. Display prediction result

Predicted classes:

- 🍎 Apple
- 🍊 Orange
- 🍐 Pear

---

# 📊 Training Visualization

This project includes:

- Accuracy Plot
- Loss Plot
- Confusion Matrix
- Classification Report

to evaluate model performance and detect overfitting/underfitting.

---

# 👨‍💻 Author

**Eko Hendrawan**

---

# ⭐ Notes

This project was created as part of the **Dicoding Deep Learning Image Classification Submission** using TensorFlow and CNN architecture.
