"# Image-Inpainting" 
✨ Telea's Inpainting Method

The Telea method works in the following steps:

   Region Detection
    The damaged area is defined using a mask image, typically a binary image where white pixels represent the region to be inpainted.

  Inpainting from Outside Inward
    The algorithm uses the Fast Marching Method to begin inpainting from the boundary of the damaged region and gradually moves inward—like peeling an onion. Pixels near healthy areas are restored first.
    Weighted Averaging of Neighboring Pixels
    Each damaged pixel is filled by computing a weighted average of nearby healthy pixels. Closer pixels and those better aligned with the region’s boundary get higher weights.
    Note: When we set radius=3, it does not mean just 3 individual pixels—it refers to 3 layers of neighboring pixels.

🌊 Navier-Stokes (NS) Inpainting Method

This method is inspired by fluid dynamics and the Navier-Stokes equations. It treats the image like a fluid and tries to continue isophotes (lines of constant intensity) across the missing region.

  NS is more suitable for images with strong edges or structural elements, such as drawings or object outlines.

   It is based on the paper:
    "Navier-Stokes, Fluid Dynamics, and Image and Video Inpainting".

How to Run

Install the required libraries:

pip install opencv-python matplotlib

Open TestII.ipynb in Jupyter Notebook or Google Colab.

Provide a source image and a corresponding binary mask (damaged area), then run the inpainting code using either cv2.INPAINT_TELEA or cv2.INPAINT_NS.
