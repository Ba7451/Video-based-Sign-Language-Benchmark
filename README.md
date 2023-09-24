# Project Dataset Description

Data download: [Google Drive Link](https://drive.google.com/drive/folders/18PFNQzjqTcRWQczwU32AnY31GKiUoZA1?usp=drive_link)

The data for this project, provided by Google, consists of metadata and landmarks specifically designed for American Sign Language (ASL) recognition. Here is a detailed description of the components:

## Files

### `[train/supplemental_metadata].csv`

This CSV file contains the following columns:

- `path`: The path to the landmark file.
- `file_id`: A unique identifier for the data file.
- `participant_id`: A unique identifier for the data contributor.
- `sequence_id`: A unique identifier for the landmark sequence. Each data file may contain many sequences.
- `phrase`: The labels for the landmark sequence. The train and test datasets contain randomly generated addresses, phone numbers, and URLs derived from components of real addresses/phone numbers/URLs. Any overlap with real addresses, phone numbers, or URLs is purely accidental. The supplemental dataset consists of finger-spelled sentences. Note that some of the URLs include adult content. The intent of this data is to support the Deaf and Hard of Hearing community in engaging with technology on an equal footing with other adults.

### `character_to_prediction_index.json`

### `[train/supplemental]_landmarks/`

This directory contains the landmark data. The landmarks were extracted from raw videos with the MediaPipe holistic model. Not all of the frames necessarily had visible hands or hands that could be detected by the model.

The landmark data includes the following columns:

- `sequence_id`: A unique identifier for the landmark sequence. Landmark files contain approximately 1,000 sequences. The sequence ID is used as the dataframe index.
- `frame`: The frame number within a landmark sequence.
- `[x/y/z]_[type]_[landmark_index]`: There are now 1,629 spatial coordinate columns for the x, y, and z coordinates for each of the 543 landmarks. The type of landmark is one of ['face', 'left_hand', 'pose', 'right_hand']. Details of the hand landmark locations can be found [here](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker). The spatial coordinates have already been normalized by MediaPipe. Note that the MediaPipe model is not fully trained to predict depth so you may wish to ignore the z values. The landmarks have been converted to float32.

## Important Note

Landmark data should not be used to identify or re-identify an individual. Landmark data is not intended to enable any form of identity recognition or store any unique biometric identification.
