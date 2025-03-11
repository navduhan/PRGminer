# PRGminer: Deep Neural Network-Based Plant Resistance Gene Prediction

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Python 3.7+](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Bioinformatics](https://img.shields.io/badge/Bioinformatics-Tool-brightgreen.svg)](https://bioinfo.usu.edu/PRGminer/)

## Overview

PRGminer is a state-of-the-art bioinformatics tool that employs deep learning to predict and classify plant resistance genes (R-genes). The tool implements a two-phase prediction approach:

1. **Phase 1**: Binary classification of sequences as R-genes or non-R-genes
2. **Phase 2**: Detailed classification of R-genes into eight distinct categories:
   - CNL (Coiled-coil NBS-LRR)
   - KIN (Kinase)
   - LYK (Lysin Motif Kinase)
   - LECRK (Lectin Receptor Kinase)
   - RLK (Receptor-like Kinase)
   - RLP (Receptor-like Protein)
   - TIR (Toll/Interleukin-1 Receptor)
   - TNL (TIR-NBS-LRR)

## Features

- 🧬 Advanced deep learning models for accurate R-gene prediction
- 🔄 Two-phase prediction pipeline
- 📊 Detailed probability scores for each prediction
- 🚀 Fast and efficient processing
- 💻 User-friendly command-line interface
- 📝 Comprehensive output reports

## Requirements

### System Requirements
- Linux or macOS operating system
- Python 3.7 or higher
- 4GB RAM (minimum)
- 2GB free disk space

### Dependencies
- TensorFlow 2.x
- Keras
- NumPy
- Pandas
- Biopython
- Scikit-learn

## Installation

Choose one of the following installation methods:

### 1. Using Git and Conda (Recommended)

```bash
# Clone the repository
git clone https://github.com/navduhan/PRGminer.git
cd PRGminer

# Create and activate conda environment
conda env create -f environment.yml
conda activate PRGminer

# Install the package
pip install .
```

### 2. Using Miniconda

```bash
# Download PRGminer
wget https://kaabil.net/PRGminer/download/PRGminer.tar.gz
tar -xvzf PRGminer.tar.gz
cd PRGminer

# Create and activate environment
conda env create -f environment.yml
conda activate PRGminer
pip install .
```

### 3. Using System Python

```bash
# Download and extract
wget https://kaabil.net/PRGminer/download/PRGminer.tar.gz
tar -xvzf PRGminer.tar.gz
cd PRGminer

# Install
pip install .
```

## Usage

### Basic Usage

```bash
PRGminer -i <input.fasta> -od <output_directory> -l <prediction_level>
```

### Command-line Arguments

| Argument | Description | Default |
|----------|-------------|---------|
| `-i, --fasta_file` | Input protein sequences in FASTA format | Required |
| `-od, --output_dir` | Output directory for results | PRGminer_results |
| `-l, --level` | Prediction level (Phase1 or Phase2) | Phase2 |
| `-o, --output_file` | Output file name | PRGminer_results.txt |

### Example

```bash
# Phase 1 prediction (R-gene vs non-R-gene)
PRGminer -i proteins.fasta -od results_phase1 -l Phase1

# Phase 2 prediction (detailed classification)
PRGminer -i proteins.fasta -od results_phase2 -l Phase2
```

## Input Format

PRGminer accepts protein sequences in FASTA format only. Example:

```fasta
>protein1
MAEGEQVQSGEDLGSPVAQVLQKAREQGAQAAVLVVPPGEEQVQSAEDLGSPVAQVLQKA
>protein2
MTKFTILLFFLSVALASNAQPGCNQSQTLSPNWQNVFGASAASSCP
```

⚠️ Note: Nucleotide sequences are not supported.

## Output Files

### Phase 1 Output (Phase1_dnn_log.txt)
```
SeqID    Prediction    Rgene    Non-Rgene
prot1    Rgene        0.92     0.08
prot2    Non-Rgene    0.15     0.85
```

### Phase 2 Output (Phase2_dnn_log.txt)
```
SeqID    Prediction    CNL     KIN     LYK     LECRK    RLK     RLP     TIR     TNL
prot1    CNL          0.85    0.02    0.03    0.02     0.02    0.02    0.02    0.02
```

## Performance Considerations

- Processing time depends on:
  - Number of input sequences
  - Sequence lengths
  - Available computational resources
- Recommended batch size: < 1000 sequences
- For large datasets, consider splitting into smaller batches

## Troubleshooting

Common issues and solutions:

1. **Invalid sequence format**
   - Ensure sequences are in proper FASTA format
   - Verify sequences contain valid amino acids only

2. **Memory errors**
   - Reduce batch size
   - Close unnecessary applications
   - Increase system swap space

3. **Installation issues**
   - Verify Python version compatibility
   - Check for conflicting dependencies
   - Ensure proper environment activation

## Citation

If you use PRGminer in your research, please cite:

<!-- ```bibtex
@article{PRGminer2023,
    author = {Duhan, Naveen and Kaundal, Rakesh},
    title = {PRGminer: Deep learning-based prediction and classification of plant resistance genes},
   
}
``` -->

## Support

### Technical Support
For bugs and technical issues:
- Create an issue on GitHub
- Email: naveen.duhan@usu.edu

### Scientific Inquiries
For questions about the methodology:
- Dr. Rakesh Kaundal: rkaundal@usu.edu
- Naveen Duhan: naveen.duhan@usu.edu

## License

PRGminer is released under the [GNU General Public License v3](LICENSE).

## Acknowledgments

This work was supported by the Kaundal Bioinformatics Lab at Utah State University.

---
© 2023 Kaundal Bioinformatics Lab, Utah State University



