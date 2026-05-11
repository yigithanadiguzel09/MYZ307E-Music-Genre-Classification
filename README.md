# Audio Classification and Music Genre Recognition Using CNNs

**MYZ307E — Machine Learning for Electrical and Electronics Engineering**
Istanbul Technical University · Spring 2026

Term project replicating the Tzanetakis & Cook (2002) music genre classification
baseline and proposing a CNN-based extension with audio data augmentation and
architectural regularization.

## Team

| Name | Student ID |
|---|---|
| Yiğithan Adıgüzel | 040220347 |
| Zeynep Tutumlu | 040200419 |
| Aybüke Çaylak | 040200423 |
| Ozan Temel | 040200401 |

**Instructor:** Dr. Sümeye Nur Karahan

## Results Summary

| Model | Method | Test Accuracy |
|---|---|---|
| Tzanetakis & Cook (2002) — original | 30-dim + GMM-3 | 61.00%* |
| Our replication | 30-dim + GMM-3 | 54.15% |
| Our replication | 30-dim + kNN-5 | 58.26% |
| Baseline MLP | MLP, no augmentation | 40.00% |
| Augmented MLP | MLP + augmentation | 41.87% |
| CNN basic | CNN + augmentation | 71.53% |
| CNN V2 | CNN + high dropout | 70.85% |
| **CNN V3 (train-time)** | **CNN + L2 + GAP + ReduceLR** | **76.20%** |
| **CNN V3 (re-evaluated)** | same model, regenerated split | **68.25%** |

\*as reported in the original paper

The CNN V3 model exceeds the Tzanetakis baseline by 10–18 percentage points
depending on the test split realization (see Sturm, 2013 for the well-known
GTZAN split sensitivity).

## Repository Structure
