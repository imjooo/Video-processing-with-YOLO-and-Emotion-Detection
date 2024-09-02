# Video Processing with YOLO and Emotion Detection

## Overview

This project involves processing a video to detect and track people, identify their emotions, and classify them as either "Child" or "Therapist." The tools used include:

- **YOLO (You Only Look Once):** A model that detects objects in images and videos. In this case, it's used to detect people.
- **FER (Facial Emotion Recognition):** A tool that detects emotions from facial expressions.

The main tasks of the code are:
1. Upload a video.
2. Detect people in the video.
3. Classify detected people as "Child" or "Therapist" based on their height.
4. Track each person across frames, even if they leave and re-enter the frame.
5. Detect emotions and annotate them on the video.
6. Save the processed video and make it available for download.

## Requirements

1. **Python 3** - Make sure you have Python 3 installed on your system.
2. **Libraries** - Install the following Python libraries:
   - `ultralytics`
   - `opencv-python-headless`
   - `fer`
   - `google-colab` (for file upload in Google Colab)
   
   You can install these libraries using pip:
   ```bash
   pip install ultralytics opencv-python-headless fer google-colab
   ```

## How to Use

### 1. Upload the Video

- The code starts by uploading a video file. If you are running this code in Google Colab, you'll be prompted to upload a video file. If you are running it locally, modify the file upload section as needed.

### 2. Process the Video

- The video is processed frame by frame:
  - **Detection:** Each frame is analyzed to find people.
  - **Classification:** Each detected person is classified as either "Child" or "Therapist" based on their height.
  - **Tracking:** Each person is assigned a unique ID and tracked across frames.
  - **Emotion Detection:** Facial emotions are detected and displayed on the video.

### 3. Save and Download the Processed Video

- After processing, the video is saved as `output_video.avi`.
- If using Google Colab, the processed video is available for download.

## Code Explanation

Here's a step-by-step breakdown of the code:

1. **Imports**: Import necessary libraries and modules.

2. **Initialize Models**:
   - `YOLO` model is used for detecting people.
   - `FER` model is used for detecting emotions in faces.

3. **Upload the Video**:
   - In Google Colab, use `files.upload()` to upload the video.

4. **Load and Open the Video**:
   - Open the uploaded video file using OpenCV (`cv2.VideoCapture`).

5. **Set Up Video Writer**:
   - Prepare to save the processed video using `cv2.VideoWriter`.

6. **Detection and Tracking**:
   - For each frame:
     - Detect people using YOLO.
     - Classify each person as "Child" or "Therapist" based on their height.
     - Track each person by assigning and managing unique IDs.
     - Detect emotions and annotate them on the video.

7. **Save the Output Video**:
   - Write the processed frames to the output video file.

8. **Release Resources**:
   - Release video capture and writer objects and destroy any OpenCV windows.

9. **Download the Processed Video**:
   - If in Google Colab, provide a download link for the processed video.

## Screenshots 
- ![image](https://github.com/user-attachments/assets/4888226a-a5e9-435d-838e-4ff750c42236)
-![image](https://github.com/user-attachments/assets/340d5bff-31f5-4183-a99e-b63c810d4acc)

## Screen Recording
-https://github.com/user-attachments/assets/2a81a46a-e706-48cf-aa96-748cc67f4f8b



## Additional Points

-Purpose: The Child Threshold is a height value that helps the code classify detected individuals as either "Child" or "Therapist" (adult) based on their height.
- ## How it works:
- The height of the detected person (measured from the bounding box) is compared against this threshold value.
- If the height is less than the threshold (e.g., 280 pixels), the person is classified as a "Child."
- If the height is greater than or equal to the threshold, the person is classified as an "Adult" or "Therapist."
- ## Adjusting the Threshold:
- The threshold value (280 pixels in this case) can be adjusted based on the specific context of the video or the expected size of children and adults in the footage.

## Notes

- The video file should be in a supported format (e.g., AVI, MP4).
- The code assumes a basic setup and may need adjustments for different environments or additional features.
- The model will take time to process the video and give output
- Child thurshold must be tweeked based on the video so as to get much accurate output
- It will take upto 30-more than 60 minitues to process the video and get output

## Troubleshooting

- **Error: No file uploaded**: Ensure you upload a file when prompted.
- **Error: Could not open video**: Check if the video file path is correct and the file is accessible.

