# Avataar_Assignment_H3
## Image Manipulation using CLIP, SAM, and Stable Diffusion
This project demonstrates how to combine state-of-the-art AI models to perform object segmentation, shifting, and inpainting within images. The project includes two primary tasks:

Object Segmentation and Highlighting using CLIP and SAM
Object Shifting and Background Inpainting using CLIP, SAM, and Stable Diffusion
Features
Object Identification: Uses CLIP to find the most relevant region in an image based on a textual description (e.g., "laptop").
Object Segmentation: Uses SAM to segment the identified object.
Object Shifting: Moves the segmented object to a new location within the image.
Background Inpainting: Fills the original object's area with natural-looking content using Stable Diffusion's inpainting model.
Task 1: Object Segmentation and Highlighting
Description
This task uses CLIP and SAM models to locate and segment an object in an image based on a text description (e.g., "laptop"). After segmentation, a red border is applied around the object to highlight it.

Workflow
CLIP is used to find the region of the image most relevant to the text (e.g., "laptop").
SAM (Segment Anything Model) segments the object based on the bounding box around the region.
A red border is drawn around the segmented object to visually emphasize it.
Example
In an image of a workspace, if the text prompt is "laptop", the code segments the laptop and highlights it with a bold red border.

## Run Task 1
bash
Copy code
# Install dependencies
pip install -r requirements.txt

# Execute the script
python segment_and_highlight.py --image_path "path_to_image.jpg" --object_class "laptop" --output_path "output_image.png"
Task 2: Object Shifting and Background Inpainting
Description
This task allows you to shift a segmented object in an image to a new location and inpaint the original area where the object was using Stable Diffusion.

Workflow
CLIP identifies the best point in the image matching the text description.
SAM segments the object.
The segmented object is shifted to a new location.
The Stable Diffusion Inpainting model fills in the background where the object was originally located, creating a natural-looking scene.
Example
In an image with a laptop, the script shifts the laptop slightly to a new location and inpaints the original space to blend it naturally with the background.

## Run Task 2
bash
Copy code
# Install dependencies
pip install -r requirements.txt

# Execute the script
python shift_and_inpaint.py --image_path "path_to_image.jpg" --object_class "laptop" --x_shift 50 --y_shift 20 --output_path "shifted_output.png"
Dependencies
The project uses the following Python libraries:

torch
transformers
PIL
segment-anything
opencv-python
diffusers
numpy
