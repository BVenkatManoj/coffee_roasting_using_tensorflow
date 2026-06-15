# ☕ Coffee Roasting Classification using TensorFlow

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/4/45/Coffea_arabica%2C_coffee_beans_.jpg" width="500">
</p>

A binary classification neural network built with TensorFlow/Keras to predict whether a coffee roasting process produces **Good Coffee** or **Bad Coffee** based on roasting **Temperature** and **Duration**.

☕ 🫘 ☕ 🫘 ☕ 🫘 ☕

## Inspiration

This project was inspired by Andrew Ng's famous coffee roasting example used in machine learning education. His enthusiasm for coffee beans made the coffee roasting problem an engaging and intuitive way to learn neural networks, feature normalization, and binary classification with TensorFlow.

## Features

* Data preprocessing and feature normalization
* Binary classification using a neural network
* TensorFlow/Keras implementation
* Performance evaluation using Accuracy, Precision, and Recall
* Training and validation loss visualization
* Prediction on new roasting conditions

## Dataset

The dataset is automatically downloaded from Kaggle using KaggleHub:

```python
import kagglehub

path = kagglehub.dataset_download(
    "youssefahmed2612/coffee-roasting"
)
```

## Model Architecture

* Input Layer: 2 Features (Temperature, Duration)
* Hidden Layer: 3 Neurons with Sigmoid Activation
* Output Layer: 1 Neuron with Sigmoid Activation

## Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib
* KaggleHub

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/coffee-roasting-classification.git
cd coffee-roasting-classification
```

Install dependencies:

```bash
pip install tensorflow numpy pandas matplotlib kagglehub
```

## Usage

Run the notebook or Python script to:

1. Download the dataset
2. Preprocess and normalize features
3. Train the neural network
4. Evaluate performance
5. Make predictions on new roasting conditions

## Results

The model successfully learns the relationship between roasting parameters and coffee quality, producing probability-based predictions for unseen roasting conditions.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
