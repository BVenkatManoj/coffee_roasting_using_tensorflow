# ☕ Coffee Roasting Classification using TensorFlow

<p align="center">
  <img src="coffee-cup.jpg" width="500" alt="Hot Coffee Cup">
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
  <a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.7+-blue.svg" alt="Python 3.7+"></a>
  <a href="https://www.tensorflow.org/"><img src="https://img.shields.io/badge/TensorFlow-2.x-orange.svg" alt="TensorFlow 2.x"></a>
</p>

A binary classification neural network built with TensorFlow/Keras to predict whether a coffee roasting process produces **Good Coffee** ✅ or **Bad Coffee** ❌ based on roasting **Temperature** and **Duration**.

---

## 🎯 Overview

This project implements a simple yet effective neural network to classify coffee roasting quality. Using just two input features (temperature and duration), the model learns to distinguish between successful and unsuccessful roasting conditions.

## 🌟 Features

- ✅ Data preprocessing and feature normalization
- ✅ Binary classification using a 2-layer neural network
- ✅ TensorFlow/Keras implementation
- ✅ Performance evaluation using Accuracy, Precision, and Recall
- ✅ Training and validation loss visualization
- ✅ Probability-based predictions on new roasting conditions
- ✅ Reproducible results with fixed random seeds

## 📊 Dataset

The dataset contains **200 coffee roasting samples** automatically downloaded from Kaggle using KaggleHub.

**Dataset Statistics:**
- **Total Samples:** 200
- **Features:** 2 (Temperature, Duration)
  - Temperature range: 151.32°C - 284.99°C
  - Duration range: 11.51 - 15.45 minutes
- **Classes:** Binary (Good Coffee: 1, Bad Coffee: 0)
- **Expanded Dataset:** 200,000 samples (tiled 1000x for training)

```python
import kagglehub

path = kagglehub.dataset_download("youssefahmed2612/coffee-roasting")
```

**Dataset Source:** [Coffee Roasting Dataset on Kaggle](https://www.kaggle.com/datasets/youssefahmed2612/coffee-roasting)

## 🧠 Model Architecture

A simple feed-forward neural network with the following structure:

```
Input Layer (2 features)
    ↓
Hidden Layer (3 neurons, Sigmoid activation)
    ↓
Output Layer (1 neuron, Sigmoid activation)
```

**Model Parameters:**
- **L1 (Hidden Layer):** 9 parameters (2×3 weights + 3 biases)
- **L2 (Output Layer):** 4 parameters (3×1 weights + 1 bias)
- **Total Trainable Parameters:** 13

## 🛠️ Technologies Used

| Technology | Purpose |
|-----------|---------|
| Python 3.7+ | Programming language |
| TensorFlow / Keras | Deep learning framework |
| NumPy | Numerical computations |
| Pandas | Data manipulation |
| Matplotlib | Visualization |
| KaggleHub | Dataset download |

## 📋 Prerequisites

- Python 3.7 or higher
- Kaggle API credentials (for KaggleHub dataset download)
- GPU support (optional, for faster training)

## 💻 Installation

### Clone the Repository

```bash
git clone https://github.com/BVenkatManoj/coffee_roasting_using_tensorflow.git
cd coffee_roasting_using_tensorflow
```

### Install Dependencies

Using pip:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install tensorflow numpy pandas matplotlib kagglehub
```

### Kaggle API Setup (Required for Dataset Download)

1. Go to [Kaggle Settings](https://www.kaggle.com/settings/account)
2. Click "Create New API Token" to download `kaggle.json`
3. Place it in `~/.kaggle/kaggle.json`
4. Set permissions: `chmod 600 ~/.kaggle/kaggle.json`

## 🚀 Usage

### Run the Jupyter Notebook

```bash
jupyter notebook roasting_coffee.ipynb
```

The notebook covers:

1. **Data Loading:** Download and load the coffee roasting dataset
2. **Exploratory Data Analysis:** Inspect dataset structure and statistics
3. **Feature Preprocessing:** Normalize temperature and duration
4. **Model Definition:** Build the 2-layer neural network
5. **Model Training:** Train on 200,000 samples
6. **Evaluation:** Calculate accuracy, precision, and recall
7. **Visualization:** Plot training/validation loss curves
8. **Predictions:** Make predictions on new roasting conditions

### Quick Prediction Example

```python
import numpy as np

# Normalized input: [Temperature, Duration]
# Example: good roasting conditions
new_roast = np.array([[1.0, 0.5]])  # normalized values

# Make prediction
prediction = model.predict(new_roast)
confidence = prediction[0][0] * 100

print(f"Good Coffee Probability: {confidence:.1f}%")
print(f"Prediction: {'Good ✅' if confidence > 50 else 'Bad ❌'}")
```

## 📈 Results

The model achieves solid performance on the coffee roasting classification task:

| Metric | Performance |
|--------|-------------|
| **Training Accuracy** | 91.2% |
| **Validation Accuracy** | 91.0% |
| **Validation Precision** | 79.1% |
| **Validation Recall** | 79.1% |
| **Model Size** | 13 parameters |
| **Training Time** | ~2 minutes (on GPU) |

The model converges quickly by **Epoch 4** and plateaus thereafter, achieving stable performance. It successfully learns a reasonable decision boundary between good and bad coffee roasting conditions.

### Future Improvements

- Deeper or wider architectures
- Advanced hyperparameter tuning
- Additional feature engineering
- Class balancing techniques if applicable

## 📁 Project Structure

```
coffee_roasting_using_tensorflow/
├── roasting_coffee.ipynb          # Main Jupyter notebook
├── README.md                       # This file
├── requirements.txt                # Python dependencies
├── coffee-cup.jpg                  # Coffee cup image
└── LICENSE                         # MIT License
```

## 🔍 How It Works

1. **Data Normalization:** Features are standardized using TensorFlow's Normalization layer to center them around 0 with unit variance
2. **Neural Network:** The model learns non-linear decision boundaries through sigmoid activations
3. **Training:** Binary cross-entropy loss optimizes the network to separate good from bad coffee batches
4. **Prediction:** The output neuron produces a probability (0-1) indicating likelihood of good coffee

## 📚 Learning Resources

- [Andrew Ng's Machine Learning Specialization](https://www.coursera.org/specializations/machine-learning-introduction) - Inspiration for this project
- [TensorFlow Documentation](https://www.tensorflow.org/api_docs)
- [Keras Sequential Models](https://keras.io/api/models/sequential/)

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs or suggest improvements
- Fork the repository and create pull requests
- Add enhancements like different architectures or optimizers

## 📝 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

This project was inspired by **Andrew Ng's** famous coffee roasting example, used extensively in machine learning education. His passion for making machine learning accessible and engaging through real-world applications is commendable.

Special thanks to the Kaggle community for the coffee roasting dataset!

---

**Happy roasting! ☕🫘** If this project helped you, please consider giving it a ⭐ star!