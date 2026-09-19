# MTG-MaxViTX configuration files

The three YAML files reproduce the configuration values embedded in the supplied notebooks.

| Notebook | Configuration | Intended execution profile |
| --- | --- | --- |
| `MTG_MaxViTX_Final.ipynb` | `MTG_MaxViTX_Final.yaml` | Corrected Q1 resume run with full five-seed baselines and proposed-model experiments |
| `MTG_MaxViTX_Final_1.ipynb` | `MTG_MaxViTX_Final_1.yaml` | Full data preparation, primary training, refinement, V6 balanced ensemble, and evaluation pipeline |
| `MTG_MaxViTX_Final_2.ipynb` | `MTG_MaxViTX_Final_2.yaml` | Corrected Q1 resume run with full five-seed baselines and proposed-model experiments |

The resume configurations intentionally retain the values used in the corresponding notebooks: 256 × 256 input, classification batch size 16, segmentation batch size 8, AdamW with a learning rate of `2e-4`, weight decay of `1e-4`, 12 epochs, patience 3, one ablation seed, and five seeds for baseline and proposed-model reproducibility runs.

`MTG_MaxViTX_Final_1.yaml` retains the broader 30-epoch primary-training profile and its separate classification and segmentation refinement settings. The common Python dependencies used across all three notebooks are listed in `requirements.txt`. Only `timm` was version-pinned in the notebooks, so the remaining packages are left unpinned rather than assigning unsupported versions.

These YAML files are configuration records. The supplied notebooks currently define their constants directly in code and do not automatically read YAML. To make YAML values control execution, add a YAML-loading cell before the existing configuration cell and map the required keys to the notebook variables.
