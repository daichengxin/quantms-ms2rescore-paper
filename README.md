# quantms, ms2rescore and multiple search engines enables deep proteome coverage across protein quantification, immunopeptidomics, and phosphoproteomics experiments

This repository contains the manuscript and supporting materials for the research paper "quantms, ms2rescore and multiple search engines enables deep proteome coverage across protein quantification, immunopeptidomics, and phosphoproteomics experiments" by:

- **Dai Chengxin**¹'² - State Key Laboratory of Medical Proteomics, Beijing Proteome Research Center, National Center for Protein Sciences (Beijing), Beijing Institute of Lifeomics, Beijing, China; International Academy of Phronesis Medicine (Guangdong), Guangdong, China
- **Ralf Gabriels**³ - VIB-UGent Center for Medical Biotechnology, VIB, 9052 Ghent, Belgium
- **Robbin Bouwmeester**³ - VIB-UGent Center for Medical Biotechnology, VIB, 9052 Ghent, Belgium
- **Jonas Scheid**⁴'⁵'⁶'⁷ - Department of Peptide-based Immunotherapy, Institute of Immunology, University and University Hospital Tübingen, Germany; Cluster of Excellence iFIT (EXC2180) "Image-Guided and Functionally Instructed Tumor Therapies", University of Tübingen, Germany; Quantitative Biology Center (QBiC), University of Tübingen, Germany; Institute for Bioinformatics and Medical Informatics (IBMI), University of Tübingen, Germany
- **Lennart Martens**³ - VIB-UGent Center for Medical Biotechnology, VIB, 9052 Ghent, Belgium
- **Oliver Kohlbacher**⁹ - Department of Computer Science, Applied Bioinformatics, University of Tübingen, Tübingen, Germany
- **Mingze Bai**⁸ - Chongqing Key Laboratory of Big Data for Bio Intelligence, Chongqing University of Posts and Telecommunications, Chongqing, China
- **Timo Sachsenberg**⁹ - Department of Computer Science, Applied Bioinformatics, University of Tübingen, Tübingen, Germany
- **Yasset Perez-Riverol**¹⁰ - European Molecular Biology Laboratory, European Bioinformatics Institute, Wellcome Genome Campus, Cambridge, United Kingdom

## Abstract

The exponential growth of public proteomics datasets has outpaced the capacity of traditional desktop tools for large-scale automated analysis. This study presents an integrated workflow combining quantms, a cloud-native pipeline, with MS2Rescore, a machine learning-driven rescoring tool, to enable deep reanalysis of massive proteomic datasets. Leveraging the Nextflow workflow engine for parallel computing, the pipeline integrates fragment ion intensity and retention time predictions from MS2PIP and DeepLC to optimize peptide-spectrum match reliability via Percolator.

## Key Findings

- **16-22.8% increase** in identified spectra compared to traditional approaches
- **Hundreds of newly quantified proteins and phosphosites** across diverse experimental designs
- Demonstrated improvements across:
  - Label-free quantification (LFQ)
  - TMT labeling
  - Immunopeptidomics
  - Phosphoproteomics

## Repository Structure

```
.
├── ms2rescore-quantms-mcp/
│   ├── main.tex                    # Main manuscript LaTeX file
│   ├── main.pdf                    # Compiled manuscript PDF
│   ├── references.bib              # Bibliography file
│   ├── mcp.bib                     # Additional bibliography
│   └── figures/                    # All manuscript figures
│       ├── PXD019643.png          # Immunopeptides results
│       ├── PXD001819.jpg          # LFQ benchmark results
│       ├── CPTAC_TMT.png          # TMT experiment results
│       ├── phospho2.png           # Phosphoproteomics results
│       ├── *_weights.png          # Feature weight analyses
│       └── PXD001819/             # Additional LFQ figures
├── README.md                       # This file
└── LICENSE                         # License information
```

## Methodology

### Datasets Analyzed

1. **PXD001819**: Sigma UPS1 proteins spiked into yeast lysate (LFQ benchmark)
2. **PXD019643**: HLA Class I immunopeptides
3. **PXD026824**: Phosphoproteomics dataset
4. **PDC000125**: CPTAC TMT dataset

### Workflow Configurations

The study evaluated five different workflow settings:
1. Comet alone
2. Comet + MSGF+
3. Comet + MS2Rescore
4. Comet + MSGF+ + MS2Rescore
5. Comet + MSGF+ + SAGE + MS2Rescore

### Key Technologies

- **quantms**: Cloud-based pipeline for quantitative proteomics
- **MS2Rescore**: Machine learning-driven rescoring tool
- **MS2PIP**: Fragment ion intensity prediction
- **DeepLC**: Retention time prediction
- **Percolator**: Statistical validation and FDR control
- **Nextflow**: Workflow management system

## Requirements

### Software Dependencies

- quantms pipeline
- MS2Rescore
- Nextflow
- OpenMS toolkit
- Percolator

### Data Access

All datasets used in this study are publicly available:
- **PRIDE Archive**: PXD001819, PXD019643, PXD026824
- **CPTAC**: PDC000125

## Reproducibility

This work follows FAIR (Findability, Accessibility, Interoperability, and Reusability) principles:

- All analyses use open-source tools
- Standard file formats employed throughout
- Reproducible execution environments
- Publicly available datasets
- Open workflow management with Nextflow

## Results Summary

### Label-Free Quantification (PXD001819)
- 17% improvement with multiple search engines
- Additional 16% improvement with MS2Rescore features
- Enhanced quantification of low-abundance UPS1 proteins

### TMT Experiments (CPTAC)
- 3.6% improvement in PSM identification
- 921 newly quantified proteins
- 27 newly quantified differentially expressed proteins

### Immunopeptidomics (PXD019643)
- 11.7% improvement with multiple search engines
- Additional 22.8% improvement with MS2Rescore
- Clear separation of target and decoy PSMs

### Phosphoproteomics (PXD026824)
- 19% improvement in spectra identification
- 17% increase in phosphorylated peptides at 0.01 FLR
- 350 newly identified protein phosphorylation sites

## Citation

If you use this work, please cite:

```bibtex
@article{dai_quantms_ms2rescore_2024,
    title = {quantms, ms2rescore and multiple search engines enables deep proteome coverage across protein quantification, immunopeptidomics, and phosphoproteomics experiments},
    author = {Dai, Chengxin and Gabriels, Ralf and Bouwmeester, Robbin and Scheid, Jonas and Martens, Lennart and Kohlbacher, Oliver and Bai, Mingze and Sachsenberg, Timo and Perez-Riverol, Yasset},
    journal = {[Journal Name]},
    year = {2024},
    note = {In preparation}
}
```

## Links

- [quantms pipeline](https://quant.ms.org/)
- [MS2Rescore](https://github.com/compomics/ms2rescore)
- [PRIDE Archive](https://www.ebi.ac.uk/pride/)
- [CPTAC](https://proteomics.cancer.gov/programs/cptac)

## Building the PDF

To generate the PDF from the LaTeX source:

### Prerequisites

Ensure you have a LaTeX distribution installed:
- **Linux/macOS**: Install TeX Live
- **Windows**: Install MiKTeX or TeX Live
- **Online**: Use Overleaf (https://overleaf.com)

### Required LaTeX Packages

The manuscript requires the following LaTeX packages:
- `amsmath`, `amssymb` - Mathematical symbols
- `graphicx` - Figure inclusion
- `geometry` - Page layout
- `setspace` - Line spacing control
- `authblk` - Author and affiliation formatting
- `cite` - Citation management
- `caption` - Figure caption formatting
- `subfigure` - Subfigures
- `natbib` - Bibliography management

### Compilation Steps

1. **Navigate to the manuscript directory:**
   ```bash
   cd ms2rescore-quantms-mcp/
   ```

2. **Compile the LaTeX document:**
   ```bash
   # First compilation
   pdflatex main.tex
   
   # Generate bibliography
   bibtex main
   
   # Second compilation (resolves citations)
   pdflatex main.tex
   
   # Third compilation (resolves cross-references)
   pdflatex main.tex
   ```

3. **Alternative single command:**
   ```bash
   latexmk -pdf main.tex
   ```

### Output Files

After successful compilation, you'll find:
- `main.pdf` - The final manuscript
- `main.aux` - Auxiliary file with references
- `main.bbl` - Bibliography file
- `main.blg` - Bibliography log
- `main.log` - Compilation log
- `main.synctex.gz` - SyncTeX file for editor integration

### Troubleshooting

- **Missing packages**: Install required LaTeX packages using your distribution's package manager
- **Figure errors**: Ensure all figures in the `figures/` directory are accessible
- **Bibliography errors**: Check that `references.bib` is properly formatted
- **Font issues**: Some systems may require additional font packages

### Online Compilation

For convenience, you can also compile the document online:
1. Upload the entire `ms2rescore-quantms-mcp/` folder to [Overleaf](https://overleaf.com)
2. Set `main.tex` as the main document
3. Compile using the platform's interface

## Contributing

This repository contains research materials. For questions or comments about the methodology or results, please contact the authors.

## Acknowledgments

Thank those who supported the research, including funding bodies and the proteomics community for making public datasets available. 