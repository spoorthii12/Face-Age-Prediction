**_Age Prediction from Facial Images using CNN_**

This project implements an age prediction model using the UTKFace dataset. A Convolutional Neural Network (CNN) is trained to classify facial images into discrete 5-year age intervals ranging from 0–4 to 100+ years. The task is framed as a **multi-class classification problem**.

📂 Dataset
The model uses the [UTKFace dataset](https://susanqq.github.io/UTKFace/) which contains over 23,000 labeled face images in the format:  
`[age]_[gender]_[race]_[date&time].jpg.chip.jpg`  
Each image is processed as a 64x64 grayscale input.

Preprocessing
- Skipped corrupt or unreadable files with error handling
- Resized all images to `64x64x1` format
- Normalized pixel values to `[0, 1]`
- Mapped continuous ages into 21 discrete classes (0–4, 5–9, ..., 100+)

Model Architecture
- 3 convolutional layers with ReLU activation
- Max pooling and dropout layers for regularization
- Fully connected dense layers
- Softmax output layer with 21 classes

Training
- Loss function: `Categorical Crossentropy`
- Optimizer: `Adam`
- Batch size: `128`
- Epochs: `25`
- Evaluation on test split using accuracy and loss metrics

Results
The model achieves consistent classification performance across various age groups and handles imbalanced distribution in the dataset effectively.
