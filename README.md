# 🩺 COCA AI Medical Image Segmentation

An end-to-end deep learning pipeline for medical image segmentation using the COCA CT dataset and a U-Net architecture implemented in PyTorch.

---

# 📌 Results at a Glance

| Item | Value |
|------|------|
| Dataset | COCA CT Dataset |
| Task | Medical Image Segmentation |
| Model | U-Net |
| Framework | PyTorch |
| Test Images | 528 |
| Best Dice Score | **0.8649** |
| Best IoU | **0.8179** |

---

# 📖 Project Overview

Medical image segmentation is an important task in computer-aided diagnosis because it enables automatic identification of anatomical structures from CT images.

This project develops an end-to-end deep learning pipeline that includes:

- Image preprocessing
- Ground-truth mask preparation
- Dataset splitting
- U-Net model training
- Model evaluation
- Data augmentation
- Fine-tuning
- Performance comparison

The objective is to investigate whether data augmentation can improve segmentation accuracy on CT images.

---

# 🔄 Workflow

<img width="2152" height="2967" alt="workflow_diagram" src="https://github.com/user-attachments/assets/1c12b7c3-a961-48df-9eb6-bc6c079e64f1" />


The workflow starts with raw CT images and corresponding masks, followed by preprocessing, model training, fine-tuning, and quantitative evaluation.

---

# ⭐ Key Contributions

- Developed an end-to-end medical image segmentation pipeline using PyTorch.
- Built automated preprocessing for CT images and segmentation masks.
- Trained a U-Net segmentation model.
- Improved segmentation performance using data augmentation.
- Achieved a **Mean Dice score of 0.8649** after fine-tuning.
- Documented the complete workflow with reproducible notebooks and evaluation results.

---

# 📊 Model Performance

| Model | Dice | IoU |
|-------|------:|------:|
| Baseline U-Net | 0.6319 | 0.5049 |
| Fine-tuned U-Net | **0.8649** | **0.8179** |

The fine-tuned model achieved significantly better segmentation accuracy after introducing data augmentation.

---

# 📈 Performance Comparison

<img width="1841" height="1349" alt="performance_comparison" src="https://github.com/user-attachments/assets/f2ee3695-2b93-4b60-8d4a-2c47608d8e2d" />

Performance improved after fine-tuning:

- Dice: **0.6319 → 0.8649**
- IoU: **0.5049 → 0.8179**

---

# 🖼 Example Prediction

<img width="2850" height="943" alt="prediction_example (3)" src="https://github.com/user-attachments/assets/cff999a3-4580-4825-be58-4a68e907a985" />


The prediction example compares:

- Original CT image
- Ground-truth segmentation
- Model prediction

---

# 🔀 Data Augmentation

The following augmentation techniques were applied during training:

- Random horizontal flip
- Random vertical flip
- Random 90° rotation
- Image resizing (256 × 256)

<img width="2514" height="1166" alt="augmentation_example (1)" src="https://github.com/user-attachments/assets/8f29d44e-df84-42fe-8cf4-e2419ac8b508" />


These augmentations increased dataset diversity and improved model generalization.

---

# 🏗 Project Structure

```text
COCA-AI-Segmentation/
│
├── docs/
│
├── figures/
│   ├── week2/
│   ├── week3/
│   ├── week4/
│   ├── week5/
│   ├── workflow_diagram.png
│   └── performance_comparison.png
│
├── notebooks/
│
├── results/
│
├── README.md
└── .gitignore
```

---

# 🛠 Technologies

- Python
- PyTorch
- NumPy
- Pandas
- Matplotlib
- Google Colab
- Git
- GitHub

---

# 📅 Project Timeline

| Week | Objective |
|------|-----------|
| Week 2 | Dataset preprocessing |
| Week 3 | U-Net training |
| Week 4 | Model evaluation |
| Week 5 | Data augmentation & fine-tuning |
| Week 6 | Documentation & visualization |

---

# ⚠ Limitations

- Only one segmentation architecture (U-Net) was evaluated.
- The model was tested on a single dataset.
- Hyperparameter optimization was limited.
- External validation on independent datasets was not performed.
- This project is intended for educational and research purposes only and is not designed for clinical use.

---

# 🚀 Future Work

Potential future improvements include:

- Compare U-Net with Attention U-Net and U-Net++.
- Explore Dice Loss, Focal Loss, and hybrid loss functions.
- Perform systematic hyperparameter optimization.
- Validate on larger and more diverse CT datasets.
- Investigate transformer-based segmentation models.
- Improve visualization and error analysis.

---

# 🙏 Acknowledgements

This project was developed for educational and research purposes in AI-based medical image analysis using Python, PyTorch, and the COCA CT dataset.
