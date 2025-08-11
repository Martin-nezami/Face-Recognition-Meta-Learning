# Face Recognition Using Meta-Learning

## Overview
This project implements a face recognition system using Model-Agnostic Meta-Learning (MAML). The system is designed to recognize individuals from facial images by leveraging meta-learning techniques. The goal is to enable the model to quickly adapt to new face recognition tasks with minimal training data.


## Project Structure
The project is structured as follows:

1. **Data Loading and Preprocessing**: Reads facial images from the ORL Faces dataset, prepares pairs of genuine (same person) and impostor (different person) images, and splits them into training and testing sets.

2. **Siamese Neural Network**: Implements a Siamese network architecture to learn embeddings for facial images. It includes convolutional layers, pooling layers, dropout for regularization, and dense layers for feature extraction.

3. **Model-Agnostic Meta-Learning (MAML)**: Utilizes MAML to train the Siamese network across multiple face recognition tasks. MAML facilitates fast adaptation to new tasks by updating the model parameters based on support and query sets from each task.

4. **Training Loop**: Implements the meta-training loop where batches of tasks are sampled. For each task, support and query sets are used to update the model via the inner loop (task-specific adaptation) and compute gradients for the outer loop (meta-update).

5. **Evaluation**: Evaluates the meta-learned model on the test dataset by calculating accuracy, generating confusion matrices, and visualizing sample predictions. It also computes precision, recall, F1-score, and support for detailed performance analysis.



## Setup and Installation
### Prerequisites

- ```Python 3.x
- ``pip (Python package installer)``

### Required Libraries
Install the necessary libraries using pip:  
```bash
pip install numpy tensorflow matplotlib pillow scikit-learn
```


## Implementation Details
### Data Loading
The ORL Faces dataset is used for face recognition tasks. Images are preprocessed into pairs of genuine and impostor sets, normalized, and split into training and testing sets.

### Siamese Neural Network
The base network architecture extracts features from facial images. It includes convolutional layers for feature extraction, pooling layers for dimensionality reduction, and dropout layers for regularization.

### Model-Agnostic Meta-Learning (MAML)
MAML is applied to facilitate rapid adaptation to new face recognition tasks. It involves an inner loop for task-specific adaptation (updating weights) and an outer loop for meta-update across tasks using RMSprop optimizer.

### Training Loop
The meta-training loop runs for multiple epochs, sampling batches of tasks. Each task batch undergoes inner updates to adapt the model, followed by outer updates to refine model parameters based on meta-gradients.

### Evaluation and Analysis
The trained model is evaluated on the test dataset to assess its face recognition performance. Metrics such as accuracy, confusion matrix, precision, recall, F1-score, and support are computed and visualized to analyze model effectiveness.

## Running the Code
To run the project, ensure Python and the required libraries are installed. Adjust paths and parameters as necessary for your environment and dataset location.
```python
``Final Project\Face Recognition.ipynb"``
```


## Results and Visualizations
Results include meta-training loss trends over epochs, training/validation accuracy, and loss plots. Visualizations such as confusion matrices and sample image predictions provide insights into model performance and behavior.

## Conclusion
This project demonstrates the application of Model-Agnostic Meta-Learning (MAML) to enhance face recognition tasks. By leveraging meta-learning techniques, the model achieves efficient adaptation to new tasks with minimal training data, offering promising results in face recognition applications.