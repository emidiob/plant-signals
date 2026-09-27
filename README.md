# Plant Signals

Building AI course project

## Summary

Plant Signals is a proposed installation that learns patterns in plant-related sensor data and translates unusual changes into images and sound. It makes environmental relationships perceptible while showing the uncertainty of its interpretations.

## Background

Changes in a plant's surroundings can be difficult to notice: soil moisture, light and temperature fluctuate over hours and days. A single sensor reading offers little context, and an expressive visualization can easily make an uncertain interpretation look like a fact.

This project explores how machine learning can reveal patterns in these measurements and support an artistic encounter with a living environment. Its motivation comes from an interdisciplinary practice concerned with AI, image culture and non-human agency.

The initial goal is an interpretable installation for a small collection of indoor plants. Its usefulness and reliability remain to be tested. It is a project proposal, not a completed or scientifically validated system.

## How is it used?

An artist or educator places soil-moisture, temperature and light sensors around a plant. A local computer displays recent measurements, compares them with that plant's previous observations, and generates a visual or sonic response.

1. Collect a baseline across several weeks, including ordinary watering and changes in daylight.
2. Record events such as watering, sensor repositioning and equipment faults.
3. Analyze short time windows and flag unusual measurement patterns.
4. Map those patterns to changes in image brightness, texture, sound pitch or rhythm.
5. Let visitors inspect the measurements and the reason for each alert alongside the artwork.

The interface distinguishes measured values, model estimates and artistic interpretations. It includes a sensor-status indicator and pauses interpretation when data is missing or unreliable. Audio should be optional, with a visual alternative for accessibility.

Artists, exhibition visitors, educators and plant caretakers are the intended users. Caretakers retain responsibility for plant care; the installation does not automatically change watering or lighting.

## Data sources and AI methods

The first dataset would be collected specifically for this project. No dataset has yet been collected or evaluated. It would contain timestamps, plant identifiers, sensor readings, equipment checks and manually logged events. Camera images and personal visitor data are unnecessary for the first version.

| Stage | Proposed approach |
| --- | --- |
| Data preparation | Check calibration, flag missing readings, aggregate measurements into consistent time intervals and scale features using training data only. |
| Baseline | Compare the model with simple moisture thresholds and a persistence forecast. |
| Prediction | Use linear regression to estimate the next soil-moisture reading from recent moisture, temperature and light measurements. |
| Pattern comparison | Use nearest-neighbor distances between measurement windows to identify patterns unlike those in the baseline. |
| Interpretation | Display prediction residuals, distances and contributing measurements. Treat an anomaly as an unusual observation, not a diagnosis. |
| Artistic output | Use an explicit, documented mapping from measurements and model outputs to image and sound parameters. |

Training and evaluation would use separate chronological periods rather than randomly mixing adjacent readings. Scaling and alert thresholds would be fitted on training and validation data, with the final test period held aside. Evaluation would report moisture prediction error, alerts per day and a manual review of alerts against event logs. Performance on additional plants would be tested separately before claiming generalization.

## Challenges

Sensor drift, sunlight variation, different soil types and plant species may change the data. A model trained on one plant may perform poorly on another. Few labeled examples make claims about plant health especially uncertain.

The project cannot infer a plant's thoughts, feelings or intentions. It does not translate a plant language, prove consciousness or diagnose disease. Visual and sonic outputs are human-designed interpretations of measurements. Exhibition text should make this distinction explicit.

Plants must be cared for independently of the experiment. Deliberately harming or withholding necessary care from plants to obtain unusual data is outside the proposed method. Electrical safety, sensor maintenance and energy use also matter in an installation setting.

## What next?

Start with one instrumented plant and a display of raw measurements. After collecting a baseline, add regression and nearest-neighbor analysis, evaluate them against simple rules, and develop a small installation prototype.

Further development would benefit from a plant-care specialist, a collaborator experienced with sensors and a sound artist. A later release could share appropriately documented measurements, reproducible analysis and the artistic mapping so others can examine the system's assumptions.

## Acknowledgments

- The Building AI course by the University of Helsinki and Reaktor provided the project structure and the introduction to regression, nearest-neighbor methods and overfitting.
- The conceptual motivation is the relationship between non-human environments, artistic interpretation and machine learning.
- No third-party code, images or dataset are included. Any future dependencies or reused materials should be credited with their respective licenses.
