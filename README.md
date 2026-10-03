# Emotion-Aware-Music-Recommendation-System

This project integrates Facial emotion recognition with a music recommendation system to create a dynamic and responsive user experience. The system detects the user's emotions in real-time and plays music that complements or contrasts their mood, aiming to enhance emotional well-being and provide a personalized listening experience.

[![Version](https://img.shields.io/badge/version-1.0.0-blue)](URL_TO_VERSION) <!-- Replace URL_TO_VERSION with actual link --> 
[![Python](https://img.shields.io/badge/python-3.9+-informational)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/opencv-4.5+-informational)](https://opencv.org/)
[![DeepFace](https://img.shields.io/badge/deepface-0.0.70-informational)](https://github.com/serengil/deepface)
[![MediaPipe](https://img.shields.io/badge/mediapipe-0.10+-informational)](https://developers.google.com/mediapipe)
[![Gemini AI](https://img.shields.io/badge/gemini_ai-latest-red)](https://ai.google.dev/models/gemini)

## Description

The AI-Powered Emotion-Aware Music Recommendation System is a sophisticated application that leverages real-time facial emotion detection to curate and play music tailored to the user's current emotional state. By analyzing facial expressions through the webcam, the system identifies emotions such as happiness, sadness, and neutrality. Based on this detection, it selects and plays appropriate music from categorized folders, aiming to either match the user's mood or offer a comforting or uplifting selection.

Furthermore, the system incorporates a voice assistant powered by Google's Gemini AI, enabling interactive conversations and task execution through voice commands. This dual functionality creates an immersive and intelligent user experience, bridging the gap between emotional awareness and personalized entertainment.

## Table of Contents

- [Project Title & Badges](#ai-powered-emotion-aware-music-recommendation-system)
- [Description](#description)
- [Table of Contents](#table-of-contents)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Project Structure](#project-structure) 
- [Important Links](#important-links) 

## Features

- **Real-time Emotion Detection** : Utilizes computer vision libraries (OpenCV, MediaPipe) and DeepFace to detect facial expressions and identify emotions like happiness, sadness, fear, anger, surprise, disgust, and neutrality.
- **Emotion Simplification** : Simplifies detected emotions into three broad categories: 'Happy', 'Sad', and 'Neutral' for music selection.
- **Emotion-Aware Music Playback** : Selects and plays music from categorized folders (happy, sad, neutral) based on the user's detected emotion.
- **Interactive Voice Assistant** : Integrates with Google Gemini AI for natural language understanding and response generation, allowing voice-based interaction.
- **Face Mesh Landmark Detection** : Advanced face mesh analysis to pinpoint facial features for more accurate emotion detection.
- **Dynamic Music Adjustment** : Plays music for a set duration (e.g., 20 seconds) and allows for early interruption via voice command.
- **Secure API Key Management** : Uses environment variables (`.env` file) for secure handling of API keys, specifically for the Gemini AI service.
- **Visual Feedback** : Displays detected emotion probabilities and visualizes the face detection bounding boxes in real-time.

##  Tech Stack

- **Languages**: Python 
- **Computer Vision**: OpenCV, MediaPipe, DeepFace, HSEmotionRecognizer
- **AI & Machine Learning**: Google Gemini API, HSEmotionRecognizer
- **Audio Processing**: Pygame
- **Speech Recognition**: SpeechRecognition, pyttsx3
- **Data Handling**: NumPy, Collections (deque)
- **Utilities**: Math, OS, Random, Time, Threading, Matplotlib, Dotenv

##  Installation

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/Deadeepya574/AI-Powered-Emotion-Aware-Music-Recommendation-System.git
    cd AI-Powered-Emotion-Aware-Music-Recommendation-System
    ```

2.  **Set up a Python Virtual Environment** (Recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate   # On Windows use `venv\Scripts\activate`
    ```

3.  **Install Dependencies**:
    The project requires several Python libraries. You can install them using pip:
    ```bash
    pip install opencv-python deepface mediapipe pygame speechrecognition pyttsx3 google-generativeai python-dotenv numpy matplotlib hsemotion-onnx
    ```

4.  **Configure Gemini API Key**:
    - Create a `.env` file in the root directory of the project.
    - Add your Gemini API key to the `.env` file in the following format:
      ```
      GEMINI_API_KEY=YOUR_ACTUAL_API_KEY
      ```
    - Obtain your API key from [Google AI Studio](https://aistudio.google.com/app/apikey).

5.  **Set Up Music Folders**:
    - Create a main folder for your music, for example, `C:\Users\ksuma\Desktop\project x\songs`.
    - Inside this main folder, create subfolders for each mood category:
      - `happy_songs`
      - `sad_songs`
      - `neutral_songs`
    - **Important**: Update the `BASE_SONG_PATH` variable in `songs.py` and `test.py` to reflect the exact absolute path to your main music folder.
      Example:
      ```python
      # In songs.py and test.py
      BASE_SONG_PATH = r"C:\Users\ksuma\Desktop\project x\songs" # Replace with your actual path
      ```

6.  **Run the Application**:
    You can run the main application using the `test.py` script, which integrates all functionalities:
    ```bash
    python test.py
    ```

## How to Use

This project offers two primary modes of interaction:

### 1. Emotion-Aware Music Playback 

   - Run the `test.py` script.
   - The application will prompt you to look at the camera for emotion detection.
   - It will display a window showing your face detection and real-time emotion probabilities.
   - Once a dominant emotion is detected and sustained for a few seconds (e.g., 'Happiness', 'Sadness', 'Neutral'), the system will automatically select and play a song from the corresponding music folder.
   - The song will play for 20 seconds, or until you interrupt it by saying commands like "stop music" or "next song".

### 2. Interactive Voice Assistant 

   - After launching `test.py`, the system will greet you and activate its voice assistant mode.
   - You can engage in conversation by speaking commands or asking questions. For example:
     - "Hello"
     - "What time is it?"
     - "Tell me a joke."
   - The assistant uses Google Gemini AI to understand and respond to your queries.
   - To trigger the music playback based on your emotion, say "capture my emotion" or "play songs".
   - To exit the application, say "stop" or "bye".

**Example Interaction Flow:**
1. Run `python test.py`.
2. The assistant says: "Hello! I’m your AI assistant... Say 'capture my emotion' whenever you want me to play songs based on your mood!"
3. You say: "Tell me about yourself."
4. The assistant (Gemini) responds verbally and textually.
5. You say: "Capture my emotion."
6. The camera activates, detects your expression (e.g., you smile, showing 'Happiness').
7. A happy song starts playing, and the assistant says: "I detected a Happiness mood! Let’s enjoy [song name] for 20 seconds."

##  Project Structure

```
AI-Powered-Emotion-Aware-Music-Recommendation-System/
├── README.md               # Project documentation (this file)
├── emotion.py              # Script for standalone emotion detection using DeepFace
├── facecapture.py          # Script for face detection and mesh landmark analysis
├── interaction.py          # Script for voice assistant functionality with Gemini AI
├── songs.py                # Script for basic mood-based music playback
├── test.py                 # Main script integrating all functionalities (emotion detection, music, voice assistant)
├── venv/                   # Virtual environment folder (if created)
└── .env                    # Stores sensitive API keys (e.g., Gemini API key)
└── songs/                  # Directory to store music files
    ├── happy_songs/
    ├── sad_songs/
    └── neutral_songs/
```

##  Important Links

- **Project Repository**: [AI-Powered-Emotion-Aware-Music-Recommendation-System](https://github.com/Deadeepya574/AI-Powered-Emotion-Aware-Music-Recommendation-System)
- **Gemini AI API**: [Google AI Studio](https://aistudio.google.com/app/apikey)
- **OpenCV**: [https://opencv.org/](https://opencv.org/)
- **DeepFace**: [https://github.com/serengil/deepface](https://github.com/serengil/deepface)
 
