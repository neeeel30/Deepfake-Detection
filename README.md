# DeepfakeDetection

This project is a web application that uses a deep learning model to classify images, utilizing React for the frontend and Flask for the backend. The project leverages TensorFlow for model training and inference.

## Features

- **Frontend**: Built with React, offering an interactive and user-friendly interface.
- **Backend**: Powered by Flask, providing a RESTful API for model predictions.
- **Machine Learning**: Implements a TensorFlow model for deepfake image classification.
- **Data Handling**: Uses TensorFlow's data pipeline for efficient data loading and preprocessing.
- **Visualization**: Integrates Matplotlib for visualizing data and model performance.

## Prerequisites

To run this project, you need the following:

- Python 3.x
- Node.js and npm
- TensorFlow
- Flask
- React

## Installation

### Backend (Flask)

1. **Clone the repository**:
    ```bash
    git clone https://github.com/neeeeel30/Deepfake-Detection.git
    cd tisbproject/backend
    ```

2. **Set up a virtual environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Run the Flask server**:
    ```bash
    flask run
    ```

### Frontend (React)

1. **Navigate to the frontend directory**:
    ```bash
    cd ../frontend
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Start the React development server**:
    ```bash
    npm start
    ```

## Usage

1. Make sure both the backend and frontend servers are running.
2. Access the application via `http://localhost:3000` in your web browser.
3. Use the interface to upload images and view classification results.

## TensorFlow Model

The application uses a TensorFlow model for deepfake image classification.

### Preprocessing

The data is prepared for model training by scaling pixel values between 0 and 1. This normalization step is crucial for improving the performance and convergence of the neural network. The dataset is then split into training, validation, and test sets to evaluate model performance effectively:


def preprocess_images(data):
    data = data.map(lambda x, y: (x / 255.0, y))
    return data

# Apply preprocessing
train_data = preprocess_images(train_data)
val_data = preprocess_images(val_data)
test_data = preprocess_images(test_data)

### Model Architecture

The deep learning model is constructed using TensorFlow's Keras API. The model is designed to efficiently classify images into predefined categories. Here’s a basic example of a convolutional neural network (CNN) used for image classification:

### Data Visualization

To gain insights into the data and model performance, Matplotlib is used for visualization. It helps in understanding the distribution of the data and evaluating model predictions:



