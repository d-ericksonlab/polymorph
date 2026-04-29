# polymorph

Companion code for *"Raman-Grounded Multimodal Sensing of CaCO₃ Polymorphs
during Microfluidic Biomineralization"* (Filanoski & Erickson, ACS Sensors,
under review).

## What's here

A single Colab notebook (`polymorph_pipeline.ipynb`) that walks through the
full polymorph identification pipeline on four representative channels:

1. Load Raman ground-truth labels
2. Plot raw Raman spectra grouped by polymorph class
3. Overlay Raman point locations on the brightfield image
4. Color the points by Raman-derived polymorph label
5. Cellpose instance segmentation
6. Label propagation: Cellpose masks colored by Raman ground truth
7. EfficientNet-B0 polymorph classifier predictions
8. Classifier predictions vs. Raman ground truth

## Running the notebook

Open `polymorph_pipeline.ipynb` in Google Colab. The notebook expects the
companion dataset (Zenodo DOI 10.5281/zenodo.19868283), including the trained
Cellpose and EfficientNet-B0 model weights. Edit `PUB_DIR`, `MODEL_PATH`,
and `CLASSIFIER_PATH` in the relevant cells to point at your local copy.

GPU recommended; works on CPU with longer runtime.

## Data

Available on Zenodo: https://doi.org/10.5281/zenodo.19868283

Includes:
- `raman_data.parquet` — 550 Raman-labeled training points across 5 sets
- Raw spectra (CSV + TXT) for the 4 example channels
- Brightfield + polarized-light PNGs for the 4 example channels
- Trained Cellpose model (`cellpose_5set`)
- Trained polymorph classifier (`model5_3class_best.pth`)

## Citation

If you use this code or data, please cite the accompanying paper and the
Zenodo deposit.

## License

MIT (see `LICENSE`).
