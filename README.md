# Model selection with the Regularized Map Equation

Companion code for the paper **"Reliable data clustering with Bayesian community detection"** by Magnus Neuman, Jelena Smiljanić, and Martin Rosvall ([arXiv:2510.15013](https://arxiv.org/abs/2510.15013)).

The notebook shows the one-step approach from the paper on synthetic correlational data: it uses the Regularized Map Equation to pick the correlation threshold and the clusters at the same time, by maximizing the description-length compression. This replaces the usual two steps — first threshold the correlation matrix, then cluster it — with a single, principled model-selection step that uses all the samples.

## What the notebook does

`Model selection with correlational data.ipynb` has four components:

1. Generate synthetic data with a known (planted) cluster structure.
2. Compare the observed correlations with the theoretical within- and between-cluster distributions.
3. Scan thresholds and pick the one that compresses the description length most.
4. Infer the clusters at that threshold and compare them with the planted structure using the adjusted mutual information (AMI).

Thresholding is done on the absolute correlation, so negative correlations are kept.

## Requirements

- Python 3.10 or later
- [`infomap`](https://www.mapequation.org)
- `networkx` (>= 3.0)
- `numpy`, `scipy`, `scikit-learn`, `matplotlib`

Install with:

```bash
pip install infomap "networkx>=3.0" numpy scipy scikit-learn matplotlib
```

## Running

Open the notebook and run the cells from top to bottom:

```bash
jupyter notebook "Model selection with correlational data.ipynb"
```

The random seed is fixed, so the figures are reproducible.

## Citation

If you use this code, please cite the paper:

```bibtex
@article{neuman2025reliable,
  title         = {Reliable data clustering with Bayesian community detection},
  author        = {Neuman, Magnus and Smiljani\'c, Jelena and Rosvall, Martin},
  year          = {2025},
  eprint        = {2510.15013},
  archivePrefix = {arXiv},
  primaryClass  = {stat.ML},
  url           = {https://arxiv.org/abs/2510.15013}
}
```

## Contact

Magnus Neuman — magnus.neuman@umu.se
