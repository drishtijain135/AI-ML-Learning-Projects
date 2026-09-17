
# Image Captioning Using CLIP

A Python-based image-text similarity project that uses the CLIP model from Sentence Transformers to find the text description that best matches an image.

## Features

- Loads images using PIL.
- Uses the pre-trained CLIP model `clip-ViT-B-32`.
- Compares images with multiple text descriptions.
- Calculates similarity scores between image and text embeddings.
- Finds the best matching description.
- Displays the image and its matching description.

## Technologies Used

- Python
- Jupyter Notebook
- Sentence Transformers
- CLIP
- PyTorch
- PIL (Pillow)
- NumPy
- Matplotlib

## Project Structure

```text
image-captioning/
│
├── Image Captioning.ipynb
├── README.md
└── requirements.txt
```

## Installation

Install the required libraries:

```bash
pip install -r requirements.txt
```

Or install them directly:

```bash
pip install sentence-transformers torch Pillow matplotlib numpy jupyter
```

## How to Run

1. Open `Image Captioning.ipynb` in Jupyter Notebook or Google Colab.
2. Install the required libraries.
3. Load the CLIP model.
4. Provide the image path.
5. Define a list of text descriptions.
6. Run the image-text similarity comparison.
7. The notebook displays the best matching description and similarity score.

## How It Works

### Step 1: Load the Model

The project uses:

```python
model = SentenceTransformer("clip-ViT-B-32")
```

### Step 2: Load the Image

The image is opened using PIL.

### Step 3: Define Text Descriptions

Example descriptions:

```python
text_description = [
    "Two dogs in the snow",
    "A cat on a table",
    "A picture of london at night",
    "A happy dog playing fetch",
    "A dog sleeping on a couch",
    "Two cats fighting in a garden",
    "An icecream selller on road",
    "Taj mahal view"
]
```

### Step 4: Generate Embeddings

The model converts images and text descriptions into embeddings.

### Step 5: Calculate Similarity

The project calculates similarity scores using the dot product between image and text embeddings.

### Step 6: Find the Best Match

The description with the highest similarity score is selected as the best match.

## Example Output

```text
Best match for the image is Taj mahal view
```

The actual output depends on the image and the text descriptions provided.

## Limitations

- The notebook compares an image against a predefined list of descriptions.
- It does not generate a completely new caption word by word.
- The image paths must be updated for your own computer or Google Colab.
- Similarity scores depend on the model and input descriptions.

## Future Improvements

- Add automatic caption generation.
- Allow users to upload images through a web interface.
- Add more text descriptions.
- Build a Streamlit application.
- Add support for multiple images.
- Improve image-text matching and display similarity scores.

## Author

Drishti Jain

Aspiring Software Developer | AI/ML Enthusiast

## License

This project is available for educational and learning purposes.
