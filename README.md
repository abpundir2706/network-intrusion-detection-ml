# Network Intrusion Detection using Machine Learning

Multi-class classification project predicting network attack type (Normal, DoS, Probe, R2L, U2R)
from connection-level features, using the NSL-KDD benchmark dataset.

## Contents

```
network_intrusion_detection.ipynb   -- the complete project notebook (already executed, with outputs)
requirements.txt                    -- exact Python library versions used
data/
    KDDTrain+.txt                   -- training data (125,973 records)
    KDDTest+.txt                    -- test data (22,544 records)
```

## How to run

1. Install the required libraries:
   ```
   pip install -r requirements.txt
   ```

2. Make sure the `data/` folder sits in the **same directory** as the notebook (this is already
   the case if you keep this folder structure intact).

3. Open the notebook:
   ```
   jupyter notebook network_intrusion_detection.ipynb
   ```

4. Run all cells (Cell -> Run All), or just read through — all outputs and charts are already
   saved in the notebook from a prior full run, so you can view results without re-running anything.

## Data source

NSL-KDD dataset, originally published by the Canadian Institute for Cybersecurity, University of
New Brunswick (https://www.unb.ca/cic/datasets/nsl.html). It is an improved, deduplicated version
of the original KDD Cup 1999 intrusion detection benchmark.

## Project summary

- **Problem:** classify network connections as normal traffic or one of 4 attack categories
- **Models used:** Random Forest, XGBoost (compared side by side)
- **Key techniques:** feature selection, categorical encoding, SMOTENC for class imbalance
- **Result:** XGBoost achieved ~76-77% accuracy and macro F1 ~0.57 after addressing class imbalance
- **Key finding:** a large share of the model's weakest-performing category (R2L) failures are
  traced back to attack types that never appeared in the training data at all — a genuine,
  explainable limitation rather than a simple tuning issue

See the notebook itself for the full step-by-step explanation of every stage of the pipeline.
