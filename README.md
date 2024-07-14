# OMR-grader
# OMR Grading System

This project is an automatic OMR (Optical Mark Recognition) grading system using OpenCV and imutils in Python. It processes scanned images of quiz answer sheets and calculates the score based on the detected answers.

## Features
- Detects and processes the quiz answer sheet.
- Identifies the selected answers for each question.
- Compares the detected answers with the provided answer key.
- Calculates and displays the total score on the image.

## Prerequisites
- Python 3.x
- OpenCV
- imutils
- numpy

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/omr-grading-system.git
    cd omr-grading-system
    ```

2. Install the required packages:
    ```bash
    pip install opencv-python imutils numpy
    ```

## Usage
1. Place the image of the quiz answer sheet in the project directory.
2. Run the script:
    ```bash
    python omr_grading.py
    ```

3. Enter the path to the input image when prompted.

The script will process the image, detect the selected answers, and display the total score.

## Code Explanation
- **`four_point_transform`**: Performs a perspective transform to get a top-down view of the quiz answer sheet.
- **`cv2.findContours`**: Finds contours in the image to detect the boundaries of the answer sheet and the answer bubbles.
- **`cv2.threshold`**: Applies a threshold to binarize the image for easier contour detection.
- **`contours.sort_contours`**: Sorts the detected contours to organize the answer bubbles by their position on the sheet.
- **`cv2.countNonZero`**: Counts the non-zero pixels in the masked image to determine which bubble has been filled in.
- **`cv2.drawContours`**: Draws contours on the image to mark the detected answers and the correct answers.

## Example
```bash
Enter the path to the input image: path/to/your/quiz_answer_sheet.jpg
total score: 80.00%
