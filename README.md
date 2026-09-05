# Face Blurring for Privacy Protection

A computer-vision pipeline that detects human faces in images and automatically anonymizes them using Gaussian blur.

The project demonstrates an end-to-end privacy-preservation workflow using OpenCV, including face detection, image preprocessing, anonymization, evaluation, and performance analysis.

## Features

* Haar Cascade face detection
* Image preprocessing and histogram equalization
* Gaussian face anonymization
* Multiple-face handling
* Quantitative detection evaluation using IoU
* Precision, recall, and F1-score
* Processing-time measurement
* Qualitative analysis of successful and failed detections


## Approach

The pipeline follows four main stages:

```text
Input Image
     ↓
Preprocessing
     ↓
Face Detection
     ↓
Face Blurring
     ↓
Protected Image
```

Face detection is performed using OpenCV's Haar Cascade classifier. Detected face regions are then blurred using a Gaussian filter.

## Evaluation

The system was evaluated on a subset of the **WIDER FACE validation dataset** using ground-truth face bounding boxes.

Evaluation includes:

* Intersection over Union (IoU)
* True positives
* False positives
* False negatives
* Precision
* Recall
* F1-score
* Detection time

The baseline evaluation achieved:

| Metric    | Result |
| --------- | -----: |
| Precision | 74.26% |
| Recall    |  8.15% |
| F1-score  | 14.69% |

The results demonstrate reasonable precision but limited recall, particularly in crowded and difficult scenes. This highlights the limitations of traditional Haar Cascade detection and provides a baseline for future improvements.

## Limitations

The current implementation uses a traditional Haar Cascade detector. Performance can decrease significantly with:

* Small faces
* Non-frontal faces
* Occlusion
* Crowded scenes
* Difficult lighting conditions

The project therefore represents a **baseline privacy-preservation system**, rather than a production-ready face anonymization solution.

A future version could replace the Haar Cascade detector with a modern deep-learning-based face detector.

## Dataset

The evaluation uses the WIDER FACE validation dataset.

The dataset is **not included in this repository**. Users should download it from the official WIDER FACE source and comply with its licensing requirements.

## Running the Project

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Then run the notebooks in order:

1. `01_Face_Blurring_Pipeline.ipynb`
2. `02_Face_Blurring_Evaluation.ipynb`

The notebooks demonstrate the complete pipeline and its evaluation.

## Technologies

* Python
* OpenCV
* NumPy
* Matplotlib
* Jupyter Notebook
* WIDER FACE
