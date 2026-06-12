tags - [[AI]] ,

introduction:
- language models try to learn the probability of words appearing in that order in a sentence.
- we teach language models to predict the next word based on the previous words

### Vocabulary:
   the complete set of words subwords or tokens that a model knows and can understand or generate

### Chain rule of Probability:
For multiple events (\(A_1, A_2, A_3 ..... A_n\)), the generalized formula extends sequentially:
$$P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) \cdot P(A_2 \mid A_1) \cdot P(A_3 \mid A_1 \cap A_2) \cdots P(A_n \mid A_1 \cap A_2 \cap \dots \cap A_{n-1})$$

![[Pasted image 20260612141902.png]]

- LLMS are __autoregressive__ : t 

