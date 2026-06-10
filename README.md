# Person Search on PRW Dataset

## Project Structure

```
main.ipynb   — main notebook (all code + explanations)
README.md    — this file
```

## Kaggle Datasets Required

Add the following datasets as inputs to the Kaggle notebook:

| Dataset | Content |
|---|---|
| `edoardomerli/prw-person-re-identification-in-the-wild` | PRW dataset |
| `guillermolpezprez/detector-clean` | Detector weights (`detector_clean_ep25.pt`) |
| `guillermolpezprez/rpp-final` | Re-ID weights (`rpp_final.pt`) |
| `guillermolpezprez/retinanet-detector-architecture` | Detector architecture diagram |
| `guillermolpezprez/pcb-reid-architecture` | Re-ID architecture diagram |

## How to Run

This project runs on **Kaggle** with GPU acceleration.

1. Open `main.ipynb` on Kaggle.
2. Add all five datasets listed above as inputs.
3. Enable GPU accelerator (Settings → Accelerator → GPU T4 x2).
4. Run all cells. Training cells are disabled by default, the notebook loads pre-trained weights and runs inference directly.

## File Paths (automatically set by Kaggle)

```
PRW dataset:   /kaggle/input/datasets/edoardomerli/prw-person-re-identification-in-the-wild/
Detector:      /kaggle/input/datasets/guillermolpezprez/detector-clean/detector_clean_ep25.pt
Re-ID:         /kaggle/input/datasets/guillermolpezprez/rpp-final/rpp_final.pt
Diagram 1:     /kaggle/input/datasets/guillermolpezprez/retinanet-detector-architecture/retinanet_detector_architecture.svg
Diagram 2:     /kaggle/input/datasets/guillermolpezprez/pcb-reid-architecture/pcb_reid_architecture.svg
```

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
| **Full pipeline (detector + Re-ID)** | **48.90%** | **86.53%** |
| NAE+SeqNet+CBGM (Li et al., 2021) | 47.6% | 87.6% |
