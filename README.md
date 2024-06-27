[![Python package](https://img.shields.io/pypi/v/adaMVP.svg?color=brightgreen&label=python-package)](https://pypi.org/project/adaMVP)

# Application of A3D3a's MVP (adaMVP)
This is the application of official codebase for **adaMVP: Probabilistic graph-based model uncovers druggable vulnerabilities in major solid cancers.**

## What is A3D3a's MVP?
A3D3a’s MVP (Adaptive AI-Augmented Drug Discovery and Development Molecular Vulnerability Picker) is a novel graph-based, cooperativity-led Markov chain model, developed and maintained by [Bissan Al-lazikani lab](https://faculty.mdanderson.org/profiles/bissan_al_lazikani.html) at the University of Texas MD Anderson Cancer Center. The algorithm exploits cooperativity of weak signals within a cancer molecular network to enhance the signal of true molecular vulnerabilities. 

## Workflow of A3D3a's MVP
![workflow](https://github.com/YingZ-A3D3a/A3D3a_MVP/blob/main/docs/workflow.png)

## Installation

adaMVP works with Python >= 3.8. Please make sure you have the correct version of Python installed pre-installation.

We highly recommend using an isolated python environment using [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) or [virtualenv](https://docs.python.org/3/library/venv.html).
1. Create python>=3.8 environment
   - Using conda: `conda create -n ada_mvp python=3.8`
   - Using virtualenv: `python -m venv ada_mvp`

2. Activate environment
   - Using conda: `conda activate ada_mvp`
   - Using virtualenv: `source ada_mvp/bin/activate`

3. After setting the environment, you could install adaMVP via pip:

```bash
pip install adaMVP
```

4. (optional) Setup jupyter lab
- Install the ipython kernel: `pip install -U ipykernel`
- Install jupyter lab: `pip install jupyterlab`
- Introduce the virtual environment to jupyter: `python -m ipykernel install --user --name 'ada_mvp'`
- Open/Start Jupyter by typing `jupyter lab` and select the created kernel `ada_mvp`

## Preparing INPUTS
#### Preparing your seed genes input file (mandatory)
This csv file must include two column names 'Gene' and 'Freq'. The 'Gene' column should have a list of genes with official gene symbols (HGNC symbols), and the 'Freq' column should be a list of numeric numbers between 0 and 1 representing the altered freq of a gene within the populations. An example file can be downloaded at [example input file](https://github.com/YingZ-A3D3a/A3D3a_MVP/blob/main/input/TCGA_BRCA_DNA_altered_freq.csv). 
The recommended number of seed genes is between 50-200. For data from multiple modalities, e.g. mutation, CNV, RNA, the 'Freq' can be set as the maximum altered frequency across modalities. Please read the method part of the manuscript for detailed explanations.

#### RNA expression data for filtering expressed genes in first neighbors
The RNA expression matrix should have gene symbols (HGNC symbols) as row indices and sample names as column indices. The RNA expression matrix can contain either raw counts or log normalized counts.

### Tutorial
#### Find first neighbors, filter the expressed genes, and build MVP model for prioritizing molecular vulerabilities
The tutorial for running the adaMVP pipeline can be found at 

[build graph and community detection]()





