# Comparative Analysis of Gun Violence Coverage Across News Outlets

This repository contains the full pipeline for **NLP Homework 5**, which analyzes how four major U.S. news outlets describe shooters and victims in gun-violence reporting. The workflow includes coreference resolution, descriptive phrase extraction, semantic clustering, manual evaluation, cross-outlet frequency analysis, and chi-square hypothesis testing.

All code is designed to be run in **Google Colab** on a GPU.


## Repository Structure
├── data_100/ # Raw article files (4 outlets × 25 each)
├── task1_coref_contexts.csv # Output from Task 1 (resolved shooter/victim sentences)
├── task2_descriptions.json # Output from Task 2 (LLM-extracted phrases)
├── task3_phrases_with_clusters.csv # Semantic clustering output
├── task5_cluster_frequency.csv # Frequency table
├── task5_cluster_proportions.csv # Proportion table
├── task6_chi_square_results.csv # Statistical test output
├── nlp_hw5.ipynb # Full Colab notebook
└── README.md 

All intermediate results are saved so the pipeline can be resumed at any stage.

## Requirements

This project is intended for **Google Colab**. 
Install all dependencies by running the first code cell in the Colab file. After installation, restart the runtime before running any other cells (Colab will prompt you).

## OpenAI API Configuration
Replace the placeholder text in the notebook:
```python
client = OpenAI(api_key="YOUR_KEY_HERE")
```
with your actual OpenAI API key.

## Data Setup and Running
Upload the repository contents into your Google Drive, then mount Drive in Colab:
```python
from google.colab import drive
drive.mount('/content/drive')
```
Update the directory paths in the notebook so it points to your Google Drive copy of the Github contents. You may run the entire notebook end-to-end, or start from any task as long as the relevant saved results file is available.

## Outputs
All processed datasets and analysis outputs are saved to CSV or JSON files so the workflow can be reproduced, resumed, and inspected without re-running earlier steps. This is especially helpful for steps that involve models or LLM inference.