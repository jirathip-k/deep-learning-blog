---
title: "Language Model"
date: 2023-10-24T15:30:56+11:00
draft: false
---

# Introduction

## Tokenisation

## Text Representation (Word Embeddings)

### Word2Vec

- **Skip-gram**: Target word predict context words

  - Output layer is computionally expensive due to softmax is a summation over all words in dictionary
  - Depends on the context window size

- **Continuous Bag of Words (CBOW)**: Context words predict target word
