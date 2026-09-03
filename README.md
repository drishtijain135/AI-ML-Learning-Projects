# Semantic FAQ Chatbot 🤖

A simple **semantic search-based chatbot** built with **Python, Pandas, and Sentence Transformers**.

Instead of matching the user's question using exact keywords, the chatbot converts the user's query and FAQ questions into **numerical embeddings** and finds the FAQ question with the closest semantic meaning.

##  How It Works

```text
User Query
    ↓
Sentence Transformer
    ↓
Query Embedding
    ↓
Compare with FAQ Embeddings
    ↓
Find Most Similar FAQ
    ↓
Retrieve Corresponding Answer
```

##  Technologies Used

- Python
- Pandas
- Sentence Transformers
- Semantic Search
- Cosine Similarity
- Jupyter Notebook / Google Colab

##  Installation

Install the required library:

```python
%pip install sentence-transformers
```

Import the required libraries:

```python
import pandas as pd
from sentence_transformers import SentenceTransformer, util
```

## Loading the Model

The project uses the pre-trained multilingual Sentence Transformer model:

```python
model = SentenceTransformer("distiluse-base-multilingual-cased-v1")
```

This model converts sentences into **embeddings (vectors)** that represent their semantic meaning.

For example:

```python
a = model.encode("I am not feeling well")
b = model.encode("I am not feeling good")
```

The two sentences have different words but similar meanings, so their embeddings should have a relatively high semantic similarity.

Similarity can be calculated using:

```python
util.cos_sim(a, b)
```

## FAQ Dataset

A sample FAQ dataset is created using a Python dictionary containing:

- `question`
- `answer`

It is then converted into a Pandas DataFrame:

```python
df = pd.DataFrame(faq_data)
```

Example:

| Question | Answer |
|---|---|
| What is machine learning? | Machine learning is a field of AI that uses statistical techniques to give computers the ability to learn. |
| How to reduce stress? | Reducing stress can involve mindfulness, exercise, and adequate rest. |
| How to improve mental health? | Mental health can be improved through therapy, exercise, and social support. |

##  Semantic Search

The user's query is converted into an embedding:

```python
user = model.encode(input("Your query:"))
```

All FAQ questions are converted into embeddings:

```python
faq = model.encode(df["question"].tolist())
```

The most semantically similar FAQ is then found:

```python
id = util.semantic_search(
    user,
    faq,
    top_k=1
)[0][0]["corpus_id"]
```

### What does `top_k=1` mean?

It asks the semantic search function to return only the **best matching FAQ**.

The returned `corpus_id` represents the index of the FAQ question that matched the user's query most closely.

The corresponding answer is retrieved using:

```python
df["answer"][id]
```

##  Chatbot Function

The final chatbot continuously accepts questions until the user types `exit` or `quit`.

```python
def chatbot():
    print("Chatbot : Hello!! Ask a question or type exit to quit")

    while True:
        user_query = input("You : ")

        if user_query.lower() in ["exit", "quit"]:
            print("Chatbot : Goodbye!!")
            break

        query_emb = model.encode(user_query)

        closest = util.semantic_search(
            query_emb,
            faq,
            top_k=1
        )

        best_match_id = closest[0][0]["corpus_id"]
        best_answer = df.iloc[best_match_id]["answer"]

        print(f"Chatbot :{best_answer}")
```

Run it with:

```python
chatbot()
```

## example

**Input:**

```text
You : how to improve mental health
```

**Output:**

```text
Chatbot : Mental health can be improved through therapy, exercise, and social support.
```

The chatbot does not need the user's wording to exactly match the FAQ question. It searches based on **semantic meaning**.

## Key Concepts Learned

### 1. Embeddings

Embeddings represent text as numerical vectors.

```text
Text → Embedding Vector
```

### 2. Semantic Similarity

Semantic similarity measures how close two pieces of text are in meaning.

### 3. Semantic Search

Instead of searching for exact words, semantic search finds content with a similar meaning.

### 4. `corpus_id`

`corpus_id` identifies which FAQ entry was the best match.

### 5. `top_k`

`top_k=1` returns the single best matching result.

##  Possible Improvements

This is a basic semantic FAQ chatbot. It can be extended by:

- Using a larger real-world FAQ dataset
- Returning the top 3–5 results instead of only one
- Adding a similarity-score threshold
- Returning a fallback response when no FAQ is sufficiently similar
- Building a web interface using Flask or Streamlit
- Adding conversation history
- Using a vector database for larger datasets
- Extending the system into a **RAG (Retrieval-Augmented Generation)** application

##  Project Structure

```text
semantic-chatbot/
│
├── chatbot.ipynb
└── README.md
```

## 👩‍💻 Created By

**Drishti Jain**
