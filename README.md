# Cross-Language Generalization of Parkinson’s Disease Speech Detection
This project investigates how models would perform within the same dataset and in cross-language zero shot testing, whether adding a small, speaker-balanced fraction of the target dataset during training would improve the cross-dataset
performance, and if fairness (difference in False Negative Rates between two comparable demographic groups) depended on training alone, or on the decision threshold selection as well. This study evaluates whether speech-based PD detection can generalize across languages and
datasets under limited exposure to the target dataset.

This is a research project. The models and analyses are not intended for clinical diagnosis or medical decision-making. For any real-world use, additional clinical validation and ethical oversight would be needed.

## What is in this repository
- `Yash_PD_Voice_Project.ipynb`  
  The main notebook with preprocessing, training, evaluation, and analysis steps.
- `model_card.md`  
  A short, plain-language description of the model family and how it was tested.
- `.gitignore`  
  Prevents large or private files (like datasets and generated outputs) from being uploaded by accident.

## Datasets (not included here)
This repository does not include the speech datasets or audio clips. The study uses public datasets and keeps data handling separate from the code.

Examples of datasets used in the study include:
- NeuroVoz (Castilian Spanish)
- EWA-DB (Slovak)
- IPVS (Italian)
- MDVR-KCL (English-UK)
- English-US sustained “Ah” sounds

Please follow each dataset’s license and access rules.

## How the model is set up (high level)
- Audio is standardized (mono, 16 kHz) and split by speaker so the same person does not appear in more than one split.
- A pretrained speech model (Wav2Vec2) is used as a frozen feature extractor.
- Two small classification heads are trained: one for vowel clips and one for read/other speech tasks.

## How to run
1. Open `Yash_PD_Voice_Project.ipynb` in Google Colab or Jupyter.
2. Follow the notebook cells in order.
3. Update any local or Google Drive paths used by the notebook.

Tip: Before uploading new versions of the notebook, clear all outputs so the file stays small.

## Citation
If you use this code for a paper or school project, please cite the associated manuscript and the dataset sources listed there.

## Related publication
This repository supports the research described in the paper:
“Cross-Language Generalization of Parkinson’s Disease Speech Detection Using Limited Target Data Calibration".

The paper reports the experimental design and results. This repository provides the accompanying code and analysis notebooks.

## Contact
For questions about this repository, please open a GitHub Issue.

## License
This project is released under the MIT License. See the LICENSE file for details.
