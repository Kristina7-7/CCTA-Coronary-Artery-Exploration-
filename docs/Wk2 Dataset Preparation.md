## Week 2: Annotation Parsing and Mask Generation

During Week 2, the Stanford COCA annotations were converted into
binary segmentation masks for coronary artery calcium.

### Preprocessing workflow

1. Loaded non-contrast cardiac CT images from DICOM files.
2. Converted DICOM pixel values into Hounsfield Units.
3. Parsed XML annotation files containing coronary calcium ROIs.
4. Extracted polygon coordinates from `Point_px`.
5. Matched each ROI to the corresponding DICOM slice using its
   physical z-coordinate.
6. Combined multiple ROIs located on the same CT slice into one
   binary mask.
7. Saved each CT slice and its corresponding mask as a paired
   NumPy array.

### Results

- Annotated patients processed: **449**
- Image-mask pairs generated: **3,671**
- Image size: **512 × 512 pixels**
- Preprocessing errors: **0**
- Mask values:
  - `0`: background
  - `1`: coronary artery calcium

### Example

![Example CT slice and calcium mask](figures/example_image_mask_pair.png)

The red region represents the binary calcium annotation overlaid on
the corresponding CT slice.

### Data availability

The original COCA DICOM files and generated NumPy arrays are not
included in this repository because of dataset size and data-use
requirements. This repository contains the preprocessing workflow,
summary results, and de-identified example visualizations.
