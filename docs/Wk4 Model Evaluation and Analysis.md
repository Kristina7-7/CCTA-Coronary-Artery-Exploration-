## Objective

Evaluate the trained U-Net model on the independent test dataset and analyze segmentation performance.

## Completed Tasks

- Loaded the best U-Net model from Week 3.
- Evaluated all 528 test image-mask pairs.
- Calculated Dice and IoU for each test image.
- Identified the best and worst prediction cases.
- Visualized prediction examples.
- Generated the Dice score distribution.
- Saved evaluation results to the `week4_results` folder.

## Evaluation Results

| Metric | Value |
|---------|------:|
| Test Images | 528 |
| Mean Dice | 0.632 |
| Median Dice | 0.694 |
| Mean IoU | 0.505 |
| Median IoU | 0.531 |
| Maximum Dice | 1.000 |
| Minimum Dice | 0.000 |
| Dice Standard Deviation | 0.246 |

## Observation

The model achieved a mean Dice score of approximately 0.63 on unseen test images. While several cases were segmented accurately, a few difficult slices resulted in low Dice scores, indicating variability in performance. These results provide a strong baseline for further model improvement in Week 5.
