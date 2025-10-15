# A Genome-wide Computational Model of DNA Probe Accessibility

This project provides a Python-based pipeline for performing an exhaustive, dual-strand analysis of DNA probe accessibility. The model calculates the probability of a short (5-mer) probe binding to a target sequence by accounting for the confounding effects of local secondary structure under specific, non-standard experimental conditions (high temperature and 70% formamide).

The core of the model uses the ViennaRNA package to calculate per-base and per-site unpaired probabilities over the entire thermodynamic ensemble of possible structures. This notebook is a complete, streamlined pipeline that goes from a raw genome FASTA file to a rich set of publication-quality visualizations.

### Key Features
- **Exhaustive Analysis:** Analyzes every fragment of the genome, not just a sample, providing a complete accessibility map.
- **Dual-Strand Model:** Critically, it calculates accessibility for both the **forward** and **reverse complement** strands at every genomic locus, defining accessibility as the best opportunity on either strand.
- **Multi-Level Reporting:** Generates insights at three key levels:
  1.  **Locus Level:** Identifies which large genomic regions are generally accessible or inaccessible.
  2.  **Per-Site Level:** Provides the most granular view, showing the accessibility of every single possible 5-mer target.
  3.  **Per-Motif Level:** Aggregates data by sequence to identify which 5-mer motifs are intrinsically easy or difficult to target.
- **Rich, Interactive Visualizations:** Creates a comprehensive report including:
  - Genome-wide "browser track" plots showing accessibility hotspots.
  - High-resolution smoothed tracks that highlight problematic regions.
  - Correlation plots that visualize strand asymmetry.
  - An interactive global profile of all 1024 possible 5-mer motifs.
- **Built for Reproducibility:** Includes a Conda `environment.yml` file to recreate the exact computational environment.

---

### How to Run This Analysis

#### Prerequisites
- **Git:** To clone the repository.
- **Conda / Miniconda:** To manage the Python environment. ([Installation Guide](https://docs.conda.io/en/latest/miniconda.html))

#### 1. Clone the Repository
Open your terminal and clone this project to your local machine:
```bash
git clone [https://github.com/YourUsername/genome-accessibility.git](https://github.com/YourUsername/genome-accessibility.git)
cd genome-accessibility

#### 2. Create and Activate the Conda Environment
This project's dependencies are specified in the `environment.yml` file. Use it to create a new, isolated environment. This step ensures that all the correct library versions are installed and is critical for reproducibility.

```bash
# Create the environment named 'genome-access'
conda env create -f environment.yml

# Activate the new environment
conda activate genome-access