# Sanskrit-English-Retrieval
A multilingual semantic retrieval system for Bhagavad Gita verses using a fine-tuned multilingual embedding model.

The system supports:
- Sanskrit → English retrieval
- English → Sanskrit retrieval
- Transliteration → Sanskrit retrieval
- Hard-negative mining
- Contrastive fine-tuning
- Recall@K, MRR and nDCG evaluation
- Mini RAG demonstration

### Setup
1. Clone the repository :
```
git clone https://github.com/Bhavikaa324/Sanskrit-English-Retrieval.git
```
2. Create a virtual environment :
```
python -m venv venv
venv\Scripts\activate
```
3. Dataset :
The project uses the Bhagavad Gita Sanskrit-English dataset from HuggingFace. The cleaned dataset contains 701 aligned verses. Dwonload and load it before running notebook.

`JDhruv14/Bhagavad-Gita_Dataset`

Load it using:
`from datasets import load_dataset`

`dataset = load_dataset("JDhruv14/Bhagavad-Gita_Dataset")`
4. Run the notebook :
`notebooks/sanskrit-english-retrieval.ipynb`

Base model: `intfloat/multilingual-e5-small`
5. Evaluation :
Evaluation is performed for:
- Sanskrit → English
- English → Sanskrit
- Transliteration → Sanskrit
The final results are saved to:`results/final_results.csv`
#### Limitations:
- The dataset contains only 701 verses.
- English translations can vary in wording.
- Transliteration formats may vary.

