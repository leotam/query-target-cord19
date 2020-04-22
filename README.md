# A Transformer Query-Target Knowledge Discovery Method

We introduce a straight-forward extension of the "Unsupervised word embeddings capture latent knowledge from materials science literature" using the Roberta transformer-based architecture, enabling many modern benefits including state of the art language modeling performance (full-text processing), negation handling, and flexible relationship analysis. 

The insight of the "latent knowledge" paper was to realize the power of domain specific analogies and the ability of the word2vec algorithm to capture these relationships to some degree. Yet there are challenges to adapting this method to modern transformer architectures. First, what is the task that best maps to the skip-gram approach to mine analogies? How should the algorithm adapt from the straight-forward single hidden layer method in word2vec to the deep encoder decoder architectures used in modern language models? Namely, how are methods to adapt to the new pretrain-finetune paradigm? 

We make first strides in answering these questions in light of the practical application of FDA approval of influenza drugs over the past 50 years, pulling data from clinicaltrials.gov and the excellent review article "Approved Antiviral Drugs over the Past 50 Years", which itself appears in the CORD-19 dataset.

## How to cite
Pending the Arxiv submission, please cite:

```@inproceedings{Transformer Query-Target Knowledge Discovery,
    author = {Tam, Leo K., Wang, Xiaosong, Xu, Daguang},
    title = {Transformer Query-Target Knowledge Discovery (TEND): Drug Discovery from CORD-19},
    year = {2020},
    month = {March-April},
    location = {NVIDIA, Santa Clara, CA, USA}, 
    note={DLMed Research Group},
    howpublished = {\url{https://github.com/leotam/query-target-cord19}}
}
```

Note: We've hardlinked the outputs in the notebook below pending release of the model.

## Methods
We train a Roberta-large model to high accuracy on CORD-19 (pplx=2.47) use prediction scores on a query filtered by the target tokens to score relevance.  Using 'efficacy' as a target, prediction scores are demonstrated on a forward chaining analysis, analyzing historical clincial drug trials for influenza and when the drugs were approved. The ranking of drugs that were historically approved are in the Top 3 prior to approval, though the dataset is limited (influenza is reflective of the dataset but perhaps the dataset does not reflect the broader antiviral landscape). Subsequently, we issue predictions on ongoing clinical trials for COVID-19, as well as  predictions on novel drug combinations.

## Perspectives
We discuss several details on the experimental method and a few caveat emptor points, pending further experiments and peer review on this work in progress. 

Special thanks to Greg Peterfreund, MD and Jason Su for helpful comments.
