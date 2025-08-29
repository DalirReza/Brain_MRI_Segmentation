# Brain MRI Segmentation and Cancer Detection
---

## Overview
This project applies a **U-Net model** for brain tumor segmentation from MRI scans. The main idea is to automatically detect and highlight tumor regions, making the process faster and more reliable compared to manual segmentation by doctors.
---

## Dataset
The dataset contains brain MRI scans with **segmentation masks** that label tumor areas.  
- Images were preprocessed (grayscale, resizing to 256×256, normalization).  
- CLAHE and Gaussian blur were used to enhance contrast and improve model performance.  
---
## Method 
- **Model**: Standard U-Net (encoder–bottleneck–decoder structure with skip connections).  
- **Loss Functions**: Tested Dice+Binary Cross Entropy, and Binary Cross Entropy alone.  
- **Training**: Up to 50 epochs with early stopping.  
- **Bonus**: Added an **attention mechanism** in skip connections to focus more on tumor regions.  
---
## Results
Final evaluation on the test set (U-Net, 41 epochs with BCE loss):  
- **IoU**: 0.7734  
- **Dice Coefficient**: 0.8722  
- **Rand Error**: 0.0027  
- **Pixel Error**: 0.0027  
The attention-based U-Net slightly reduced overall accuracy but improved boundary detection, making it more effective in difficult cases.
---
## Key Takeaways
- Preprocessing (CLAHE, normalization) helped improve accuracy over baseline results.  
- Standard U-Net achieved strong segmentation performance.  
- Attention-augmented U-Net improves boundary precision, even if global metrics are slightly lower.  
