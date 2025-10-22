The following prompt is a pipeline for my web application, designed to predict if a text is being written by a human of by AI. 
Below, I have presented the pipeline of the functions of this web application. Each step resembles a functionality that the application needs to do. 

1. DATA LOAD & PREPARATION

Input: User uploads train.csv and test.csv files

Processing:

Automatically detects Label (0/1) in column 2 and Text Content in final column

Cleans CSV artifacts (quotes, escaped characters, brackets)

Validates data format and filters invalid entries

Output: Cleaned arrays of [Label, Text] pairs

2. DATA INSPECTION & ANALYSIS

Statistics: Calculates class distribution (Human vs AI samples)

Visualization:

Displays data preview table

Shows class balance chart using tfjs-vis

Flags imbalanced datasets

Purpose: Understand data quality and distribution before modeling

3. TEXT PREPROCESSING & TOKENIZATION

Parameters: User sets max sequence length and embedding dimension

Processing:

70/30 train-validation split

Creates vocabulary from training texts only

Converts text to integer sequences

Pads/truncates sequences to uniform length

Output: Numerical tensors ready for neural network

4. EMBEDDING LAYER SETUP

Function: Defines vocabulary size and embedding dimensions

Purpose: Converts token indices to dense vector representations

Output: Embedding parameters finalized for model architecture

5. NEURAL NETWORK MODEL CONSTRUCTION

Architecture:

Embedding Layer: Word vector representations

Conv1D Layer: Feature extraction from text sequences

Global Max Pooling: Dimensionality reduction

Dense Layer: Non-linear transformation

Dropout: Regularization to prevent overfitting

Output Layer: Softmax for binary classification

Compilation: Adam optimizer with binary cross-entropy loss

6. MODEL TRAINING

Process:

Trains on training data

Validates on validation set in real-time

Monitors loss and accuracy metrics

Visualization: Real-time training graphs using tfjs-vis

Output: Trained model ready for predictions

7. LIVE PREDICTION INTERFACE

Input: User types or pastes text

Processing:

Same preprocessing pipeline as training data

Model inference on single text sample

Output: Real-time classification with confidence scores

Visual: Color-coded results (green for human, red for AI)

8. MODEL EVALUATION & METRICS

Validation: Runs predictions on held-out validation set

Metrics Calculated:

Confusion Matrix (TN, FP, FN, TP)

Accuracy, Precision, Recall, F1-Score

Interactive: Adjustable classification threshold with real-time metric updates

9. BATCH PREDICTION & EXPORT

Processing: Runs model on entire test.csv dataset

Output: Generates downloadable CSV with:

Text snippets

Prediction labels (0=Human, 1=AI)

AI probability scores

Format: Ready for analysis or reporting

🔧 Key Technical Features

End-to-End Browser Solution: No server required

Memory Management: Tensor disposal to prevent leaks

Responsive UI: Works on desktop and mobile

Real-time Visualizations: Training progress and metrics

Interactive Controls: Threshold adjustment with live updates

Robust Data Handling: Automatic column detection and cleaning

📊 Model Architecture Specifics

Input: Padded sequences of token indices

Embedding: Learned word vectors

Feature Extraction: 1D Convolution + Global Max Pooling

Classification: Dense layers with dropout

Output: Probability distribution over 2 classes

This pipeline demonstrates a complete machine learning workflow from raw data to deployed predictions, all running client-side in the browser.



here are also attached the test and train CSV files. 
This is the way they are, and they are not going to change! 
I have been having Issues with the first part 1. DATA LOAD & PREPARATION. 
This stage has some instructions in my prompt (something about the 0 and 1 labels) which consistently does not allow me to load my data properly. 
Take a good look at the uploaded train.csv and test.csv, and fix the prompt (the insturction) so that it becomes possible to work with the data given. 
GO!
