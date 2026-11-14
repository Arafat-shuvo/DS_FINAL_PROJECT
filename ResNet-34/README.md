
Respiratory Disease Classification — ResNet-34 (scratch + ImageNet-pretrained) on Log-Mel (ICBHI) — ALL 8 optimizers in one notebook
Runs 8 optimizers — Adam, AdamW, SGD (momentum=0.9), RMSprop, NAdam, RAdam, Adamax, Adagrad — with two ResNet-34 variants: scratch (random init) and pretrained (ImageNet weights, full fine-tuning), each with 2 learning rates (0.001, 0.0001) × 5 seeds (42, 123, 2024, 7, 2025) = 20 runs per optimizer, 160 runs in total. Preprocessing, features, patient-level split (split_seed=42), batch size 32, max 150 epochs, patience 15 and the metrics are identical to the earlier notebooks, so results are directly comparable. All optimizers use PyTorch defaults except the learning rate. No class weighting, oversampling or augmentation.

Pretrained weights: the notebook first tries the torchvision download (needs Internet enabled in the Kaggle notebook settings). If that fails it looks for a resnet34*.pth file in /kaggle/input (add a dataset containing it). It never silently falls back to random weights. Tip: run once with RESP_SMOKE_TEST=1 (2 epochs, 1 seed, 1 LR) to confirm everything works before the full run.

Outputs (only the main things):

/kaggle/working/resnet34_csv/ — 8 CSV files, one per optimizer (resnet34_<optimizer>_results.csv, one row per run).
/kaggle/working/resnet34_download_5parts/ — a zip (the 8 CSVs + all main figures) split into 5 parts for easy download, plus rejoin instructions.
No model checkpoints are saved; the feature cache and per-run files live in a temp folder outside /kaggle/working.
Stem conv is changed to 1 input channel (pretrained: RGB filters summed); the final layer is Dropout(0.5) + Linear(512, 8). Time note: 160 ResNet-34 runs is long. Keep the session alive until the end (the temp folder is lost if the session restarts).
