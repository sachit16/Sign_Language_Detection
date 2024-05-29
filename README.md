Certainly! Below is a comprehensive `README.md` file for your project on sign language detection. This file provides details about the project, its features, installation instructions, usage guidelines, and descriptions of each script file.

---

# Sign Language Detection with Mediapipe and LSTM

This project aims to detect sign language gestures using a combination of Mediapipe for hand tracking and LSTM neural networks for sequence modeling. The project includes scripts for data collection, preprocessing, model training, and real-time gesture recognition.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Data Collection](#data-collection)
  - [Preprocessing](#preprocessing)
  - [Model Training](#model-training)
  - [Real-time Gesture Recognition](#real-time-gesture-recognition)
- [Directory Structure](#directory-structure)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Real-time video capture:** Captures frames from a webcam for gesture data collection.
- **Alphabetical categorization:** Saves captured images in directories named after alphabet letters (A-Z).
- **Region of Interest (ROI):** Focuses on a specific region of the frame to ensure consistent image size and quality.
- **Hand tracking and keypoint extraction:** Uses Mediapipe to detect hands and extract keypoints, saving them as numpy arrays.
- **Sequence modeling with LSTM:** Trains an LSTM model on the extracted keypoints for gesture classification.
- **Real-time gesture recognition:** Recognizes gestures in real-time using the trained model.

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/sachit16/Sign_Language_Detection
   cd sign-language-detection
   ```

2. **Install the required dependencies:**
   ```bash
   pip install opencv-python mediapipe numpy scikit-learn keras tensorflow
   ```

3. **Set up the directory structure:**
   Ensure that you have a directory named `Image` with subdirectories for each letter you want to collect data for. For example:
   ```
   Image/
   ├── A/
   ├── B/
   ├── C/
   ├── D/
   ├── E/
   └── F/
   ```

## Usage

### Data Collection

1. **Run the data collection script:**
   ```bash
   python collect_data.py
   ```
2. **Press the corresponding alphabet key (A-Z) to save frames in the respective directory.**

### Preprocessing

1. **Run the preprocessing script to convert images to numpy arrays:**
   ```bash
   python data.py
   ```

### Model Training

1. **Run the model training script to train the LSTM model:**
   ```bash
   python train_model.py
   ```

### Real-time Gesture Recognition

1. **Run the real-time gesture recognition script:**
   ```bash
   python app.py
   ```

## Directory Structure

```
sign-language-detection/
├── Image/
│   ├── A/
│   ├── B/
│   ├── C/
│   ├── D/
│   ├── E/
│   └── F/
├── MP_Data/
│   ├── A/
│   ├── B/
│   ├── C/
│   ├── D/
│   ├── E/
│   └── F/
├── Logs/
├── collect_data.py
├── data.py
├── function.py
├── train_model.py
├── app.py
├── model.h5
├── README.md
```

## Descriptions of Script Files

1. **`collect_data.py`**
   - Captures video frames from the webcam and saves them into directories named after alphabet letters.
   - Press a key (A-Z) to save the current frame to the respective directory.

2. **`data.py`**
   - Loads the saved images, processes them using Mediapipe for hand tracking, and extracts keypoints.
   - Saves the extracted keypoints as numpy arrays for use in model training.

3. **`train_model.py`**
   - Loads the processed keypoints data.
   - Trains an LSTM neural network model to recognize gestures based on the sequence of keypoints.
   - Saves the trained model architecture and weights.

4. **`app.py`**
   - Loads the trained model and uses it to recognize gestures in real-time from the webcam feed.
   - Displays the recognized gesture and its confidence level on the video feed.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to customize the `README.md` file further based on your specific requirements or add more details as necessary.
