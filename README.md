
# 🧠 Brain Tumor Classifier using CNN and Gradio

This project is a deep learning-based image classification model built with TensorFlow and deployed with Gradio. It classifies brain tumor images into one of the following four categories:

- **Glioma**
- **Meningioma**
- **No Tumor**
- **Pituitary**

---

## 📁 Project Structure

```
brain_tumor_classifier/
├── model_training_and_app.py     # Main Python script (the code you provided)
├── README.md                     # Project documentation
└── Brain Tumor Dataset/
    └── Training/
        ├── glioma/
        ├── meningioma/
        ├── notumor/
        └── pituitary/
```

---

## 🛠️ Requirements

You will need the following Python packages:

```bash
pip install tensorflow opencv-python numpy scikit-learn gradio
```

If you're running in **Google Colab**, you can skip the installation as most packages are pre-installed.

---

## 📌 Dataset

- The dataset should be organized as:

```
/Training/
    /glioma/
    /meningioma/
    /notumor/
    /pituitary/
```

- Each folder should contain images belonging to that specific class.

You can mount your Google Drive in Colab to access the dataset:

```python
from google.colab import drive
drive.mount('/content/drive')
```

---

## 🧠 Model Architecture

The model is a CNN composed of:

- Multiple `Conv2D` layers for feature extraction
- `MaxPooling2D` for downsampling
- `BatchNormalization` for faster convergence
- `GlobalAveragePooling2D` to reduce the spatial dimensions
- Fully connected `Dense` layers with `Dropout` for regularization

---

## 🚀 How to Run

1. **Upload your dataset** to Google Drive.
2. **Update the `DATASET_PATH`** variable in the script to your actual dataset location.
3. Run the script in a Python environment or Google Colab.

```bash
python model_training_and_app.py
```

4. A Gradio web interface will launch. Use it to upload images and see the predicted class.

---

## 🌟 Gradio Interface

- **Input**: Upload a brain MRI image.
- **Output**: Predicted tumor category (one of glioma, meningioma, notumor, or pituitary).

---

## 📈 Model Training

- Image size: 128x128
- Batch size: 16
- Epochs: 10
- Optimizer: Adam
- Loss function: Categorical Crossentropy

---

## 📤 Prediction Function

Each uploaded image is:
- Resized to 128x128
- Normalized (divided by 255)
- Passed through the trained CNN model
- Output is decoded to the class label using `LabelBinarizer`

---

## 📬 Future Improvements

- Save/load the model using `model.save()` and `load_model()`
- Add early stopping and learning rate scheduling
- Use data augmentation to improve generalization
- Deploy on Hugging Face Spaces or as a standalone web app

---

## 🧑‍💻 Author

This project was implemented using TensorFlow and Gradio, and trained using a labeled dataset from Google Drive.
