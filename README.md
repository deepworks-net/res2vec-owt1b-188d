---
license: mit
language:
- en
---

# res2vec OpenWebText-1B Word Embeddings

![Model at a Glance](info.jpg)     

| | |
|---|---|
| **Dimensions** | 188 |
| **Vocabulary** | 1,008,133 words |
| **Embedding Size** | 723 MB |
| **Total Size** | ~744 MB |
| **Format** | NumPy (.npy) |

## Model Properties

| Metric | Value |
|--------|-------|
| Information Capacity (I) | 0.106 |
| Average Resonance (R) | 0.071 |
| Optimal Dimension (d*) | 187.6 |
| Fixed Point | ✓ |

## Benchmarks

| Model | Dim | Corpus | SimLex-999 | WordSim-353 |
|-------|-----|--------|------------|-------------|
| word2vec Skip-gram | 300 | Wikipedia 1B | 0.37 | 0.63 |
| GloVe | 300 | Wikipedia+Gigaword 6B | 0.42 | 0.66 |
| **res2vec** | **188** | **OpenWebText 1B** | **0.296** | **0.597** |

## Example Similarities (cosine)

| Pair | Similarity |
|------|------------|
| king – queen | 0.693 |
| man – woman | 0.798 |
| cat – dog | 0.854 |
| good – bad | 0.855 |

## Usage

```python
import numpy as np
import json

# Load embeddings
embeddings = np.load("res2vec_owt1b_188d_embeddings.npy")  # (1008133, 188)

# Load vocabulary
with open("res2vec_owt1b_188d_vocab.json") as f:
    vocab = json.load(f)  # {"word": index, ...}
```

## Files

| File | Description |
|------|-------------|
| `res2vec_owt1b_188d_embeddings.npy` | Embedding matrix, shape `(1008133, 188)`, float32 |
| `res2vec_owt1b_188d_vocab.json` | Word-to-index mapping, `{"word": index, ...}` |
| `res2vec_owt1b_188d_metric.npy` | Learned metric tensor, shape `(188, 188)`, float64 |
| `res2vec_owt1b_188d_results.json` | Training metadata and diagnostics |
| `res2vec_owt1b_188d_evaluation.json` | Benchmark scores and word pair similarities |

This is an initial proof-of-concept/demonstration of the Resonance Theory technique. Will be adding more versions and refining as I go. Please let me know what you think! :-)

## Links
- Huggingface: [https://huggingface.co/deepworks-net/res2vec-owt1b-188d](https://huggingface.co/deepworks-net/res2vec-owt1b-188d)
- Github: [https://github.com/deepworks-net/res2vec-owt1b-188d](https://github.com/deepworks-net/res2vec-owt1b-188d)