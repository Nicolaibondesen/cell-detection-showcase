# Cell Detection in C

**Technical University of Denmark (DTU)**  
02132 Computer Systems | 2026

## Overview

This project implements a cell detection algorithm in C,
developed as part of a university group assignment at DTU.

The program processes bitmap images and identifies
cell-like structures using image processing techniques.

The project focuses on algorithm implementation,
performance optimization, and the evaluation of
different approaches to image processing.

## Technologies

- C
- Image Processing
- Algorithm Optimization
- Memory Management
- Performance Testing
- Git

## Implementation

The cell detection algorithm consists of several steps:

1. **Grayscale Conversion:** Converts RGB images into
   grayscale representations.

2. **Dynamic Thresholding:** Applies adaptive thresholding
   to distinguish foreground objects from the background.

3. **Morphological Erosion:** Iteratively processes binary
   images to identify individual cell structures.

4. **Circular Detection:** Uses a circle-based detection
   algorithm inspired by Bresenham's circle algorithm.

5. **Visualization:** Marks detected cells in the original
   image and generates an output bitmap.

The implementation is divided into individual C source
files, with corresponding header files.

Two binary image buffers are reused during erosion
to reduce unnecessary memory allocation.

## Performance Analysis

Several optimizations were evaluated to investigate
their impact on execution time and cell detection.

The optimizations were introduced cumulatively:

- Baseline implementation
- Dynamic thresholding
- Circular detection
- Diagonal erosion

### Cell Detection Results

| Implementation | Easy | Medium | Hard | Impossible |
|---|---:|---:|---:|---:|
| Baseline | 298 | 244 | 239 | 191 |
| Dynamic Threshold | 299 | 255 | 245 | 211 |
| Circular Detection | 300 | 267 | 262 | 233 |
| Final Implementation | 300 | 268 | 261 | 226 |

### Execution Time (ms)

| Implementation | Easy | Medium | Hard | Impossible |
|---|---:|---:|---:|---:|
| Baseline | 5547 | 5352 | 7382 | 6698 |
| Dynamic Threshold | 7731 | 8761 | 9369 | 8362 |
| Circular Detection | 3599 | 3981 | 3503 | 3550 |
| Final Implementation | 3466 | 3553 | 3542 | 3834 |

The results demonstrate how algorithmic changes
affected both execution time and detection counts.

Dynamic thresholding increased execution time,
while circular detection significantly reduced
processing time compared to the previous implementation.

The final implementation introduced diagonal erosion,
which produced mixed results depending on image difficulty.

These measurements were recorded during the original
assignment using the same four test images.

Detection counts alone do not establish accuracy
without reference measurements.

## Build Instructions

### Requirements

- GCC compiler
- GNU Make

### Compilation

Clone the repository and navigate to its directory.

Compile the project:

```bash
make
```

This generates the executable:

```text
bin/cell-detection
```

### Running the Program

```bash
./bin/cell-detection input.bmp output.bmp
```

The program expects a 950 x 950 pixel BMP image.

If the included sample image is available, run:

```bash
./bin/cell-detection samples/demo_input.bmp output.bmp
```

### Cleaning

Remove generated build files:

```bash
make clean
```

## Project Structure

```text
cell-detection-c/
|
|-- src/
|   |-- main.c
|   |-- detect_spots.c
|   |-- detect_spots_circle.c
|   |-- dynamic_threshold.c
|   |-- erode.c
|   |-- ...
|
|-- include/
|   |-- *.h
|
|-- samples/
|   |-- demo_input.bmp
|
|-- docs/
|   |-- demo_input.png
|   |-- demo_output.png
|
|-- Makefile
|-- README.md
|-- .gitignore
```

## My Contributions

This project was developed as a group assignment
for the Computer Systems course at DTU.

My contributions included:

- Implementation of image processing functions in C.
- Algorithm improvements and optimization.
- Testing across different image difficulties.
- Performance measurements and analysis.
- Documentation of implementation and test results.

## Notes

This repository is intended as a portfolio presentation
of university project work.

The original project was developed collaboratively,
and the code includes contributions from other
group members.