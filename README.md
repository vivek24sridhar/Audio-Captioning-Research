Hierarchical Multi-Level Audio Caption Generation
1) **Overview**

This project converts audio signals into meaningful text descriptions.
Instead of showing only sound labels, the system generates human-readable sentences explaining what is happening in the audio, including environmental sounds and human speech.
The system works in multiple levels (frame, segment, and global) and uses pre-trained deep learning models to understand audio effectively.

2) **Key Features**

Detects environmental sounds (animals, vehicles, rain, music, etc.)

Identifies dominant sound events using hierarchical processing

Converts human speech into text using speech-to-text

Generates clear natural-language captions

Supports both audio upload and live microphone recording

Provides visual analysis using waveform, spectrogram, and graphs

3) **Tools & Technologies Used**

Python

TensorFlow & TensorFlow Hub

YAMNet – Environmental sound detection

Whisper – Speech-to-text conversion

Librosa – Audio processing

Google Colab – Development and testing environment

Matplotlib – Visualization

4) **System Workflow**

Audio is either uploaded or recorded live using a microphone.

The audio is resampled and converted into a waveform.

YAMNet analyzes the audio in small time frames and predicts sound events.

Frame-level predictions are grouped to identify dominant sound events.

A hierarchical strategy removes weak or noisy detections.

If human speech is detected, Whisper converts speech into English text.

For non-speech sounds, predefined sentences are used.

The final caption describes what is happening in the audio.

5)  **Code Structure Explanation**
**step 1:** Library Installation

Installs all required Python libraries for audio processing, sound detection, and speech recognition.

**step 2:** Model Loading

Loads the YAMNet model for environmental sound detection.

Loads the Whisper model for speech transcription.

Reads class labels used by YAMNet.

**step 3:** Audio Input

Allows the user to either:

Upload an audio file, or

Record live audio using the system microphone.

The selected audio is saved for processing.

**step 4:** Audio Preprocessing

Audio is resampled to 16 kHz.

Converted into a TensorFlow-compatible format.

**step 5:** Frame-Level Sound Detection

YAMNet predicts sound classes for each small audio frame.

Frame-wise sound labels are extracted.

**step 6:** Dominant Event Selection (Hierarchical Level)

Repeated sound events are counted.

Weak and short events are removed using a threshold.

Only dominant sound events are selected.

A fallback mechanism ensures at least one event is selected.

**step 7:** Speech Detection

Checks whether speech is present using confidence scores.

Speech processing is activated only when speech is detected.

**step 8:** Caption Generation

Sound events are mapped to predefined natural-language sentences.

If speech is present, Whisper generates text from speech.

Final caption combines all detected information.


5) **Applications**

Assistive technology for deaf or hard-of-hearing users

Smart home and IoT systems

Audio surveillance and security

Environmental and wildlife monitoring

Human-computer interaction

6) ** Project Status**

In Progress – Further optimization and real-time hardware deployment are planned.

7) ** Future Enhancements**

Real-time hardware implementation using Raspberry Pi

Multi-language caption support

Mobile and embedded device integration

Improved accuracy using fine-tuned models

8) **Author**

S.Vivek
Mohanachandhiran P
Rhuthresh S
Hierarchical Multi-Level Audio Caption Generation
(Research & Implementation)
