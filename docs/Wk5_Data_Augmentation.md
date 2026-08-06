## Objective

Improve the U-Net segmentation model by applying data augmentation and fine-tuning.

### Data Augmentation

- Random horizontal flip
- Random vertical flip
- Random 90° rotation
- Resize to 256 × 256

### Performance

| Metric | Value |
|--------|------:|
| Mean Dice | **0.8649** |
| Mean IoU | **0.8179** |

### Improvements

Compared with Week 4:

- Dice improved from **0.6319** to **0.8649**
- IoU improved from **0.5049** to **0.8179**

The fine-tuned model demonstrated substantially better segmentation performance on the COCA test dataset.
