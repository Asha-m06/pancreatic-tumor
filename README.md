# Pancreatic Tumor Segmentation Using a CNN-GNN Hybrid Model

## Overview

Pancreatic cancer is a serious disease for which accurate analysis of medical images can support research into early detection and tumor assessment. This project explores automated pancreatic tumor segmentation from CT scan images using a hybrid deep-learning architecture that combines **EfficientNet-B3** and a **Graph Attention Network (GAT)**.

The system processes 3D NIfTI CT volumes by extracting 2D axial slices and applying image preprocessing, data augmentation, feature extraction, and tumor segmentation techniques. Grad-CAM-based visualizations are also used to help interpret model predictions.

This project is developed as an academic research prototype for medical image analysis.

## Live Demo

**Application:** [Open the pancreatic tumor segmentation application](YOUR_PUBLIC_DEPLOYED_URL)

> Replace `YOUR_PUBLIC_DEPLOYED_URL` with your actual public deployment URL. `http://localhost:8501/` is a local address and cannot be accessed by other users. If the application is not deployed yet, you can remove this link temporarily.

## Key Features

- **3D-to-2D slice extraction:** Converts 3D NIfTI CT volumes into 2D axial slices for slice-based model processing.
- **Image preprocessing:** Includes CT windowing, normalization, contrast enhancement, and region-of-interest (ROI) extraction.
- **Data augmentation:** Applies image transformations to improve model robustness.
- **EfficientNet-B3 feature extraction:** Uses a pretrained CNN to extract image features.
- **Graph Attention Network:** Uses graph-based attention to learn relationships between extracted features.
- **Tumor segmentation:** Predicts tumor and background regions in CT image slices.
- **Model interpretability:** Uses Grad-CAM-based visualizations to examine model attention.
- **Performance evaluation:** Uses Dice score, Intersection over Union (IoU), precision, recall, and F1-score.

## Model Architecture

The project combines convolutional feature extraction with graph-based feature learning.

1. **Input:** 3D NIfTI CT volume and its corresponding tumor mask.
2. **Slice extraction:** Extracts 2D axial slices from the volume.
3. **Preprocessing:** Applies CT windowing, normalization, contrast enhancement, and ROI extraction.
4. **Feature extraction:** EfficientNet-B3 extracts features from the preprocessed image.
5. **Graph construction:** Represents relevant feature relationships in a graph.
6. **Graph learning:** A Graph Attention Network learns relationships between graph features.
7. **Segmentation:** Produces predictions for tumor and background regions.
8. **Interpretability:** Grad-CAM-based visualizations help inspect model attention.
9. **Evaluation:** Compares predicted segmentation masks with ground-truth masks using segmentation metrics.

**Note:** The workflow uses 2D slices extracted from 3D CT volumes; it should not be described as full 3D neural-network segmentation unless a 3D model is actually implemented.

## Dataset

The project uses CT volumes and corresponding tumor segmentation masks.

Medical imaging data may be stored in NIfTI formats such as `.nii` and `.nii.gz`. Each volume is associated with a corresponding mask that identifies the target tumor region.

The dataset and its annotations must be obtained from an appropriate source and used according to the applicable license, terms of use, and privacy requirements.

**Important:** Add the actual dataset name and source link here after verifying them. Do not publish restricted datasets or identifiable patient information in the repository.

## Preprocessing

The preprocessing pipeline prepares medical images for model training and evaluation.

- **CT windowing:** Adjusts image intensity values to emphasize relevant tissue structures.
- **Normalization:** Standardizes image intensity values.
- **Contrast enhancement:** Improves the visibility of image structures where appropriate.
- **ROI extraction:** Focuses processing on a relevant image region.
- **2D slice extraction:** Extracts axial slices from 3D CT volumes and pairs them with the corresponding mask slices.
- **Data augmentation:** Applies selected image transformations to improve robustness.

The exact preprocessing operations should match the implementation in the source code.

## Model Training and Evaluation

The model combines EfficientNet-B3 feature extraction with GAT-based graph learning for tumor segmentation.

The following metrics can be used to evaluate segmentation quality:

- **Dice score:** Measures overlap between the predicted tumor mask and the ground-truth mask.
- **Intersection over Union (IoU):** Measures the intersection relative to the union of the two masks.
- **Precision:** Measures the proportion of predicted tumor pixels that are actually tumor pixels.
- **Recall:** Measures the proportion of ground-truth tumor pixels correctly identified.
- **F1-score:** Combines precision and recall into a single measure.

Report your actual validation and test results separately. Do not present validation results as test results.

## Project Structure

Update this example to match the actual files and folders in your GitHub repository.

```text
pancreatic-tumor-segmentation/
├── README.md
├── requirements.txt
├── app.py
├── notebooks/
│   └── training_notebook.ipynb
├── src/
│   ├── preprocessing.py
│   ├── model.py
│   └── evaluation.py
└── outputs/
    └── visualizations/
```

The filenames above are examples. Remove entries that do not exist in your repository and add the actual filenames you use.

## Installation

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd YOUR_REPOSITORY_FOLDER
```

Replace the placeholders with your repository URL and folder name.

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

On Windows:

```bash
venv\Scripts\activate
```

On Linux or macOS:

```bash
source venv/bin/activate
```

### 4. Install dependencies

If the repository contains a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Use the package versions compatible with your implementation and hardware. Graph-related packages may require installation compatible with your PyTorch version.

## Usage

### Run the web application

If your application is built using Streamlit and the entry-point file is `app.py`, run:

```bash
streamlit run app.py
```

Open the local address displayed in the terminal, usually:

```text
http://localhost:8501/
```

If your application uses a different filename, replace `app.py` with the correct filename.

### Run the notebook

If the project includes a Jupyter Notebook:

1. Open the notebook in Jupyter.
2. Configure the dataset paths.
3. Install the required dependencies.
4. Execute the notebook cells in order.
5. Review the generated predictions, visualizations, and evaluation metrics.

## Explainability

Grad-CAM-based visualizations are included to help examine which image regions influence the model's activations or predictions.

These visualizations can support qualitative inspection of model behavior. They do not independently prove that a prediction is correct or provide clinical validation.

## Limitations

- The model's performance depends on the dataset, annotations, preprocessing, and training configuration.
- Processing 2D slices does not directly model all spatial relationships across an entire 3D volume.
- Medical imaging datasets may have limited sample sizes or differences in acquisition protocols.
- Explainability visualizations can be imperfect and should be interpreted carefully.
- The system has not been established as a clinically validated diagnostic tool.

## Future Scope

Potential extensions include:

- Exploring full 3D segmentation architectures.
- Evaluating generalization across independent datasets.
- Improving segmentation of small or difficult-to-identify tumors.
- Comparing alternative CNN and graph neural network architectures.
- Improving visualization and model interpretability.
- Evaluating the model with carefully designed patient-level testing.

## Disclaimer

This project is intended for academic and research purposes only. It is not intended to replace professional medical advice, diagnosis, or treatment.

## Author

Asha M

- GitHub: (https://github.com/Asha-m06)
- Project Repository: (http://localhost:8501/)
