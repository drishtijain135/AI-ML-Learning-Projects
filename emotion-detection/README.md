
# Emotion Detection 

A Python-based Natural Language Processing (NLP) project that uses the PySentimiento library to detect emotions in English text and analyze hate speech.

## Features

### 1. Emotion Detection
- Uses the PySentimiento emotion analyzer.
- Detects emotions from English text.
- Returns the predicted emotion.
- Includes a reusable emotion detection function.

### 2. Hate Speech Analysis
- Uses the PySentimiento hate speech analyzer.
- Analyzes text for hate speech.
- Demonstrates hate speech prediction on sample sentences.

## Technologies Used

- Python
- Google Colab / Jupyter Notebook
- PySentimiento
- Natural Language Processing (NLP)
- Machine Learning

## Project Structure

```text
emotion-detection/
│
├── Emotion Detection.ipynb
├── README.md
└── requirements.txt
```

## Installation

Install the required libraries:

```bash
pip install -r requirements.txt
```

Or install PySentimiento directly:

```python
!pip install pysentimiento
```

## How to Run

1. Open `Emotion Detection.ipynb` in Google Colab.
2. Install the required library.
3. Import `create_analyzer` from PySentimiento.
4. Create an emotion analyzer for English.
5. Enter text to predict its emotion.
6. Create a hate speech analyzer.
7. Test sample sentences for hate speech analysis.

## How It Works

### Emotion Detection

The project creates an English emotion analyzer:

```python
from pysentimiento import create_analyzer

emotion = create_analyzer(
    task="emotion",
    lang="en"
)
```

Example:

```python
emotion.predict("wow it was amazing").output
```

The notebook also defines a reusable function:

```python
def emotion_detection(text):
    emotion = create_analyzer(
        task="emotion",
        lang="en"
    )
    result = emotion.predict(text)
    return result.output
```

### Hate Speech Analysis

The project creates a hate speech analyzer:

```python
hate_speech = create_analyzer(
    task="hate_speech",
    lang="en"
)
```

It then predicts hate speech from sample text.

## Example

### Emotion Detection

Input:

```text
wow it was amazing
```

The model predicts the emotion category.

### Hate Speech Detection

Input:

```text
you are the dumbest person i have ever met
```

The model analyzes the text for hate speech.

The exact output depends on the model's prediction.

## Limitations

- The notebook currently focuses on English text.
- The results depend on the pretrained model.
- The notebook demonstrates text analysis using sample inputs.
- Emotion detection and hate speech analysis are separate tasks.

## Future Improvements

- Add a user-friendly interface using Streamlit.
- Support more languages.
- Add batch processing for multiple text inputs.
- Display prediction scores.
- Add visualizations of detected emotions.
- Improve error handling and input validation.

## Author

Drishti Jain

Aspiring Software Developer | AI/ML Enthusiast

## License

This project is available for educational and learning purposes.
