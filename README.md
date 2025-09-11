# Prenith-and-Drew-Estimate-Camera-Poses

## Installation Steps

To set up the project locally, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/a3d2ddk/Prenith-and-Drew-Estimate-Camera-Poses.git
   cd Prenith-and-Drew-Estimate-Camera-Poses

### Run in Colab
```markdown
## Run in Colab

If you prefer to run the demo in Google Colab, follow these steps:

1. **Clone the Repository**:
   The code automatically checks if it's running in Colab and clones the repository if it isn't already present:
   ```python
   from pathlib import Path

   def in_colab() -> bool:
       try:
           import google.colab  # noqa: F401
           return True
       except Exception:
           return False

   REPO_URL  = "https://github.com/a3d2ddk/Prenith-and-Drew-Estimate-Camera-Poses.git"

   if in_colab():
       calibration_dir = "/content/Prenith-and-Drew-Estimate-Camera-Poses/"
       print("Running in Colab")
       if not Path("/content/Prenith-and-Drew-Estimate-Camera-Poses/").exists():
           !git clone {REPO_URL}
   else:
       calibration_dir = ""

## How to Use the Gradio UI

1. **Upload an Image**:
   Click on the "Upload Image" area to select an image where you want to estimate the camera pose.

2. **Select Points**:
   Click on the image to select points. The selected points will be numbered and displayed on the image.

3. **Undo/Redo**:
   - Click the **Undo** button to remove the last selected point.
   - Click the **Clear** button to remove all selected points.

4. **Process Points**:
   After selecting the desired points, click the **Process Points** button to estimate the camera pose. The results will be displayed in the following areas:
   - **Homography to Pose**: Displays the homography matrix.
   - **OpenCV solvePnP**: Displays the results from OpenCV's pose estimation.
   - **Coordinate Axes Overlay**: Shows the coordinate axes overlay on the uploaded image.
   - **3D Camera Pose**: Visualizes the estimated camera pose in 3D.

## Expected Outputs

- **Homography to Pose**: A string representation of the rotation and translation matrices.
- **OpenCV solvePnP**: A string representation of the rotation and translation matrices from OpenCV.
- **Coordinate Axes Overlay**: An image showing the coordinate axes on the uploaded image.
- **3D Camera Pose**: An image visualizing the camera pose in a 3D space.
