Model weights are hosted on Kaggle (public datasets):
- Detector: `guillermolpezprez/detector-clean` → `detector_clean_ep25.pt`
- Re-ID:    `guillermolpezprez/rpp-final`      → `rpp_final.pt`

## How to Run

This project runs on **Kaggle** with GPU acceleration.

1. Open `main.ipynb` on Kaggle.
2. Add the following datasets as inputs:
   - `edoardomerli/prw-person-re-identification-in-the-wild` (PRW dataset)
   - `guillermolpezprez/detector-clean` (detector weights)
   - `guillermolpezprez/rpp-final` (Re-ID weights)
3. Enable GPU accelerator (Settings → Accelerator → GPU T4 x2).
4. Run all cells. Training cells are disabled by default — the notebook
   loads pre-trained weights and runs inference directly.

## Dependencies

All dependencies are pre-installed in the Kaggle environment:
- PyTorch 2.x
- torchvision
- torchmetrics
- scipy
- scikit-learn
- Pillow
- numpy
- matplotlib

## Results

| System | mAP | Rank-1 |
|---|---|---|
| Full pipeline (detector + Re-ID) | 48.56% | 86.05% |
| PCB+RPP paper (PRW) | ~45% | ~75% |
| SeqNet state-of-the-art | 57.5% | 87.6% |
