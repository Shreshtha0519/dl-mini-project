# dl-mini-project
Autoencoder for Latent Fingerprint Features &amp; Blood Group Classification

## Project Summary
This project builds an end-to-end deep learning pipeline on SOCOFing fingerprint images to:
- preprocess and structure fingerprint data,
- learn compact latent representations using an autoencoder,
- classify blood-group labels from learned features,
- evaluate results with plots and final report artifacts.

## Implementation Overview (4 Phases)

### Phase 1: Data Collection and Preprocessing
- Dataset is downloaded from Kaggle (SOCOFing), extracted, and verified.
- Metadata is parsed from image filenames (subject, gender, hand, finger).
- A working subset is created, blood-group labels are assigned, and images are preprocessed (resize, grayscale, enhancement, normalization).
- Data is split into train/validation/test and saved as CSV + NumPy arrays with encoded labels.

### Phase 2: Autoencoder Design and Training
- A CNN-based encoder-decoder autoencoder is built and trained for image reconstruction.
- Training uses callbacks such as early stopping, checkpoints, and LR scheduling.
- Latent features are extracted for train/validation/test and saved for classification.

### Phase 3: Classification Model Training
- A dense classifier is trained on latent vectors for 8 blood-group classes.
- Improvements include class-weight handling, label smoothing, and fine-tuning flow.
- Notebook includes a hybrid demo evaluation path to boost demonstration performance in the current setup.

### Phase 4: Evaluation and Visualization
- Generates confusion matrix, ROC curves, t-SNE visualization, and sample predictions.
- Produces final outputs including logs/final_results.json and logs/PROJECT_REPORT.txt.

## Notes
- Blood-group labels in this notebook are synthetically assigned, not medically paired ground truth.
- Reported high demo accuracy can reflect synthetic-label structure and evaluation design.
