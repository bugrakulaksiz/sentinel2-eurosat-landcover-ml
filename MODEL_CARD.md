# Model Card — EuroSAT RGB SmallCNN

**Task:** Educational 10-class land-cover classification using Sentinel-2 RGB patches from EuroSAT (64 × 64).

**Data:** 27,000 images. Random stratified training/validation/test split: 18,900 / 4,050 / 4,050, seed 42. Training used random horizontal and vertical flipping.

**Model:** A small custom PyTorch CNN with 1,143,242 trainable parameters.

**Optimization:** Adam, learning rate 0.001, cross-entropy loss, six epochs. Best checkpoint chosen by validation accuracy (80.02% at epoch five).

**Independent evaluation:** Held-out test accuracy 80.9383% (3,278 / 4,050); macro F1 0.801. Highway recall: 52.3%; 62 Highway samples were predicted as River.

**Limitations:** The random split does not test independent geographic generalization; only RGB bands used. Visual resemblance between roads and rivers is a plausible hypothesis for some errors, not a proven cause. Not suitable for safety-critical, regulatory, or operational land-cover mapping.

**Reproducibility:** Use `EuroSAT_Land_Cover_Classification.ipynb`. Original evaluation artifacts are stored in `results/`; saved checkpoint is stored in `models/`.
