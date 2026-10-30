# 👟 Nike vs Adidas Image Classification Using Deep Learning

## 📌 Project Overview

This project focuses on building a Deep Learning-based Image Classification model using a **Convolutional Neural Network (CNN)** to distinguish between Nike and Adidas images.

The model is developed using Python and Keras. It processes input images, extracts important visual features using convolutional layers, and predicts whether an image belongs to the Nike or Adidas category.

The main objective of this project is to understand how Deep Learning and CNNs can be used for image classification tasks.

## 🎯 Project Objectives

- Understand the fundamentals of Deep Learning.
- Learn how Convolutional Neural Networks (CNNs) work.
- Perform image preprocessing using Python.
- Build and train a CNN model.
- Classify images into Nike and Adidas categories.
- Make predictions on new images using the trained model.

## 🛠️ Technologies & Libraries Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| NumPy | Numerical operations and array manipulation |
| TensorFlow / Keras | Building and training the CNN model |
| CNN | Image feature extraction and classification |
| Matplotlib | Image visualization |
| PIL (Pillow) | Image loading and preprocessing |
| tqdm | Displaying training data processing progress |
| OS | File and directory handling |

## 🧠 Deep Learning Model Architecture

This project uses a **Convolutional Neural Network (CNN)** with the following architecture:

1. Input Layer
   - Image size: 120 × 120 pixels
   - Grayscale images
   - 1 input channel

2. First Convolution Block
   - Conv2D (32 filters, 5 × 5 kernel)
   - Conv2D (32 filters, 5 × 5 kernel)
   - MaxPooling2D (2 × 2)

3. Second Convolution Block
   - Conv2D (64 filters, 5 × 5 kernel)
   - Conv2D (64 filters, 5 × 5 kernel)
   - MaxPooling2D (2 × 2)

4. Third Convolution Block
   - Conv2D (64 filters, 5 × 5 kernel)
   - Conv2D (64 filters, 5 × 5 kernel)
   - MaxPooling2D (2 × 2)

5. Flatten Layer
   - Converts extracted feature maps into a one-dimensional vector.

6. Fully Connected Layer
   - Dense Layer with 512 neurons.
   - ReLU activation function.

7. Output Layer
   - Dense Layer with 2 neurons.
   - Softmax activation function.
   - Predicts Nike or Adidas.

### Model Compilation

The model is compiled using:

- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Evaluation Metric: Accuracy
- Training Epochs: 10

## 📂 Project Structure

```text
DeepLearning-Nike-vs-Adidas-Image-Classification/
│
├── deeplearning_imagedetection_project_(2).ipynb
│
├── train/
│   ├── NIKE_image1.jpg
│   ├── NIKE_image2.jpg
│   ├── ADIDAS_image1.jpg
│   └── ADIDAS_image2.jpg
│
├── test/
│   └── Test images
│
└── README.md
```

**Note:** The notebook defines both train and test directories, but the current implementation only loads the training directory. The test directory is not yet used for model evaluation.

## ⚙️ Project Workflow

### Step 1: Import Libraries

Import the required Python libraries, including NumPy, Matplotlib, PIL, tqdm, and Keras.

### Step 2: Dataset Loading

Load images from the training directory.

The dataset contains two image categories:

- Nike
- Adidas

The current notebook successfully loads 100 training images.

### Step 3: Image Preprocessing

Each image goes through the following preprocessing steps:

- Load the image using PIL.
- Convert the image into grayscale.
- Resize the image to 120 × 120 pixels.
- Convert the image into a NumPy array.
- Assign the appropriate category label.

### Step 4: Image Labeling

The project uses a custom function called `label_image()`.

Labels are assigned using one-hot encoding:

- Nike → [1, 0]
- Adidas → [0, 1]

### Step 5: CNN Model Creation

Create a Sequential CNN model using convolutional layers, max-pooling layers, flattening, and dense layers.

### Step 6: Model Training

The model is trained using the prepared image dataset.

Training configuration:

- Epochs: 10
- Optimizer: Adam
- Loss: Categorical Crossentropy

### Step 7: Image Prediction

Load a new image, apply the same preprocessing steps, and pass it to the trained model.

The model produces two probabilities:

- Nike probability
- Adidas probability

The category with the higher probability is the predicted class.

## 📊 Training Results

The notebook's final training epoch produced the following results:

| Metric | Result |
|---|---|
| Training Epochs | 10 |
| Training Images | 100 |
| Final Training Accuracy | 75% |
| Final Training Loss | 0.4882 |
| Optimizer | Adam |

**Important:** The 75% accuracy is training accuracy, not test accuracy. The notebook does not currently include a separate validation or test evaluation.

## 🔍 Sample Prediction

The notebook also tests the trained model on a sample image named `niketest.webp`.

The model returned:

```python
array([[0.6316, 0.3684]])
```

Interpretation:

- Nike probability: 63.16%
- Adidas probability: 36.84%

**Predicted Category: Nike**

## 🚀 How to Run This Project

### Option 1: Using Google Colab

1. Open Google Colab.
2. Upload the Jupyter Notebook.
3. Upload your dataset to Google Colab.
4. Organize your images into `train` and `test` folders.
5. Update the dataset paths in the notebook if necessary.
6. Run all notebook cells.
7. Upload a new image to test the prediction.

### Option 2: Using Jupyter Notebook Locally

**Step 1: Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/DeepLearning-Nike-vs-Adidas-Image-Classification.git
```

**Step 2: Navigate to the project directory**

```bash
cd DeepLearning-Nike-vs-Adidas-Image-Classification
```

**Step 3: Install the required libraries**

```bash
pip install numpy matplotlib pillow tqdm tensorflow jupyter
```

**Step 4: Start Jupyter Notebook**

```bash
jupyter notebook
```

**Step 5: Open and run the notebook**

Open `deeplearning_imagedetection_project_(2).ipynb` and execute the cells.

**Note:** Update the image directory paths in the notebook according to your local dataset location.

## 💡 Key Learnings

Through this project, I learned:

- Basics of Deep Learning and CNN.
- Image preprocessing using PIL.
- Converting images into NumPy arrays.
- One-hot encoding for classification.
- Building CNN architectures using Keras.
- Training a neural network.
- Making predictions on new images.

## 🔮 Future Improvements

Some possible improvements for this project are:

- Increase the size of the training dataset.
- Add a proper train-validation-test split.
- Evaluate the model using test accuracy.
- Implement data augmentation.
- Normalize image pixel values.
- Save the trained model for future predictions.
- Create a simple web application using Streamlit or Flask.
- Extend the model to recognize additional brands.

## 👨‍💻 Author

**Your Name**

GitHub: https://github.com/YOUR_USERNAME

## ⭐ Support

If you find this project useful or interesting, consider giving this repository a star!

Thank you for visiting my project! 🚀


## 3. Important improvements before uploading to GitHub
I noticed a few things in your notebook that you should consider improving.
Area	Current status	Suggested improvement
Dataset	100 training images	Increase dataset size
Accuracy	75% training accuracy	Evaluate on unseen images
Test dataset	Not implemented	Add model evaluation
Image normalization	Not implemented	Normalize pixel values
Model saving	Not implemented	Save model as .keras
Project name	Image Detection	Use Image Classification

One important technical point: Your project is technically an Image Classification project, not Object Detection. It predicts which brand an image belongs to; it does not locate objects using bounding boxes.

## 4. Recommended files for your GitHub repository
   DeepLearning-Nike-vs-Adidas
        deeplearning_imagedetection_project_(2).ipynb  
        README.md
        train/
        test/
