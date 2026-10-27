# Amazon Reviews Sentiment Analysis — NLP Embedding Comparison

Natural Language Processing coursework project comparing three text embedding approaches for sentiment classification using the Amazon Fine Food Reviews dataset.

## Embedding methods

- **Keras trainable embedding** — learned during classifier training
- **Word2Vec** — trained on the selected review texts using Gensim
- **GloVe (100d)** — pre-trained GloVe vectors

## Reported results

The supplied `model_results.csv` records:

| Embedding method | Accuracy |
| --- | ---: |
| Keras Embedding | 89.60% |
| Word2Vec | 86.87% |
| GloVe | 85.30% |

These are previously recorded results, not new measurements.

## Repository files

- `Mohamed_Amine_Elorabi_Assessment1.ipynb` — data exploration, preprocessing, training, evaluation and comparison
- `model_results.csv` — saved model accuracy results
- `requirements.txt` — Python package dependencies
- `Read Me.txt` — short file guide
- `.gitignore` — excludes large input data, GloVe files, and local temporary files

## Data and pre-trained embeddings (not included)

The following original files were deliberately excluded because they exceed GitHub's regular file upload limit:

1. **`Reviews.csv`** — Amazon Fine Food Reviews dataset: https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews
2. **`glove.6B.100d.txt`** — download the `glove.6B.zip` archive from Stanford's GloVe project: https://nlp.stanford.edu/projects/glove/ and extract the 100-dimensional file

Place `Reviews.csv` in the notebook's working directory before running data preparation. The existing notebook starts with Google Colab upload and `!unzip Reviews.csv.zip` cells; **skip those first two cells if `Reviews.csv` already exists**. For GloVe, the notebook contains a download/unzip step and expects `glove.6B.100d.txt` in the working directory; you may use that step or place the extracted file yourself.

## Running

Recommended: use Google Colab with the notebook, or a Python environment that supports TensorFlow.

For a local environment, after installing Python and creating/activating a virtual environment:

```bash
python -m pip install -r requirements.txt
jupyter notebook Mohamed_Amine_Elorabi_Assessment1.ipynb
```

Run the cells in order, with the data files available as described above. The notebook contains some Colab-specific commands and shell commands, so local execution may require minor adjustments.

The requirements list package names, not the exact versions used in the original experiments. To document the versions in your own environment, run `python -m pip freeze` and record the relevant entries.

## Method overview

The notebook maps review star scores 1–2 to negative, 3 to neutral and 4–5 to positive, removes neutral reviews, and draws a random sample of 20,000 reviews before training and evaluation. Model training uses TensorFlow/Keras, with Gensim for Word2Vec.

## Academic context

Prepared for a Natural Language Processing coursework assessment. The submitted academic report and original assessment instructions are not included in this public-repository-ready package.
