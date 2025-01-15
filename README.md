# Adobe Challenge: Image Classification and Artifact Detection

## 📖 Introduction
Deepfakes—manipulated media that closely mimic real content—pose significant threats to digital trust. Detecting these fakes becomes even more challenging when the images are small in resolution.

This project focuses on:
- **Deepfake detection**
- **Artifact explanation generation**

The target dataset consists of 32x32-sized images altered by artifact injections from sources such as **Stable Diffusion**, **Adobe Firefly**, and **GANs**.

## 🚀 Approach

### 1. **Upscaling Low-Resolution Images**
To address the challenge of small image sizes, we:
- Fine-tuned **Real-ESRGAN_x4** on real images from **ImageNet**.
- Upscaled 32x32 images to 128x128 for better feature extraction.

### 2. **Image Classification**
- The upscaled images are fed into **DenseNet121**.
- Achieved **98% classification accuracy**, with significant robustness against adversarial perturbations.

### 3. **Artifact Detection and Explanation**
- Dataset divided into two main classes:
  - **Biological**: Artifacts mimicking natural elements.
  - **Mechanical**: Artifacts with synthetic or machine-like features.
- **Grad-CAM** applied to highlight artifact-affected regions for precise manipulation identification.

### 4. **Vision-Language Model (VLM)**
- Processed Grad-CAM outputs to focus on critical features.
- Generated explanations for detected artifacts, enhancing the interpretability and performance of the VLM.

## 📊 Results
- **Classification Accuracy**: 98%
- **Enhanced Artifact Detection**: By grouping images into Biological and Mechanical classes, the detection accuracy significantly improved.
- 
## 📂 Dataset Details
- **Sources**: Stable Diffusion, Adobe Firefly, GAN-generated images.
- **Resolution**: Original images at 32x32.

## 🛠️ Tools and Technologies
- **Real-ESRGAN_x4**: For image upscaling.
- **DenseNet121**: For image classification.
- **Grad-CAM**: For visualizing artifact-affected regions.
- **Vision-Language Model (VLM)**: For artifact explanation generation.
- **ImageNet**: For training the upscaling model.

## 💡 Key Highlights
- Combines **image upscaling**, **classification**, and **artifact explanation**.
- Effective on low-resolution images (32x32).
- High classification accuracy (98%) with robust detection capabilities.
- Grad-CAM improves interpretability and VLM performance.

## 📝 How to Use
1. **Preprocessing**:
   - Input images (32x32) are passed through Real-ESRGAN_x4 for upscaling to 128x128.
2. **Classification**:
   - Upscaled images are fed into DenseNet121 for class prediction.
3. **Artifact Detection**:
   - Grad-CAM highlights manipulated regions.
4. **Explanation Generation**:
   - Grad-CAM outputs are processed by the Vision-Language Model for generating artifact explanations.

## 📈 Performance Metrics
- **Accuracy**: 98%
- **Robustness**: Significant resilience against adversarial attacks.
- **Improved Interpretability**: Enhanced by Grad-CAM and VLM integration.
### 🔗 References
- [Real-ESRGAN GitHub](https://github.com/xinntao/Real-ESRGAN)
- [DenseNet121 Paper](https://arxiv.org/abs/1608.06993)
- [Grad-CAM Paper](https://arxiv.org/abs/1610.02391)

