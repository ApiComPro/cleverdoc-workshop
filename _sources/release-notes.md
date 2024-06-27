# Release Notes

## 1.0.8 - June 27 2024

Provided support de-identification of DICOM files.

### Features
- Added `DicomTiOmage` transformer to extract from DICOM files pixel data as images
- Added `DicomDrawBoxes` transformer to draw boxes on DICOM pixel data

### Notebooks
- Added [Dicom de-identifocation notebook](https://github.com/ApiComPro/cleverdoc-workshop/blob/main/jupyter/de-identification/dicom/DicomDeIdentification.ipynb)


## 1.0.7 - June 10 2024

Performance of the pdf de-identification pipeline was improved. So for now for process 1000 pdf pages need less than minute.

### Features
- Improve partitioning in pdf datasource
- Improve performance of rendering pdf pages
- Added `SingleImageToPdf` transformer to convert a single image to pdf, for distribute processing pages of pdf
- Added `PdfAssembler` transformer to assemble multiple pdfs into a single pdf

### Models
- Added model `ApicomPro/deid-bert-onnx-1.2.0` for de-identification of medical documents

### Notebooks
- Added [notebook](https://github.com/ApiComPro/cleverdoc-workshop/blob/main/jupyter/de-identification/PdfDeIdentification.ipynb) for de-identification of pdf documents


## 1.0.6 - Jun 4 2024

### Features
- Added support custom pdf datasource

### Notebooks
- Added notebook for demonstrate spark-pdf datasource capabilities
