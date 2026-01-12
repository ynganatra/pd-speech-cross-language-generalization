# Model Card (Research Only): Multilingual PD Voice Classifier (Model Family)

## What this is
This project does not rely on one single “final” model. It evaluates a family of models that share the same general design, but use different training setups (monolingual, multilingual, zero-shot transfer and limited target-data calibration).

## Intended use
Research on:
- cross-language and cross-dataset testing
- how limited target training data changes results
- fairness analysis using sex-stratified false negative rates (FNR)
- task comparisons (vowel vs read/other speech)

Not intended for:
- clinical diagnosis
- medical screening in real settings
- treatment decisions, patient advice, or any high-stakes use

## Inputs and outputs
**Input:** short speech clips that have been preprocessed and labeled for research (PD vs healthy control).  
**Output:** a probability score for PD vs healthy control at the clip level.

## Model design (simple description)
- A pretrained Wav2Vec2 speech model is used as a frozen feature extractor (the backbone weights are not changed during training).
- Two small classification heads are trained:
  - one head for vowel (sustained phonation) clips
  - one head for read/other speech clips
- The two-head design is used because different speech tasks can behave differently.

## Data used (not shipped in this repo)
The study uses public datasets in different languages and recording settings. The datasets are not included in this repository.

## How it is evaluated
Common evaluation steps include:
- AUROC as the main performance metric
- decision thresholds chosen from validation data (for example, Youden J)
- fairness analysis based on differences in false negative rates between female and male speakers
- additional ablations (target-data inclusion steps, task-head routing checks, score distribution plots)

## Key limitations
- Performance can change a lot when moving across datasets, languages, or recording conditions.
- Subgroup metrics can be unstable when subgroup sample sizes are small.
- This work is research-only and has not been clinically validated.

## Safety note
This model family is for research. Any real-world use would need careful clinical validation, privacy protections, and ethical oversight.
