---
license: mit
---
Coming Soon...

res2vec OpenWebText-1B Word Embeddings
==================================

Dimensions: 188
Vocabulary: 1,008,133 words

Benchmarks
----------

Model                              Dim   Corpus                    SimLex-999   WordSim-353   
--------------------------         ----  -----------------------  -----------  -----------   
word2vec Skip-gram                 300   Wikipedia 1B              0.37         0.63          
GloVe                              300   Wikipedia+Gigaword 6B     0.42         0.66          
res2vec RT OpenWebText-1B          188   OpenWebText 1B            0.30         0.60          

Example Similarities (cosine)
-----------------------------

               word2vec*   GloVe*    RT (OpenWebText-1B, 188d)
king – queen     ~0.65      ~0.75    0.69
man  – woman     ~0.77      ~0.83    0.80
cat  – dog       ~0.76      ~0.88    0.85
good – bad       ~0.60      ~0.78    0.86

Usage
-----

Python:
    from gensim.models import KeyedVectors
    model = KeyedVectors.load_word2vec_format("res2vec_188d_v1.txt")
    model.most_similar("computer", topn=10)

Download
--------