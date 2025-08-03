# Polygon UNet Assignment

This repository contains the implementation of a **UNet-based deep learning model** for polygon colorization, created as part of the **Ayna ML Internship Assignment**.

---

## **Overview**

The primary objective of this assignment is:

> Given an outline image of a polygon and a color name, predict the filled polygon image.

We implemented two models:

1. **Image-only UNet**  
   - Input: Polygon outline (RGB image)  
   - Output: Filled polygon image  
2. **Color-conditioned UNet**  
   - Input: Polygon outline (RGB image) + Color name (one-hot encoded)  
   - Output: Filled polygon image with correct color  

The color-conditioned UNet consistently outperforms the image-only model.

---

## **Repository Structure**

```
polygon-unet-assignment/
│
├── final_colab_notebook.ipynb     # Main notebook: training + inference for both models
├── train_unet.py                  # Optional script version
├── unet_imgonly.pth               # Trained image-only model
├── unet_conditioned.pth           # Trained color-conditioned model
├── Insights_Report.pdf            # Summary report (1–2 pages)
└── README.md                      # Documentation (this file)
```

---

## **Setup & Usage**

### 1. Clone the repository
```bash
git clone https://github.com/Soumodip04/polygon-unet-assignment.git
cd polygon-unet-assignment
```

### 2. Open in Google Colab
Open `final_colab_notebook.ipynb` in [Google Colab](https://colab.research.google.com/).

### 3. Upload the dataset
Upload the provided `dataset.zip` to Colab when prompted.

### 4. Training
The notebook:
- Dynamically detects available colors from the dataset
- Trains **image-only UNet**
- Trains **color-conditioned UNet**

### 5. Inference
The notebook also demonstrates:
- How to load trained models
- Run inference
- Visualize results (input, target, predicted images)

---

## **Model Links**

- **Image-only Model:** `unet_imgonly.pth`
- **Color-conditioned Model:** `unet_conditioned.pth`

---

## **W&B Tracking**

All training runs were tracked using [Weights & Biases](https://wandb.ai):

- **Image-only Model Run:**  
  [Run Link](https://wandb.ai/soumoofficial2004-techno-institute-of-engineering-and-ma/polygon_unet_assignment_imgonly/runs/bq0kn3hy)

- **Color-conditioned Model Run:**  
  [Run Link](https://wandb.ai/soumoofficial2004-techno-institute-of-engineering-and-ma/polygon_unet_assignment_conditioned/runs/y0puvi45)

---

## **Results**

### Validation Loss:
- Image-only model: **~0.037**
- Color-conditioned model: **~0.035** (improved performance)

### Qualitative Results:
- The color-conditioned model produces more accurate and consistent filled polygons, especially when multiple colors are involved.

---

## **Key Insights**

- Color conditioning significantly improves model performance.
- Dynamic color detection from `data.json` avoids errors and makes the model robust to new colors.
- W&B was essential for experiment tracking and comparison.

---

## **Future Improvements**

- Data augmentation (rotation, scaling)
- Use perceptual loss (VGG-based) for sharper results
- Experiment with transformer-based image-to-image architectures

---

## **Author**

**Soumodip Das**  
[GitHub Profile](https://github.com/Soumodip04)

---

## **Acknowledgments**

- **Dataset:** Provided by Ayna for the ML Internship Assignment  
- **Frameworks:** PyTorch, Weights & Biases, Google Colab  
