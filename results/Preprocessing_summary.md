# Week 2 Preprocessing Summary

## Dataset
Stanford COCA coronary artery calcium dataset.

## Processing workflow
- Read DICOM CT images
- Parse XML annotations
- Match ROIs to CT slices
- Generate binary masks
- Merge multiple ROIs on the same slice
- Save image-mask pairs

## Results
- Annotated patients: 449
- Image-mask pairs: 3,671
- Image size: 512 × 512
- Preprocessing errors: 0
