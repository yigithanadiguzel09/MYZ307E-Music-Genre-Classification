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
depending on the test split realization (see Sturm, 2013 for the GTZAN split sensitivity).

## Repository Structure
.
├── notebooks/         Jupyter notebooks (CNN training, baseline replication)
├── figures/           Result plots: confusion matrix, F1 chart, comparisons
├── results/           CSV outputs from evaluation
├── report/            Final IEEE report and presentation slides
└── requirements.txt   Python dependencies

## Reproducing the Results

1. Clone this repository:
```bash
   git clone https://github.com/yigithanadiguzel09/MYZ307E-Music-Genre-Classification.git
```
2. Open the notebooks in Google Colab or run locally:
```bash
   pip install -r requirements.txt
```
3. The notebooks download the GTZAN dataset directly from Kaggle. You need a
   Kaggle API key in `~/.kaggle/kaggle.json`.
4. Run `notebooks/MYZ_Project_v2.ipynb` end-to-end (~2 hours on a T4 GPU).

## Dataset

[GTZAN Music Genre Classification](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification)
— 1,000 audio tracks across 10 genres, 30 seconds each, at 22,050 Hz.

## References

- G. Tzanetakis and P. Cook, "Musical genre classification of audio signals,"
  *IEEE Trans. Speech Audio Process.*, vol. 10, no. 5, pp. 293–302, 2002.
- B. L. Sturm, "The GTZAN dataset: Its contents, its faults, their effects on
  evaluation, and its future use," *arXiv:1306.1461*, 2013.

## License

MIT License — see [LICENSE](LICENSE).
