# Week 3 – U-Net Model Training and Evaluation

## Objective

The objective of Week 3 was to develop a deep learning segmentation model for coronary artery calcium detection. A U-Net model was trained using the CT image-mask pairs prepared in Week 2, and its performance was evaluated on an independent test dataset.

---

## Tasks Completed

- Created PyTorch Dataset and DataLoader.
- Split the dataset into training, validation, and testing sets.
- Implemented a lightweight U-Net architecture.
- Trained the model for 5 epochs.
- Saved the best-performing model based on validation loss.
- Evaluated the trained model using Dice Score and Intersection over Union (IoU).
- Generated prediction visualization for qualitative assessment.

---

## Model Performance

| Metric | Value |
|---------|------:|
| Test Image-Mask Pairs | 528 |
| Mean Dice Score | **0.632** |
| Median Dice Score | **0.694** |
| Mean IoU | **0.505** |
| Median IoU | **0.531** |

---

## Training Results

The training and validation loss decreased consistently throughout the five training epochs, indicating stable convergence of the model. Dice scores also improved during training, demonstrating better overlap between the predicted masks and the ground truth annotations.

---

## Prediction Example

The figure below compares the original CT image, the ground truth calcium mask, and the predicted segmentation result.

<img width="4270" height="1485" alt="prediction_example" src="https://github.com/user-attachments/assets/a78d30c5-7a1d-4a46-9653-163a2601f8c5" />


---

## Loss Curve

The training and validation loss curves show that the model learned meaningful segmentation features during training.

<img width="2070" height="1466" alt="loss_curve" src="https://github.com/user-attachments/assets/5199e6de-184d-4642-a88c-2db27af4289f" />


---

## Dice Score Distribution

The histogram below illustrates the distribution of Dice scores across the test dataset.

<img width="2070" height="1466" alt="dice_distribution" src="https://github.com/user-attachments/assets/d2c709c4-8350-436a-8b60-916024e197c4" />


---

## Output Files

```text
week3_results/
├── best_unet_model.pth
├── evaluation_summary.csv
├── loss_curve.png
├── dice_distribution.png
└── prediction_example.png
```

---

## Reflection

This week marks the completion of the first deep learning segmentation model in this project. The trained U-Net achieved a mean Dice score of **0.632** on the test dataset, demonstrating its ability to identify coronary artery calcium regions from CT images. Although the model provides a solid baseline, its performance could be further improved through longer training, data augmentation, and more advanced segmentation architectures.

---

## Next Steps

- Analyze prediction errors.
- Investigate model limitations.
- Explore data augmentation.
- Compare different segmentation architectures (e.g., Attention U-Net, U-Net++).
