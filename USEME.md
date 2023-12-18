# USEME Guide for Image Processing Application

This document provides a comprehensive guide on the script commands supported by the image
processing application. Each command is detailed with examples and specific conditions, if any.

## Script Commands

### General Format

- Commands are typically structured as `command argument1 argument2 ...`
- Comments start with `#` and are ignored by the script processor.

### Loading and Saving Images

- **Load an Image**:
    - `load <file_path> <image_name>`
    - Example: `load images/small_4x3.ppm small`


- **Save an Image**:
    - `save <output_path> <image_name>`
    - Example: `save res/small_color-correct.ppm small_color-correct`

### Image Processing Commands

- **Brightness and Darkness Adjustment**:
    - Brighten: `brighten <increment> <source_image> <output_image>`
    - Darken: `darken <decrement> <source_image> <output_image>`
    - Example: `brighten 10 small small-brighter`
    - Example: `darken 10 small small-darker`
  

- **Image Flipping**:
    - Horizontal Flip: `horizontal-flip <source_image> <output_image>`
    - Vertical Flip: `vertical-flip <source_image> <output_image>`
    - Example: `horizontal-flip small small-horizontal`
    - Example: `vertical-flip small small-vertical`
  

- **Blur and Sharpen**:
    - `blur <source_image> <output_image>`
    - `sharpen <source_image> <output_image>`
    - Example: `blur small small-blur`
    - Example: `sharpen small small-sharpen`
  

- **Color Filters**:
    - Sepia: `sepia <source_image> <output_image>`
    - Greyscale: `greyscale <source_image> <output_image>`
    - Example: `sepia small small-sepia`
    - Example: `greyscale small small-greyscale`


- **Dither Effect**:
  - `dither <source_image> <output_image>`
  - Example: `dither small small-dither`

### Component Processing Commands

- **RGB Component Splitting and Combining**:
    - Split: `rgb-split <source_image> <red_output> <green_output> <blue_output>`
    - Combine: `rgb-combine <output_image> <red_input> <green_input> <blue_input>`
    - Example: `rgb-split small small-red small-green small-blue`
    - Example: `rgb-combine small small-red small-green small-blue`
  

- **Red Component**:
    - `red-component <source_image> <output_image>`
    - Example: `red-component small small-red-component`


- **Green Component**:
    - `green-component <source_image> <output_image>`
    - Example: `green-component small small-green-component`


- **Blue Component**:
    - `blue-component <source_image> <output_image>`
    - Example: `blue-component small small-blue-component`

  
- **Value, Intensity, and Luma Visualization**:
    - Value: `value-component <source_image> <output_image>`
    - Intensity: `intensity <source_image> <output_image>`
    - Luma: `luma <source_image> <output_image>`
    - Example: `value-component small small-value`
    - Example: `intensity small small-intensity`
    - Example: `luma small small-luma`

### Histogram Command

- **Create a Histogram Image**:
    - `histogram <source_image> <output_histogram_image>`
    - Example: `histogram small small-histogram`


  
- **Color Correction**:
  - `color-correct <source_image> <output_image>`
  - Example: `color-correct small small_color-correct`

  
- **Color Correct Histogram**:
  - `color-correct-histogram <source_image> <output_image>`
  - Example: `histogram small_color-correct small_color-correct-histogram`

  
- **Levels Adjustment**:
  - `levels-adjust <black_point> <midtone_point> <white_point> <source_image> <output_image>`
  - Example: `levels-adjust 20 100 255 small small_levels-adjust`


- **Levels Adjustment Histogram**:
  - `levels-adjust-histogram <black_point> <midtone_point> <white_point> <source_image> <output_image>`
  - Example: `histogram small_levels-adjust small_levels-adjust-histogram`

### Process Portion of Image using Split

- **Split Blur**
    - `blur <source_image> <output_image> <split_percentage>`
    - Example: `blur small small-blur-split 50`


- **Split Sharpen**
  - `sharpen <source_image> <output_image> <split_percentage>`
  - Example: `sharpen small small-sharpen-split 50`


- **Split Sepia**
  - `sepia <source_image> <output_image> <split_percentage>`
  - Example: `sepia small small-sepia-split 50`


- **Split Greyscale**
  - `greyscale <source_image> <output_image> <split_percentage>`
  - Example: `greyscale small small-greyscale-split 50`


- **Split Color Correction**
  - `color-correct <source_image> <output_image> <split_percentage>`
  - Example: `color-correct small small_color-correct-split 50`


- **Split Levels Adjustment**
  - `levels-adjust <black_point> <midtone_point> <white_point> <source_image> <output_image> <split_percentage>`
  - Example: `levels-adjust 20 100 255 small small_levels-adjust-split 50`


- **Split Dither**
  - `dither  <source_image> <output_image> <split_percentage>`
  - Example: `dither small small_dither 50`


### Run script file:
  - `-file <file_path>`
  - Example: `-file res/commands.txt

### File Format Specific Commands

- Commands can be executed for different image formats (PPM, JPG, PNG) with the same syntax.
- Example for JPG format:
    - `load images/small_4x3.jpg small`
    - `brighten 10 small small-brighter`

### How to use GUI 

- Click on the "Open a file" button to load an image. 
- Navigate to the image file and click "Open".
- The loaded image will be shown in the Current Image pane.
- Click on the dropdown menu to select the image processing command.
- When a filter is selected, the image will be shown in the Filtered Image pane as a preview until
  "Apply filter" button is clicked.
- For specific filters, a slider will be shown to adjust the filter.
- The filter is applied from the left side of the image to the right side of the image.
- For "Adjust levels" filter, the slider will be shown to adjust the black point, mid-tone point, 
  and white point. The user can enter the values in the text fields provided.
- For "Compress", the user can enter the compression ratio in the text field provided.
- The Histogram pane shows the histogram of the Filtered image. As the slider is moved, the 
  histogram will be updated in real-time.
- Click on the "Apply filter" button to apply the current filter to the image.
- If the user wants, they can apply multiple filter to the filtered image.
- Click on the "Save" button to save the image.
- Navigate to the folder where the image should be saved and click "Save".

### Pre-requisites
- Java 8 or higher

### Notes

- Ensure that commands are typed and ordered correctly.
- Some commands may need prerequisites (like loading an image before processing it).
- After every process command, type the save method to save the image.




