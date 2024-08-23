# Colorizing the Prokudin-Gorskii Photo Collection

The project takes the digitized Prokudin-Gorskii glass plate images and uses image processing techniques to automatically produce a color image with as few visual artifacts as possible.

## Table of Contents

- [Project Overview](#project-overview)
- [Key Functions](#key-functions)
- [Getting Started](#getting-started)
    - [Installation](#installation)

## Project Overview

The objective is to recreate color images from the digitized glass plate photographs Sergey Mikhaliovich Prokudin-Gorskii (1863-1944) took during the last years of the Russian Empire. The primary challenge is to align the three separate color channels—blue, green, and red (BGR)—from these glass plates to produce a single, cohesive RGB image with minimal visual artifacts. 

The process involves extracting the color channels, aligning them to form a composite image, and applying image processing techniques to ensure the final image is as clear and accurate as possible. The project includes a basic alignment algorithm using a single-scale search and an advanced version utilizing a coarse-to-fine pyramid approach to efficiently handle larger images (ex. TIFF files).

## Key Functions

- **split_color_channels()**: Splits the image into its BGR components
- **crop_image()**: Removes unnecessary borders by cropping the images
- **get_edges()**: Extracts image edges using the Canny algorithm
- **SSD()**: Calculates the Sum of Squared Differences for alignment scoring
- **align()** & **get_displacement()**: Aligns the channels by finding the optimal displacement
- **pyramid_align()**: Applies a multi-scale approach for efficient alignment of large images
- **colorize()**: The main function that integrates all the steps to produce and save the final colorized image

## Getting Started

### Installation 

Clone the repository to your local machine:
```bash
git clone https://github.com/yourusername/project-name.git
cd project-name


