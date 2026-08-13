# Sanskrit-English-Retrieval
A multilingual semantic retrieval system for the Bhagavad Gita, designed to retrieve relevant Sanskrit verses from English queries and English explanations from Sanskrit queries. The project focuses on multilingual embeddings, contrastive learning, hard-negative mining, cross-lingual retrieval, transliteration handling, and RAG.

### Objectives
The project evaluates:
- Multilingual embedding models
- Sanskrit-English cross-lingual alignment
- Contrastive learning
- Hard-negative mining
- Semantic retrieval
- Retrieval evaluation
- Evaluate top-k retrieval quality
- RAG-oriented retrieval

### Dataset
The project uses a Bhagavad Gita dataset.
The cleaned dataset contains: 701 verses
Each verse is treated as an individual retrieval document.

### Data Split
- Training:560
- Validation:70
- Test:71

### Data Preparation
The raw dataset was cleaned by:
- Removing missing Sanskrit/English entries
- Removing duplicate verses
- Normalizing whitespace
- Preserving verse and chapter identifiers
- Maintaining Sanskrit-English alignment

##### Positive Pair Creation 
For training, bidirectional cross-lingual positive pairs were created.
##### Hard Negative Mining
nstead of using only random negative examples, semantically similar but incorrect verses were identified

### BASE embedding model
The base embedding model used is: 
`intfloat/multilingual-e5-small`

### Fine-tuned embedding model
The multilingual embedding model is fine-tuned using contrastive learning.

### Retrieval
After fine-tuning, the model is used as a semantic retriever.

### Evaluation
- Recall@K
- MRR
- nDCG

### Base vs Fine-Tuned Evaluation
The final metrics are stored in:
`results/final_results.csv`

### Transliteration Handling
The dataset contains Sanskrit transliteration.
### Chunking Strategy
Each Bhagavad Gita verse is treated as one retrieval unit.
### Embedding Normalization
This allows cosine similarity to be used consistently between queries and documents.
### Failure Analysis
Incorrect retrievals are analyzed to understand where the model fails.
### Mini RAG Demo
The fine-tuned embedding model is used as the retrieval component of a small RAG pipeline.