# Vegetation-Segmentation-using-U-Net-TensorFlow-
To build a deep learning system that identifies vegetation regions in images using pixel-wise segmentation

This project performs **binary semantic segmentation** to detect vegetation from drone or satellite images.  
The dataset is downloaded from **Roboflow** (YOLO polygon format) and is converted into **U-Net friendly masks** before training.

---

##  Project Overview

This project:

- Downloads dataset from Roboflow  
- Converts YOLO polygon annotations → binary mask images  
- Prepares data for U-Net (256×256 RGB images)  
- Builds and trains a U-Net model for segmentation  
- Evaluates the model using **Dice Score** and **IoU (Intersection over Union)**  
- Displays prediction results  

All code is rewritten, structured and commented for clarity.

---

##  Dataset

- Source: **Roboflow**
- Type: YOLOv11 polygon annotations
- Classes:  
  - **0 → Background**  
  - **1 → Vegetation**
- Images are resized to **256×256**
- Masks are converted to **binary segmentation masks**

---

##  Project Structure
unet_data/
├── images/ → processed RGB images (256x256)
└── masks/ → processed binary masks (256x256)

---

##  Features

- YOLO polygon → mask image converter  
- Custom U-Net implementation  
- Training + validation split  
- Dice score and IoU implemented manually  
- Visualization of final results  

---

##  Technologies Used

- Python  
- TensorFlow / Keras  
- OpenCV  
- NumPy  
- Torch (for metrics only)  
- Matplotlib  

---

##  Model Architecture (U-Net)

- Encoder with 32 → 64 → 128 → 256 filters  
- Bottleneck layer  
- Decoder with skip connections  
- Final 1×1 sigmoid output for binary segmentation  

---

##  Metrics (Expected Results)

| Metric | Score |
|--------|--------|
| Dice Coefficient | ~0.92 – 0.94 |
| IoU | ~0.86 – 0.88 |

---

##  Example Output

The script visualizes:

- Input Image  
- Ground Truth Mask  
- U-Net Prediction  

---

##  How to Run

1. Install dependencies:
pip install tensorflow roboflow torch torchvision scikit-learn opencv-python matplotlib

2. Run the full script:


---

##  Future Improvements
- Deploy with Streamlit / FastAPI  

---

##  License

This project is open-source and free to use for research & learning.

---

##  Acknowledgements

- Roboflow for dataset hosting  
- U-Net originally proposed by **Olaf Ronneberger et al.**  

