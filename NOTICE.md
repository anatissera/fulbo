# Third-party notices

FULBO is released under the [GNU Affero General Public License v3.0](LICENSE).

That is not a free choice. The whole pipeline is built on **Ultralytics**
(YOLO11 for detection, YOLOv8-pose for the pitch keypoints), which is licensed
under AGPL-3.0, and the AGPL requires work derived from it to carry the same
license. Ultralytics sells an Enterprise license for anyone who needs different
terms; that would also allow the parts of this repository that are ours to be
relicensed.

## Dependencies

| Component | Used for | License |
|---|---|---|
| [Ultralytics](https://github.com/ultralytics/ultralytics) | YOLO11 detection and YOLOv8-pose training and inference | AGPL-3.0 |
| [roboflow/supervision](https://github.com/roboflow/supervision) | detection containers, ByteTrack, annotators | MIT |
| [roboflow/sports](https://github.com/roboflow/sports) | pitch configuration and minimap rendering | MIT |
| [DINOv2](https://github.com/facebookresearch/dinov2), via `transformers` | player appearance embeddings | Apache-2.0 |
| [umap-learn](https://github.com/lmcinnes/umap) | dimensionality reduction | BSD-3-Clause |
| scikit-learn, OpenCV, NumPy, pandas, matplotlib, PyTorch | general numerical and imaging work | BSD-3-Clause / Apache-2.0 / MIT |

## Code adapted from sources with no license

Two parts of the data preparation package are adapted from public repositories
that carry no license file. Under default copyright, their authors retain all
rights, so nothing here grants permission over that code:

- `src/data_prep/keypoints/datatools_29/` is adapted from
  [Adit-jain/Soccer_Analysis](https://github.com/Adit-jain/Soccer_Analysis)
  (no license file as of December 2025).
- `src/data_prep/keypoints/datatools_57/` is adapted from
  [NikolasEnt/soccernet-calibration-sportlight](https://github.com/NikolasEnt/soccernet-calibration-sportlight)
  (no license file as of December 2025).

They are included with attribution for a university coursework project. Anyone
reusing this repository beyond that should contact those authors directly: the
AGPL grant in [LICENSE](LICENSE) covers our own work and cannot cover theirs.

## Data

The datasets are not redistributed here. Both the calibration and tracking
splits come from [SoccerNet](https://www.soccer-net.org/), which releases them
for research purposes; the download is password protected and the password is
under an NDA. `data/` is not tracked, and `data/README.md` explains how to
regenerate everything from the original source.

The sample batch previews under `models/` (`train_batch*.jpg`,
`val_batch*.jpg`) contain frames from SoccerNet broadcast footage. They are kept
only as training diagnostics for the runs that were archived.
