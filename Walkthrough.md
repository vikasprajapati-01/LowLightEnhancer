# Performance Evaluation — Walkthrough

## What Was Done
Injected **8 evaluation cells** (1 markdown + 7 code) into `main.ipynb` after the training cell (Cell 23). A backup was saved as `main_backup.ipynb`.

**Total cells: 24 → 32**

## New Cells Added (Cells 24–31)

| Cell | Type | Purpose |
|------|------|---------|
| 24 | Markdown | Section header explaining the 3 metrics (PSNR, SSIM, MAE) |
| 25 | Code | **Loss Curves** — plots all 5 training losses over epochs |
| 26 | Code | **Metric Functions** — defines `compute_psnr`, `compute_ssim`, `compute_mae` with docstrings explaining the math |
| 27 | Code | **Test Set Evaluation** — runs all 15 eval images, computes metrics for both original→GT and enhanced→GT, prints per-image table + averages |
| 28 | Code | **Bar Charts** — per-image PSNR/SSIM/MAE comparison (red=original, green=enhanced) |
| 29 | Code | **Visual Comparison** — [Original → Enhanced → Ground Truth] grid for 5 images with metrics annotated |
| 30 | Code | **Histogram Analysis** — brightness distributions overlaid for 3 images |
| 31 | Code | **Final Report** — clean summary with model config, metrics, and interpretation |

## How to Run
1. Open `main.ipynb` in Google Colab (or Jupyter/VS Code)
2. Mount Google Drive first (if using Colab)
3. Run **all cells from the top** (Cells 0–23 train the model first)
4. Cells 24–31 will evaluate performance after training completes
5. No additional packages needed — uses only `tensorflow`, `numpy`, `matplotlib` already imported

## Google Colab Path Changes
When running on Colab, update these paths:
- `TRAIN_VAL_IMAGE_DIR` → `/content/drive/MyDrive/LowLightImageEnhancer/lol_dataset/our485/low`
- `TEST_IMAGE_DIR` → `/content/drive/MyDrive/LowLightImageEnhancer/lol_dataset/eval15/low`
- `TEST_LOW_DIR` → `/content/drive/MyDrive/LowLightImageEnhancer/lol_dataset/eval15/low`
- `TEST_HIGH_DIR` → `/content/drive/MyDrive/LowLightImageEnhancer/lol_dataset/eval15/high`

## Validation
- Verified notebook JSON has 32 cells with correct structure
- All new cells reference variables from earlier cells (`zero_dce_model`, `history`, `IMAGE_SIZE`, etc.)
- Helper scripts cleaned up; only `main.ipynb` and `main_backup.ipynb` remain
