# PDF Mining and Auto-screening for Literature Reviews

## Licence

[![CC BY-NC 4.0][cc-by-nc-shield]][cc-by-nc]  [![CC BY-NC 4.0][cc-by-nc-image]][cc-by-nc]

This work is licensed under a
[Creative Commons Attribution-NonCommercial 4.0 International License][cc-by-nc].  

[cc-by-nc]: https://creativecommons.org/licenses/by-nc/4.0/
[cc-by-nc-image]: https://licensebuttons.net/l/by-nc/4.0/88x31.png
[cc-by-nc-shield]: https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg


## Code

[Please visit here for the code and citation information](https://doi.org/10.5281/zenodo.12872948)


## Introduction

This repository contains the Python scripts developed for the automatic screening process in our study, [A Systematic Review of Aspect-based Sentiment Analysis (ABSA): Domains, Methods, and Trends](https://arxiv.org/abs/2311.10777).


We share these scripts to facilitate large-scale literature reviews by mining extracted academic publication PDFs and reference files through the following steps:

1. Unzipping and renaming files when necessary
2. PDF keyword searching and counting
3. Keyword- and rule-based auto-screening and analysis

The script run times shown at the bottom of the scripts were calculated based on running on a Windows laptop with the following specifications:

- **Processor**: Intel(R) Core(TM) i7-1165G7 CPU
- **RAM**: 32.0 GB



## Prerequisites

`Input`

A collection of academic publications in the form of PDF files or zip files containing PDFs, and reference files in CSV or BibTeX format.

`Output`

Excel files containing records of all the PDF files, including their key citation information, local file links for easy reading and note-taking. The second output file also contains the automatic screening results and reasons, as well as tables and graphs for screening result analysis.


`Input File Directory Structure`

Before using these scripts, please organise the PDF and reference files (in CSV or BibTeX format) downloaded from digital databases as described below:

* All digital database downloads should be saved under a common main path. 

* Each database export should be placed in its own subdirectory, e.g. "ACM DL", "IEEE Xplore". Inside each database subdirectory:

    * Organise PDFs or zip files into subfolders based on the publication type, e.g. "Journals", "Conferences", "Magazines". 

    * Create a folder named `reffiles` to store all the CSV or BibTeX reference files associated with the exported files from that database.

Below is an example of the overall directory structure:
```
main_directory
├── ACM DL
│   ├── Journals
│   │   ├── result_page_1 (optional sub_sub_directory)
│   │   │   ├── paper_1.pdf
│   │   │   └── ...
│   │   ├── result_page_2
│   │   │   ├── paper_101.pdf
│   │   │   └── ...
│   │   └── ...
│   ├── Conferences
│   │   ├── result_page_1.zip
│   │   ├── result_page_2.zip
│   │   ├── paper_1001.pdf
│   │   └── ...
│   ├── ...
│   │   └── ...
│   └── reffiles
│       ├── journal_refs_result_page_1.csv
│       ├── journal_refs_result_page_2.csv
│       ├── result_page_1.bib
│       └── ...
└── IEEE Xplore
    └── ...
```


## Usage Instructions

1. Ensure your files are organised as described in the [Input File Directory Structure](#input-file-directory-structure) section above.

2. Run the `0-1. (One-off) unzip_and_rename_files` script to prepare your files.

3. Use the `1. pdf_keyword_search` script to create an Excel list of all the PDF files, their citation information, and the count of each keyword identified in each document.

4. Apply the `2. auto_screening` script to categorise and filter the documents based on both rules and keyword counts. This will generate an updated Excel list of all files with auto-inclusion results and reasons, along with inclusion-exclusion statistics presented as tables and graphs.


