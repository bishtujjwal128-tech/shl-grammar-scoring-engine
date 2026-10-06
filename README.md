# SHL Grammar Scoring Engine

## SHL Hiring Assessment 2026

This project develops a machine learning based Grammar Scoring Engine for spoken English audio samples.

The objective is to predict a continuous grammar score from 0 to 5 using acoustic features extracted from speech recordings.

## Dataset

- Training samples: 769
- Test samples: 216
- Audio format: WAV
- Target: Grammar/MOS score from 0 to 5

## Approach

The project follows this pipeline:

1. Load and inspect the audio dataset.
2. Analyze speech waveforms.
3. Generate spectrograms and MFCC visualizations.
4. Extract acoustic features from each audio file.
5. Train multiple regression models.
6. Compare models using 5-fold cross-validation.
7. Select the best-performing model.
8. Train the final model using the complete training dataset.
9. Generate predictions for the test set.
10. Create the final submission file.

## Audio Features

The feature extraction pipeline includes:

- MFCC
- Delta MFCC
- Mel-spectrogram statistics
- Chroma features
- Spectral centroid
- Spectral bandwidth
- Spectral rolloff
- Zero-crossing rate
- RMS energy

A total of 274 fixed-length acoustic features were extracted for each audio sample.

## Models Evaluated

The following regression models were compared:

- Random Forest
- Extra Trees
- Gradient Boosting
- XGBoost

## Model Selection

XGBoost achieved the best 5-fold cross-validation performance.

| Model | Mean RMSE | Mean Pearson |
|---|---:|---:|
| XGBoost | 0.7759 | 0.7759 |
| Extra Trees | 0.7875 | 0.7712 |
| Gradient Boosting | 0.7998 | 0.7602 |
| Random Forest | 0.7999 | 0.7618 |

## Final Training Results

Training RMSE:

**0.2529**

Training Pearson Correlation:

**0.9830**

The training metrics are reported separately because they are calculated on the same data used to train the final model.

## Cross-Validation Results

Mean 5-fold CV RMSE:

**0.7759**

Mean 5-fold CV Pearson Correlation:

**0.7759**

## Output

The final model generated grammar-score predictions for all 216 test audio samples.

The submission file contains:

- `filename`
- `label`

with 216 predictions constrained to the required 0–5 range.

## Future Improvements

Future versions could use pretrained speech representations such as:

- wav2vec 2.0
- HuBERT
- Whisper embeddings

Additional linguistic and speech-prosody features could also improve grammar-score prediction.

## Competition

SHL Hiring Assessment 2026

## Author

Ujjwal Bisht
