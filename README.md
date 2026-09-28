# AstroPaperRec: Astrophysics Paper Recommendation

AstroPaperRec is a content-based recommendation prototype for discovering astrophysics papers. It uses arXiv metadata and compares two representations of paper titles and abstracts: TF-IDF and Sentence-BERT. Recommendations are ranked by cosine similarity.

## Repository contents

- `main.ipynb` — notebook for data filtering, recommendation, and evaluation.
- `requirements.txt` — Python dependencies.

## Requirements

Python 3.10 or later and an internet connection for downloading the arXiv metadata dataset and the pretrained Sentence-BERT model.

Install the required packages:

```bash
python -m pip install pandas scikit-learn sentence-transformers kagglehub jupyter
```

## Run the notebook

1. Clone or download this repository.
2. Start Jupyter:

   ```bash
   jupyter notebook
   ```

3. Open `main.ipynb` and run the cells in order.

The notebook downloads the arXiv metadata dataset through KaggleHub, filters astrophysics papers, creates TF-IDF and Sentence-BERT representations, and lets you search for a seed paper by title keyword before generating recommendations.

## Runtime note

The notebook processes the full set of valid astrophysics papers. Generating Sentence-BERT embeddings for the complete collection can take a long time and requires substantial memory. The first run also downloads the dataset and pretrained model.

## Evaluation

Category Precision@K is used as a proxy measure: a recommendation counts as relevant if it shares at least one arXiv category with the selected seed paper. Since category overlap does not always indicate topical relevance, the project also inspects recommendation examples qualitatively.
