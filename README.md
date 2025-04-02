# cPCA Experiments: Satellite Image Change Detection & Spam Message Detection

## Overview
This project explores the generalizability of Contrastive Principal Component Analysis (cPCA) beyond its original application in transcriptomics data. We experimented with applying cPCA to:
1. **Detect changes in satellite images** of the same area taken years apart.
2. **Spam message detection**, distinguishing between genuine messages (such as payment/appointment reminders, OTPs, job offers) and spam messages using cPCA with k-means clustering.

We compare cPCA against traditional unsupervised clustering techniques to assess its effectiveness.

## Requirements
- **Python Version:** 3.12
- Install required packages using:
  ```sh
  pip install -r requirements.txt
  ```

## Running the Experiments

### 1. Visualizing cPCA Performance on Synthesized Data
To validate cPCA performance on synthesized data as described in the original paper, run:
```sh
jupyter notebook og_cPCA.ipynb
```

### 2. Exploring Text Clustering Experiment

#### **Required Data**
Ensure the following files are present in the `spam_text_data` directory:
- `real_message.csv`
- `scam_message.csv`
- `test_all.csv`

#### **Execution Steps**
1. **Preprocessing:**
   - Run `preprocessing_text.ipynb` before executing any other scripts.

2. **Running the Clustering Scripts:**
   - Navigate to the `spam_detection_scripts` folder and run the following notebooks:
     - **cPCA_kmeans.ipynb**: Transforms text vectors into a latent space using cPCA, showing clusters for spam and genuine texts. K-means clustering is applied in the latent space.
     - **PCA_kmeans.ipynb**: Similar to `cPCA_kmeans.ipynb`, but uses PCA instead of cPCA for transformation.
     - **kmeans.ipynb**: Applies k-means clustering directly on text vectors without dimensionality reduction.

3. **Performance Comparison:**
   - The comparative analysis of different methods can be viewed in `performance_spam_data.ipynb`.

### 3. Exploring Change Detection in Satellite Images

#### 3.1 cPCA for Change Detection
In this experiment, cPCA is applied to detect changes between "before" and "after" satellite images of the same area taken years apart.

#### 3.2 Required Data
- The "before" and "after" images must be present in the `satellite_image_data` folder.

#### 3.3 Required Data and Execution
- To visualize and analyze the results, execute the script in `satellite_image_change_scripts/cPCA.ipynb`.


## Results & Findings
- Our experiments demonstrate that cPCA can effectively transform and cluster text data, highlighting differences between genuine and spam messages.
- We provide a comparative performance analysis against other unsupervised clustering techniques to assess the efficacy of cPCA.

## Acknowledgments
This project builds upon the principles of cPCA as outlined in the original research paper. We extended its application to new domains and evaluated its generalizability.

