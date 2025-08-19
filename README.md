# AI-Power-Tool-for-Image-and-Video-Labelling
This project is a AI-Powered Tool for Image and Video Labelling toolkit that combines the power of deep learning with an interactive GUI to make CT scan analysis more accessible and reliable. The motivation came from a simple but impactful question: How can we assist radiologists in identifying lung disease regions faster and with more consistency?


# 🫁 Lung Disease Segmentation Toolkit

This project is a **PyTorch + PyQt5 based medical imaging toolkit** for semi-automatic **lung disease segmentation from CT scans**. It combines a custom deep learning pipeline with an interactive GUI for annotation, training, inference, and evaluation.  

## ✨ Features
- **Interactive Annotation GUI**  
  - Polygon & Freehand (pencil) drawing modes  
  - Undo / reset functionality  
  - Save annotations as JSON (normalized to 256×256 for consistency)  
  - Convert annotations into **mask images** (`.png`, `.npy`)  

- **Mask Generation & Training**  
  - Automatically generate masks from embedded green-box annotations  
  - Train a segmentation model directly from generated masks  
  - Models saved as `.pth` checkpoints under `checkpoints/`  

- **Inference & Visualization**  
  - Temporal inference across CT sequences for consistent predictions  
  - **Live preview overlays** on original CT images  
  - Heatmap visualization of model predictions (Jet colormap, adjustable alpha)  
  - Quantitative evaluation: **Dice, IoU, Precision, Accuracy**  

- **Batch Evaluation & Automation**  
  - Run evaluations across entire datasets  
  - Logging of temporal inference results (`logs/`)  
  - Fully automated pipelines with consistent environment execution  

## 🖥️ Tech Stack
- **Deep Learning**: PyTorch, Torchvision, Torchaudio  
- **Classical Imaging**: OpenCV, scikit-image, Pillow  
- **Evaluation**: NumPy, SciPy, scikit-learn  
- **GUI**: PyQt5, PyQtWebEngine  
- **Visualization**: Matplotlib, Seaborn, Plotly  

## 📂 Project Structure
```
├── annotation_gui.py          # Main PyQt5 GUI  
├── generate_masks_from_embedded_boxes.py  
├── temporal_inference.py      # Temporal consistency inference  
├── inference_eval.py          # Evaluation & overlay utilities  
├── checkpoints/               # Trained model checkpoints (.pth)  
├── data/  
│   ├── raw/                   # Input CT scans  
│   ├── annotations/           # JSON annotations  
│   ├── masks_png/             # Converted masks (visual)  
│   ├── masks_npy/             # Converted masks (array format)  
└── logs/                      # Temporal inference logs  
```

## 🚀 How to Use
1. **Launch GUI**
   ```bash
   python annotation_gui.py
   ```
   - Select raw CT images from data/raw/  
   - Annotate with polygon or freehand tools  
   - Save JSON annotations  

2. **Generate Masks & Train**
   - Use the **“Generate Masks and Train Model”** button to prepare masks & train  
   - Models saved to checkpoints/test_cases_segmentor.pth  

3. **Run Inference**
   - Enable **Show Model Prediction**  
   - Select model checkpoint  
   - Use **Predict and Overlay** or **Temporal Inference**  

4. **Evaluate Performance**
   - Switch GT source (NPY/PNG/JSON)  
   - Run evaluation for Dice, IoU, Precision, Accuracy  
   - Or use **Batch Evaluation** for entire datasets  

## 🌟 Motivation
This project was built to explore how **AI-driven tools can assist radiologists** by speeding up lung disease segmentation, improving diagnostic consistency, and enabling scalable annotation pipelines.  

If even one radiologist saves time or one diagnosis becomes more reliable because of this tool, then every challenge in building it was worth it.  
