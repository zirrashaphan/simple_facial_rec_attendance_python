# Face Recognition Attendance System

This is a simple attendance system that uses face recognition to mark and track attendance. It captures face images, trains a model to recognize faces, and logs attendance with timestamps, which can then be viewed through a web interface.

## Overview

The project consists of three main scripts:

- **`add_faces.py`**: Registers new users by capturing 100 face images via webcam and storing the data for recognition.
- **`test.py`**: Runs the attendance-taking system, recognizing faces in real-time and logging attendance to a CSV file.
- **`app.py`**: A Streamlit-based web app that displays the attendance records for the current day, auto-refreshing every 2 seconds.

## Components

### `add_faces.py`
- **Purpose**: Adds new users to the system.
- **Functionality**: Uses OpenCV to capture 100 face images from a webcam, processes them, and saves the face data and names in pickle files (`faces_data.pkl` and `names.pkl`) for later recognition.

### `test.py`
- **Purpose**: Takes attendance by recognizing faces.
- **Functionality**: Uses a K-Nearest Neighbors (KNN) classifier to identify faces from the trained data, logs the name and timestamp in a CSV file, and provides text-to-speech feedback ("Attendance Taken") when the 'o' key is pressed.

### `app.py`
- **Purpose**: Displays attendance records.
- **Functionality**: A Streamlit app that reads the current day's attendance CSV file and shows it in a table, refreshing every 2 seconds for real-time updates.

## Setup

To run this app, you need Python installed along with the following dependencies:

- **OpenCV**: For face detection and image processing.
- **NumPy**: For array manipulation.
- **Scikit-learn**: For the KNN classifier.
- **Pickle**: For saving and loading face data.
- **CSV**: For handling attendance logs.
- **Datetime**: For timestamp generation.
- **PyWin32**: For text-to-speech functionality (Windows only).
- **Streamlit**: For the web interface.

### Prerequisites

Ensure you have the Haar Cascade file (`haarcascade_frontalface_default.xml`) in a `data/` folder. You can download it from the [OpenCV GitHub repository](https://github.com/opencv/opencv/tree/master/data/haarcascades).

Create the following directories:

- `data/`: For storing the Haar Cascade file, `names.pkl`, and `faces_data.pkl`.
- `Attendance/`: For storing attendance CSV files.

Optionally, provide a `background.png` image (used in `test.py` for the UI background).

### Installation
Install the required libraries using pip:

```bash
pip install opencv-python numpy scikit-learn pickle-mixin csv datetime pywin32 streamlit
