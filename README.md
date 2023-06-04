# persistent_homology_of_attention
If you don't have Jupyter Lab/Notebooks already installed and working, go download [Anaconda](https://www.anaconda.com/). When it's finished downloading, open it and open a new instance of Jupyter Lab. Then you can run the [notebook](https://github.com/Amelie-Schreiber/persistent_homology_of_attention/blob/main/persistent_homology_attention.ipynb).

---

![simplicial_complex_2](https://github.com/Amelie-Schreiber/persistent_homology_of_attention/blob/main/simplicial_complex_2.png)

---
## What is Persistent Homology and how can it be used in transformers and NLP?

In the notebook, if two token nodes are connected in a cluster, they are information theoretically related in the text (at the scale defined by the `threshold` slider). To understand this better, keep reading and try running the notebook. 

Persistent homology is a tool from the field of topological data analysis (TDA) that studies the topology of data and aims to extract meaningful features from complex datasets. It can be applied to a wide range of domains, including text analysis and attention mechanisms in transformers.

In the context of text analysis and attention mechanisms in transformers, persistent homology can be used to:

1. Analyze the structure of text: By creating a distance matrix based on the attention distribution of tokens in a given text, we can capture the topological structure of the text. Persistent homology can help identify connected components, loops, or higher-dimensional structures in the text that represent linguistic or semantic properties. This can be useful for understanding how text is organized and revealing hidden patterns in the data.

2. Compare different texts: By computing persistence diagrams for different texts, we can quantify their topological similarity using metrics such as bottleneck distance or Wasserstein distance. This allows us to determine if two texts share similar structures, which could suggest that they are related in terms of topic, style, or content.

3. Investigate attention mechanisms in transformers: Persistent homology can be used to analyze the attention distributions produced by different layers and heads of a transformer model. This can provide insights into how the model processes and represents textual information, as well as help identify potential shortcomings or biases in the attention mechanism.

4. Model interpretability: By visualizing the topological features of a text using persistent homology, we can get a better understanding of how transformer models process and attend to different parts of the text. This can aid in interpreting and explaining the model's predictions and decisions.

5. Model comparison: By comparing the persistent homology features of different transformer models, we can get insights into the differences and similarities between their attention mechanisms. This can be useful for selecting the most appropriate model for a specific task or for improving model architectures.

6. Comparing Languages: Comparing the persistent homology and associated simplicial complexes of different languages may allow us to improve translation models. This can help identify patterns in the alignment of words or phrases, which can provide a better understanding of the translation process and potentially improve the translation model. Comparing the persistent homology features of different translation models can reveal differences in their attention mechanisms and how they align source and target languages. Persistent homology can be used to analyze the topological similarity between different languages or language families.

---

In the context of computational linguistics and deep learning, finding that a subset of tokens, $T = \{t_{i_1}, t_{i_2}, ..., t_{i_k}\}$, forms a persistent topological structure across multiple contexts can provide significant insights into the structure and semantics of language.

Persistent homology, a method in topological data analysis (TDA), can be used to extract and quantify the topological features of data that persist across different scales of analysis. In this case, the data is the high-dimensional space of context vectors produced by a Transformer model like BERT or GPT-2, and the scale of analysis is the level of granularity in the contexts (text corpora) $C_1, C_2, ..., C_n$.

The subset of tokens $T$ forming a persistent topological structure across multiple contexts implies that these tokens consistently have a similar relationship to each other, regardless of the specific context they appear in. This could be interpreted as these tokens forming a stable linguistic unit - in other words, a collocation. The persistence of this structure across different contexts would support this interpretation, as collocations are expected to convey a consistent meaning across different contexts.

Mathematically, we can represent the persistent homology of a context corpus $C_i$ as a filtration of simplicial complexes:

$$ F_{C_i} = \{K_{C_i}^1, K_{C_i}^2, ..., K_{C_i}^m\} $$

where each $K_{C_i}^j$ is a simplicial complex formed by a subset of tokens in $C_i$, and $K_{C_i}^1 \subseteq K_{C_i}^2 \subseteq ... \subseteq K_{C_i}^m$.

The persistent homology captures the topological features that persist across the filtration, which can be represented as a set of persistence pairs $(b,d)$, where $b$ is the birth scale (the scale at which a feature first appears) and $d$ is the death scale (the scale at which a feature disappears). The persistence of a feature is defined as $d - b$.

If $T$ forms a sub-simplicial complex of the filtration of each $C_i$, this could be represented as:

$$ T \subseteq K_{C_i}^j, \forall i,j $$

This would imply that the topological structure formed by $T$ persists across the entire filtration of each context corpus, suggesting that $T$ forms a stable linguistic unit (a collocation).

This finding could have several potential applications:

1. **Collocation Identification**: As discussed, this method could be used to identify collocations in a data-driven and context-aware manner. This could improve the performance of various NLP tasks, such as machine translation, sentiment analysis, and information retrieval.

2. **Semantic Analysis**: This method could be used to analyze the semantic relationships between words. The topological structure could reveal how words are semantically connected to each other, providing insights into the structure of the semantic space.

3. **Model Evaluation**: This method could be used to evaluate the effectiveness of Transformer models in capturing the semantics of language. A model that effectively captures the semantics should produce context vectors that form meaningful and persistent topological structures.

4. **Corpus Analysis**: This method could be used to analyze the structure and semantics of a corpus. The persistent homology could reveal the main themes and topics in the corpus, as well as their interrelationships.

In summary, persistent homology offers a unique perspective for analyzing text and attention mechanisms in transformers. By extracting topological features from attention distributions, we can gain insights into the structure of text and the inner workings of transformer models, potentially leading to improvements in model interpretability and performance.

---

## References and Further Reading
For a good reference on transformers please see:
[Are Transformers universal approximators of sequence-to-sequence functions?](https://arxiv.org/abs/1912.10077)

For a reference on persistent homology and its use to study entanglement, which was inspiration for this work, please see:
[Persistent homology of quantum entanglement](https://arxiv.org/abs/2110.10214)


