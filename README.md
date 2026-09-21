# AI-Powered Emotion-Aware Music Recommendation System

## Overview

This project is an AI-powered emotion detection and music recommendation system that analyzes a user's facial expressions in real time and plays music based on their detected emotional state. The system combines Computer Vision, Deep Learning, Speech Recognition, and Generative AI to create an interactive and personalized user experience.

The application captures live video from a webcam, detects the user's face using MediaPipe, classifies emotions using a Deep Learning-based facial emotion recognition model, and automatically recommends songs that match the detected mood. Additionally, the system integrates Gemini AI for conversational interaction, allowing users to communicate with the assistant through voice commands.

Still needed to extend the project by integrating with the sppech emotion recognitation so with the two results the emotion can be predcied some accurately.

---

## Features

### Real-Time Emotion Detection

* Captures live webcam feed using OpenCV.
* Detects faces using MediaPipe Face Detection.
* Identifies emotions using a Deep Learning facial emotion recognition model.
* Supports emotion categories:

  * Happiness
  * Neutral
  * Sadness

### Emotion Smoothing

* Uses a moving average buffer to reduce prediction noise.
* Provides stable and accurate emotion classification.

### Intelligent Music Recommendation

* Automatically selects songs based on detected emotion.
* Organizes songs into separate folders for different moods.
* Randomly chooses songs from the corresponding emotion playlist.
* Supports:

  * MP3
  * WAV
  * OGG audio formats

### Voice-Based Interaction

* Uses SpeechRecognition for voice command input.
* Uses pyttsx3 for text-to-speech responses.
* Allows hands-free interaction with the system.

### Gemini AI Integration

* Integrates Google's Gemini API.
* Maintains conversational memory through chat sessions.
* Enables natural language conversations with users.
* Provides intelligent responses beyond predefined commands.

### Interactive Controls

* Voice command to start emotion detection.
* Voice command to stop music playback.
* Voice command to end the session.

### Real-Time Visualization

* Displays emotion probability scores using Matplotlib.
* Shows live emotion confidence levels during detection.

---

## System Architecture

1. User provides webcam input.
2. MediaPipe detects the face region.
3. Facial image is extracted and passed to the emotion recognition model.
4. Deep Learning model predicts emotion probabilities.
5. Prediction smoothing is applied.
6. Dominant emotion is selected.
7. Appropriate song playlist is chosen.
8. Music is played according to the detected mood.
9. User can interact with the assistant through voice commands.
10. Gemini AI handles conversational responses.

---

## Technologies Used

### Computer Vision

* OpenCV
* MediaPipe

### Deep Learning

* DeepFace / HSEmotionRecognizer
* ONNX Runtime

### Artificial Intelligence

* Google Gemini API

### Speech Processing

* SpeechRecognition
* pyttsx3

### Data Processing

* NumPy
* Collections (Deque)

### Visualization

* Matplotlib

### Audio Playback

* Pygame Mixer

---

##  Project Structure

```text
Emotion-Based-Music-Player/
│
├── emotion.py          # Emotion detection logic
├── facecapture.py      # Webcam and face capture module
├── interaction.py      # User interaction handling
├── songs.py            # Song selection and playback
├── test.py             # Main application entry point
│
├── songs/              # Music library
│   ├── happy/
│   ├── sad/
│   ├── angry/
│   ├── neutral/
│   └── surprise/
│
├── .gitignore
├── README.md
└── venv/
```

##  Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/emotion-based-music-player.git
cd emotion-based-music-player
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

### 3. Activate Virtual Environment

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

If you don't have a requirements file:

```bash
pip install opencv-python numpy pygame
```

Install any additional libraries required by your project.


##  Running the Project

Run the main file:

```bash
python test.py
```

## Workflow

### Step 1: Voice Command

The user activates the system using a voice command such as:

"Capture my emotion"

### Step 2: Face Detection

MediaPipe detects the user's face from the webcam feed.

### Step 3: Emotion Recognition

The emotion recognition model analyzes facial expressions and predicts emotion probabilities.

### Step 4: Emotion Stabilization

Multiple predictions are averaged to reduce fluctuations.

### Step 5: Mood Identification

The dominant emotion is selected from:

* Happy
* Neutral
* Sad

### Step 6: Music Recommendation

A song matching the detected emotion is selected and played automatically.

### Step 7: AI Interaction

The user can continue interacting with the Gemini-powered assistant through voice conversations.

---

## Applications

* Personalized music recommendation systems
* Mental wellness assistants
* Emotion-aware entertainment platforms
* Human-computer interaction research
* Smart home assistants
* AI-powered companion systems

---

## Future Enhancement: Multimodal Emotion Recognition

The current system predicts user emotions primarily through facial expression analysis using Computer Vision techniques. While facial expressions provide valuable emotional cues, relying solely on visual information may not always produce the most accurate results due to variations in lighting conditions, facial occlusions, camera quality, and individual expression patterns.

To improve emotion recognition accuracy, the system will be extended with **Speech Emotion Recognition (SER)**, creating a **Multimodal Emotion Recognition Framework**.

### Planned Improvements

#### Speech Emotion Recognition

* Analyze vocal characteristics such as:

  * Pitch
  * Tone
  * Energy
  * Speaking rate
  * Spectral features (MFCCs)
* Classify emotions directly from the user's voice.

#### Multimodal Emotion Fusion

* Combine:

  * Facial Emotion Recognition (FER)
  * Speech Emotion Recognition (SER)

* Use fusion techniques such as:

  * Weighted averaging
  * Confidence-based fusion
  * Machine Learning ensemble models

#### Enhanced Emotion Categories

The extended system will support a wider range of emotions:

* Happy
* Sad
* Neutral
* Angry
* Fear
* Surprise
* Disgust

#### Improved Recommendation Engine

Music recommendations will be generated using both facial and vocal emotional cues, resulting in more personalized and accurate mood-based song selection.

### Expected Benefits

* Higher emotion recognition accuracy
* Better robustness under varying environmental conditions
* Reduced false emotion predictions
* Improved user experience
* More personalized music recommendations
* Stronger Human-AI interaction capabilities

### Long-Term Vision

The ultimate goal is to build a fully multimodal emotional AI assistant capable of understanding users through facial expressions, speech patterns, and conversational context, enabling emotionally intelligent and context-aware interactions.


This project demonstrates the integration of Computer Vision, Deep Learning, Speech Processing, and Generative AI into a single intelligent application capable of understanding user emotions and delivering personalized experiences.

### Still Working For Further Improvements...
