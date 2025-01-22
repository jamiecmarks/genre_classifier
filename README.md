# Music Genre Classifier

A simple music genre classifier based off of audio features.

## Current stage: Research

## Installation

1. Clone the repository
2. Install the required packages

```bash
pip install -r requirements.txt
```

3. Download the data

```python
import kagglehub

# Download latest version
path = kagglehub.dataset_download("andradaolteanu/gtzan-dataset-music-genre-classification")

print("Path to dataset files:", path)

```

## Acknowledgements

- [Music genre dataset](https://www.kaggle.com/andradaolteanu/gtzan-dataset-music-genre-classification)
