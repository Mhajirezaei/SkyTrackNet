SkyTrackNet
Deep Learning for Bird Trajectory Classification from Radar Data

SkyTrackNet is an advanced deep learning pipeline designed for bird trajectory classification using radar‑derived flight data.

The project combines physics‑inspired feature engineering with modern neural architectures such as Transformers and CNN‑LSTM networks to model complex motion patterns in bird flight trajectories.

Developed by SANo AI, SkyTrackNet focuses on accurate classification of bird species groups from trajectory sequences, enabling intelligent analysis of aerial wildlife movement.

Project Overview
Bird flight trajectories captured by radar contain rich temporal and spatial patterns.

However, raw coordinates alone are insufficient for accurate classification.

SkyTrackNet addresses this challenge by integrating:

• physics‑based trajectory features

• deep sequence modeling

• ensemble prediction strategies

The system learns both local motion patterns and long‑range dependencies within flight paths.

Key Features
• Physics‑inspired trajectory feature engineering

• Transformer‑based sequence modeling

• CNN‑LSTM hybrid architecture

• Cross‑validation training pipeline

• Ensemble inference strategy

• Competition‑compatible label mapping system

Feature Engineering
To improve model understanding of motion dynamics, the following trajectory features are extracted.

Position Features
• x, y, z coordinates

Velocity Features
• dx, dy, dz

• speed

Motion Dynamics
• acceleration

• turn angle

Radar Attributes
• airspeed

• radar_bird_size

These features allow the models to learn meaningful physical patterns in bird movement.

Model Architecture
SkyTrackNet uses an ensemble of two complementary deep learning models.

Transformer Model
The Transformer captures long‑range dependencies within trajectory sequences.

Capabilities:

• modeling long temporal patterns

• attention‑based trajectory reasoning

• robust sequence representation learning

CNN‑LSTM Model
Designed to capture short‑term local motion patterns.

Pipeline:

CNN layers → extract local trajectory features

LSTM layers → learn temporal motion dynamics

Ensemble Strategy
Predictions from multiple models are combined to improve robustness and accuracy.

Process:

Multiple models are trained using cross‑validation
Each model generates probability predictions
Probabilities are averaged across models
Internal model classes are mapped to competition labels
This ensemble strategy reduces variance and improves generalization.

Dataset Pipeline
The training pipeline processes trajectory sequences using:

• padding and truncation

• sequence normalization

• PyTorch Dataset abstraction

• trajectory feature extraction

This ensures consistent input formatting for neural models.

Repository Structure

SkyTrackNet/

  config.py
  # Model configuration and class definitions

  train_transformer_cv.py
  # Transformer cross‑validation training

  train_lstm.py
  # CNN‑LSTM training pipeline

  predict_ensemble.py
  # Ensemble prediction and submission generation

  src/

    dataset.py
    # Trajectory dataset pipeline

    trajectory_parser.py
    # Trajectory preprocessing utilities

    trajectory_features.py
    # Feature engineering module

    model_transformer.py
    # Transformer model implementation

    label_mapping.py
    # Mapping between internal model labels and competition labels

  data/

    train.csv
    test.csv
    sample_submission.csv


Training
To train the Transformer model with cross‑validation:
python train_transformer_cv.py

To train the CNN‑LSTM model:
python train_lstm.py


Inference
To generate the final ensemble predictions:
python predict_ensemble.py

The script loads trained models, performs ensemble averaging, maps internal labels to competition classes, and generates the final submission file.


Running the Dashboard
To launch the interactive dashboard for visualizing trajectory data and model predictions, run the following command:
python -m streamlit run dashboard.py
This will start a local Streamlit server and open the dashboard in your browser, allowing you to explore trajectory visualizations and model outputs interactively.

Team
SANo AI
Members:

• Sanay Hajirezaei

• Sonay Hajirezaei

Twin sisters from Tabriz, Iran.

Achievements

• 1i1w 2026 Winning a silver medal in international competitions

• Silver Medal — International Federation of Inventors’ Associations (IFIA), Switzerland

• Top 44 Teams — NASA Space Apps Hackathon 2025

• Ranked among the top 30 teams in the international AI Cup 2026 competition in the Netherlands.

• Multiple national gold rankings in AIO Cup and Sandbox competitions

• 4th place nationally — Khwarizmi Youth Innovation Festival

Our work focuses on artificial intelligence, deep learning, and innovative software systems.

Technical Expertise
Programming:

Python

HTML

CSS

JavaScript

PHP

Artificial Intelligence:

Machine Learning

Deep Learning

CNN

RNN

LSTM

Transformer

GAN

Decision Trees

Random Forest

Support Vector Machines (SVM)

Retrieval‑Augmented Generation (RAG)

Website
Portfolio and research projects:

https://sanay-sonay.com

Future Improvements
Possible future enhancements include:

• trajectory data augmentation

• geospatial feature engineering

• stacking ensemble models

• self‑supervised trajectory learning

These improvements may further enhance classification accuracy and robustness.

License
This project is developed for research and competition purposes.
