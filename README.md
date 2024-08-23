# Colorizing the Prokudin-Gorskii Photo Collection

The project takes the digitized Prokudin-Gorskii glass plate images and uses image processing techniques to automatically produce a color image with as few visual artifacts as possible.

## Table of Contents

- [Project Overview](#project-overview)
- [Key Functions](#key-functions)
- [Installation](#installation)
- [Running the Notebook](#running=the=notebook)
- [Running on Google Colab](#running-on-google-colab)

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

## Installation 

Clone the repository to your local machine:
```bash
git clone https://github.com/masheharashid/colorize_prokudin_gorskii_collection.git
```

## Running the Notebook

1. **Launch the Jupyter Notebook Interface**<br>
Open the terminal and navigate to the project directory. Then, launch the Jupyter Notebook interface and open the Python notebook file:
   
   ```bash
   jupyter notebook colorize_prokudin_gorskii_collection.ipynb
   ```
   
2. **Set Up Paths**<br>
- Set the correct paths for ***results_dir*** and ***img_dir*** in the notebook. Locate the following sections:

   ```python
   # --- III. The Main Function: colorize() ---
   # Saves each colorized image in the "colorized_results" folder 
   results_dir = "/path/to/your/colorized_results"  # Replace with your actual file path
   
   # --- IV. Putting Everything Together ---
   # Path to the "original_data" folder, which contains the input images 
   img_dir = "/path/to/your/original_data"  # Replace with your actual file path
   ```
   Replace "/path/to/your/colorized_results" and "/path/to/your/original_data" with your local paths.

3. Follow the instructions in the notebook and run each cell in order

## Running on Google Colabo
   
1. Upload the Notebook
   - Open Google Colab.
   - Upload the colorize_prokudin_gorskii_collection.ipynb file to Colab.

2. Mount Google Drive (Optional)
   - If your image files are stored in Google Drive, mount the drive to access them:
python
Copy code
from google.colab import drive
drive.mount('/content/drive')
Set Up Paths
Update the results_dir and img_dir to reflect the paths on Google Drive or within the Colab environment.

Run the Notebook
Execute the cells in order as instructed in the notebook.
