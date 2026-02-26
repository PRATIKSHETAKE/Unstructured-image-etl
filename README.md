# Unstructured Image-to-Parquet ETL Pipeline

## Overview
This Data Engineering Proof of Concept demonstrates how to build an ingestion and preprocessing pipeline for unstructured image data. It scans raw image directories, standardizes the data using computer vision techniques, and serializes the resulting mathematical tensors into a highly compressed Parquet format designed for Deep Learning integration.

## Architecture
1. **Extract:** Ingests raw, completely unstandardized image files (JPEGs, PNGs) of varying dimensions and color profiles from a local directory.
2. **Transform:** Utilizes `Pillow` (PIL) and `NumPy` to normalize the data. Images are converted to standard RGB, resized to a uniform 128x128 resolution, and flattened into 1D numerical arrays (tensors) so they can be processed by machine learning algorithms.
3. **Load:** Serializes the structured dataset—including the extracted metadata (original dimensions, file size) and the mathematical image arrays—into a `.parquet` file using the `pyarrow` engine, significantly reducing storage footprint and read-times for downstream modeling.

## Real-World Applications
This pipeline architecture is specifically designed to prepare complex datasets for advanced computer vision tasks. Example use cases include standardizing dashcam frames for road segmentation and object detection models, or preprocessing animation datasets (such as Ghibli images) before feeding them into deep learning neural networks.

## Tech Stack
* **Language:** Python 3
* **Image Processing:** Pillow (PIL), NumPy
* **Data Manipulation:** Pandas
* **Big Data Storage:** PyArrow (Parquet)
