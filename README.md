Singing Voice Conversion (SVC) Pipeline using so-vits-svc-fork:
This repository contains code that implements an audio processing pipeline for Singing Voice Conversion (SVC) using the so-vits-svc-fork framework. The pipeline processes your uploaded voice in WAV format, performing source separation to extract vocals and instrumental components. The dataset is then prepared by segmenting the audio based on silence detection, ensuring efficient training.

Automatic preprocessing steps, including resampling, configuration setup, and pitch detection, enhance compatibility with the SVC framework. The model training process is monitored using tensorboard for visualization. During inference, the trained model modifies the vocal quality and adjusts the pitch as desired. Finally, the modified vocals are combined with the instrumentals to produce the converted audio output.

Requirements
This code requires Python and the following libraries:
pydub
yt_dlp
ffmpeg
demucs
so-vits-svc-fork
Pipeline Overview

The code is organized into sections, each catering to a specific step in the SVC process:

Source Separation: Extracts vocals and instrumentals from the uploaded audio.
Dataset Preparation: Segments the audio based on silence detection.
Automatic Preprocessing: Includes resampling, configuration setup, and pitch detection.
Model Training: Uses tensorboard for monitoring and visualization.
Inference: Applies the trained model to modify vocal quality and adjust pitch.
Combining Vocals and Instrumentals: Produces the final converted audio output.

This pipeline utilizes several essential supporting files:

Config.json: Contains various configuration settings used in the SVC model. This file defines parameters for training, data preprocessing, model architecture, and other crucial aspects of the conversion process.

G_799th.pth: A checkpoint file containing the parameters and weights of a pre-trained neural network model. This file represents the generator component of a Generative Adversarial Network (GAN) or a similar model architecture used for SVC.

FinalCover.wav: The final output audio obtained after combining modified vocals and instrumentals.

input_data.wav: The input data (your voice in WAV format).

song_downloaded_from_utube.wav: The song with which the voice is being synthesized.

How to Use:

Upload Your Voice: Upload your voice in WAV format.
Source Separation: The code will perform source separation to extract vocals and instrumentals.
Prepare Dataset: The audio will be segmented based on silence detection.
Automatic Preprocessing: The code will handle resampling, configuration setup, and pitch detection.
Model Training: Train the model and monitor the process using tensorboard.
Inference: Apply the trained model to modify the vocal quality and adjust the pitch.
Combine Vocals and Instrumentals: Produce the final converted audio output (FinalCover.wav).
Example Usage
python
Copy code
# Ensure all dependencies are installed
pip install pydub yt_dlp ffmpeg demucs so-vits-svc-fork

# Run the SVC pipeline
python svc_pipeline.py --input input_data.wav --config Config.json --checkpoint G_799th.pth



