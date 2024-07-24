# Image Captioning using K-Nearest Neighbors (KNN)

This project implements an algorithm to perform image captioning using K-Nearest Neighbors (KNN) based on the paper [A Distributed Representation Based Query Expansion Approach for Image Captioning](https://aclanthology.org/P15-2018.pdf). The image and text embeddings are extracted from the [CLIP](https://openai.com/research/clip) model.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Algorithm](#algorithm)
- [Implementation](#implementation)
- [Results](#results)
- [Usage](#usage)
- [References](#references)

## Introduction

Image captioning is a task that involves generating a textual description for a given image. Although Vision Language Models (VLMs) are the current state-of-the-art tools for image captioning, earlier works using KNN have shown surprisingly good performance. This project explores such an approach using KNN for captioning.

## Dataset

The dataset used in this project is the MS COCO 2014 validation set, which contains images and their corresponding captions.

- [MS COCO 2014](https://cocodataset.org/#home) (validation set only)

## Algorithm

1. **Given**: Image embeddings and corresponding caption embeddings (5 per image).
2. **For every image**:
   - Find the `k` nearest images.
   - Compute its query vector as the weighted sum of the captions of the nearest images (`k*5` captions per image).
   - The predicted caption is the caption in the dataset that is closest to the query vector.

## Implementation

The implementation involves the following tasks:

1. **Implement the Algorithm**: Use Faiss for nearest neighbor computation.
2. **Compute BLEU Score**: Evaluate the algorithm using BLEU score.
3. **Experiment with Different Values of `k`**: Record observations for various values of `k`.
4. **Optimize Faiss Index Factory**: Experiment with different options in the Faiss index factory to speed up the computation and record observations.
5. **Qualitative Study**: Visualize five images, their ground truth captions, and the predicted caption.

### Starter Code

The starter code includes the basic structure to get started with the implementation. You can run this notebook on Colab for faster results.

## Results

The results section should include:

- **BLEU Scores**: For various values of `k`.
- **Faiss Index Factory Optimization**: Observations on the speed and performance improvements.
- **Qualitative Study**: Visualizations of images, their ground truth captions, and the predicted captions.

## Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/NithinV-tech/IMAGE-CAPTIONING-KNN.git
   cd IMAGE-CAPTIONING-KNN
