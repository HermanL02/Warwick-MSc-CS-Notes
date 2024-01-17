Generalization
P(l, am, fine) -> high
Bigrams
Training set -> Test set
## Smoothing
Improve the distribution by share the possibility to the other words. 
### Laplace Smoothing
- Add one Estimation
- Normalize them
- We need to decide K Estimation to avoid distribute too much on the 0s. 
### Interpolation and backoff
- Backoff: How to decide bigram, trigram, unigram, and ...
- Linear Interpolation
- Lambdas - context dependent (Do not need to know how, but know we can make it context dependent)
- How to set Lambdas? 
### Turning Smoothing
### Kneser-Ney Smoothing
