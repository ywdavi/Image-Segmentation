# Segmentation of Aerial Images for Drone Landing Detection

## Description
This project aims to detect safe drone landing zones through the segmentation of aerial images. Using deep learning models such as UNet and PSPNet, we segment aerial imagery from the Semantic Drone Dataset to identify various terrain types. The goal is to accurately distinguish between safe and unsafe landing areas based on the segmented images.

## Objectives
- Develop deep learning models for semantic segmentation of aerial images.
- Detect and classify various terrain types from aerial views to identify safe landing zones for drones.
- Fine-tune models like UNet and PSPNet for improved segmentation performance.

## Key Steps

### Data Preparation
- **Dataset:** Used the Semantic Drone Dataset, consisting of 400 high-resolution aerial images and corresponding ground truth segmentation masks.
- **Data Augmentation:** Applied transformations such as horizontal flip, vertical flip, and 90-degree rotations to improve model robustness.
- **Image Preprocessing:** Resized images to 256x256 pixels, normalized them, and used data loaders for efficient training.

### Models
- **UNet:** A convolutional network with an encoder-decoder structure and skip connections to preserve spatial resolution during segmentation.
- **Fine-tuned UNet:** Improved the UNet by using a ResNet-50 backbone pretrained on ImageNet, fine-tuned to improve segmentation accuracy.
- **Fine-tuned PSPNet:** Implemented PSPNet, which uses a pyramid pooling module to capture both local and global context information for more accurate scene parsing.

### Modeling and Training
- Models were trained over 100 epochs, using the Adam optimizer and CrossEntropyLoss for the basic UNet, while Dice Loss was used for the fine-tuned models.
- Evaluated models based on mean Intersection over Union (mIoU), Dice coefficient, and pixel-wise accuracy to assess segmentation performance.

### Drone Landing Detection
- Developed an algorithm to find safe landing zones by identifying "safe" and "avoid" classes within the segmented images.
- Used Euclidean distance transforms to ensure that landing spots are far from obstacles and image borders.
  
## Results
- **Best Model:** The fine-tuned UNet achieved the highest mIoU of 58.01%, providing the most accurate segmentations, particularly for complex terrain types like buildings and vegetation.
- **Landing Detection:** The algorithm reliably identified safe landing spots in test images, demonstrating its potential for real-world applications.

## Conclusion
This project successfully demonstrated the use of deep learning for semantic segmentation of aerial images and the detection of safe drone landing zones. The fine-tuned UNet model performed best, offering precise segmentation and reliable landing spot detection.

