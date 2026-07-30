# Week 1 – COCA Dataset Exploration and Annotation Parsing

## Project Goal

The objective of this week's work was to understand the structure of the COCA (Coronary Calcium and Chest CT) dataset and establish the relationship between CT images (DICOM) and expert calcium annotations (XML). This step provides the foundation for future coronary artery calcium (CAC) detection using deep learning.

---

# 1. Dataset Structure

The COCA gated dataset consists of two main components:

```
gated_files/
│
├── patient/
│     ├── 135/
│     ├── 136/
│     └── ...
│
└── calcium_xml/
      ├── 135.xml
      ├── 136.xml
      └── ...
```

- **patient/** contains CT images stored in DICOM format.
- **calcium_xml/** contains expert annotations describing coronary calcium lesions.

Each patient folder has one corresponding XML annotation file.

---

# 2. Reading DICOM Images

The CT images were loaded using the **pydicom** library.

Each DICOM file contains:

- Pixel values
- Image dimensions
- Slice position
- Hounsfield Unit (HU) conversion parameters
- InstanceNumber

The raw pixel values were converted into Hounsfield Units using

HU = PixelValue × RescaleSlope + RescaleIntercept

For the selected patient:

- RescaleSlope = 1
- RescaleIntercept = -1024

The reconstructed CT image had

- Minimum HU = -1024
- Maximum HU = 1082

confirming successful HU conversion.

---

# 3. CT Windowing

To improve visualization, a soft tissue window was applied.

Window settings:

- Window Center = 40 HU
- Window Width = 400 HU

Compared with the original image, the windowed image showed clearer soft tissue contrast while preserving coronary anatomy.

---

# 4. Parsing XML Annotations

Each XML file contains expert annotations for coronary calcium lesions.

Important fields include:

- ImageIndex
- NumberOfROIs
- Coronary artery name
- Point_px
- Point_mm
- HU statistics (Minimum, Mean, Maximum)

Unlike DICOM, XML does not store images. Instead, it stores the locations and boundaries of calcium plaques.

---

# 5. Matching XML with DICOM

The annotation matching process involved:

1. Selecting the corresponding patient.
2. Loading the patient's XML file.
3. Reading the ImageIndex.
4. Identifying the matching CT slice.
5. Verifying the correspondence using physical z-coordinates (ImagePositionPatient).

The matched DICOM slice was successfully identified before visualization.

---

# 6. ROI Reconstruction

The XML stores calcium lesions as polygon annotations.

Each polygon consists of:

- NumberOfPoints
- Point_px

The Point_px coordinates were converted into a polygon and overlaid onto the CT image.

This reconstructed the exact boundary drawn by the radiologist.

---

# 7. Annotation Validation

To verify the correctness of the parser, the HU values inside the reconstructed polygon were calculated and compared with the values stored in the XML.

Results:

| Measurement | XML | Calculated |
|-------------|----:|-----------:|
| Minimum HU | 135 | 135 |
| Mean HU | 138 | 138 |
| Maximum HU | 141 | 141 |

All measurements matched exactly.

This confirms that:

- XML parsing is correct.
- Polygon reconstruction is correct.
- DICOM matching is correct.
- HU conversion is correct.

---

# 8. Key Findings

- The COCA dataset separates CT images and annotation files.
- DICOM files store CT image information.
- XML files store expert coronary calcium annotations.
- ImageIndex identifies the CT slice containing the lesion.
- Point_px defines the polygon outlining the calcium plaque.
- HU validation confirmed accurate mapping between XML annotations and DICOM images.

---

# Week 1 Summary

During Week 1, I successfully established the complete annotation pipeline for the COCA dataset. Starting from DICOM image loading and HU conversion, I parsed XML annotations, matched them to the correct CT slices, reconstructed expert-defined calcium polygons, and validated the annotations by comparing reconstructed HU measurements with the original XML records.

This work provides a reliable foundation for automated coronary artery calcium detection and future deep learning model development.
