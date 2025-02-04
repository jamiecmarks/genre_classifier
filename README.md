# Music Genre Classifier

A simple music genre classifier based off of audio features.
## Main Goal: Accurately classify unseen songs into one of the given genres using the following 
1. PCA
1. KNN 
1. SVM
1. Random Forest
1. Neural Network

#### Sub-Goal: Discover the best method for identifying fusion songs, that is songs that are somewhat in-between two genres by using only non-fusion training data


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
## Biggest takeaways
### Feature Selection

Feature selection can be somewhat ad-hoc, especially when multiple features describe the same underlying concept. For example, 'mfccx_mean' where x varies from 1 to 10. To address this, consider the following approaches:

1. **Correlation Analysis**: Identify and remove highly correlated features to reduce redundancy.
2. **Feature Importance**: Use algorithms like Random Forest or Gradient Boosting to rank feature importance and select the most relevant ones.
3. **Dimensionality Reduction**: Apply techniques like PCA or t-SNE, but be cautious of potential data leakage and ensure proper cross-validation.
4. **Domain Knowledge**: Leverage domain expertise to select features that are known to be significant.

By applying these methods, you can create a more robust and interpretable model.

### PCA can cause unnecessary confusion in understanding what is actually important for a dataset. Especially because it's easy to use data transformed via PCA for both testing and training which is actually a data leak if you do PCA based on all of the data. However, if you don't use all the data PCA can underexaggerate important features of that data. It seems therefore that PCA is most useful for the purpose of visualization.

### In other KNN examples I saw people obtain the optimal K using all the data. This is a large oversight and should be very intentionally avoided as it is a clear data leak which then overexaggerates the test accuracy of these models. A similar data leak also tends to happen in normalization when the scaler is fitted on all of the data instead of just the training data, and it is then used to fit all the data. This is using data that you shouldn't have access to in training.



## Acknowledgements

- [Music genre dataset](https://www.kaggle.com/andradaolteanu/gtzan-dataset-music-genre-classification)
- [Music analysis article](https://towardsdatascience.com/music-genre-classification-with-python-c714d032f0d8)
