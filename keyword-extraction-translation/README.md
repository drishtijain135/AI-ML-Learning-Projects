# Keyword Extraction and Translation

A Python-based NLP project that performs automatic semantic keyword extraction from text and translates text into a selected language.

## Features

### 1. Automatic Keyword Extraction

- Uses the Sentence Transformers library.
- Loads the `all-MiniLM-L6-v2` pre-trained model.
- Converts input text and predefined keywords into embeddings.
- Calculates cosine similarity between the text and keywords.
- Returns the top 3 most relevant keywords.

### 2. Language Translation

- Uses the `deep-translator` library.
- Translates text into a selected target language.
- Supports language codes such as:
  - `en` - English
  - `hi` - Hindi
  - `ur` - Urdu
  - `ta` - Tamil
  - `pa` - Punjabi

## Technologies Used

- Python
- Jupyter Notebook
- Sentence Transformers
- PyTorch
- NumPy
- Deep Translator

## Project Structure

```text
keyword-extraction-and-translation/
│
├── Keywordextraction.ipynb
├── README.md
└── requirements.txt
