# Text Summarizer

A web-based text summarization application built with Flask that provides two different summarization techniques: **Extractive** and **Abstractive** summarization.

![Text Summarizer Application](<img width="425" height="416" alt="screenshot" src="https://github.com/user-attachments/assets/d5cff562-478f-44b0-82a1-09dd3522058a" />)


## Description

Text Summarizer is a Python web application that allows users to input text and generate concise summaries using two different approaches. This project serves as a great learning resource for those interested in natural language processing and practical model integration.

### Features

- **Extractive Summarization**: Uses Natural Language Processing (NLTK) to identify and extract the most important sentences from the original text based on word frequency scoring. This method preserves the original wording from the text.

- **Abstractive Summarization**: Leverages a pre-trained BART (Bidirectional and Auto-Regressive Transformers) model (`lidiya/bart-large-xsum-samsum`) to generate summaries that may contain new phrases and sentences not present in the original text, providing a more natural summary.

### How It Works

1. **Input Text**: Users can paste or type any text they want to summarize in the input text area.
2. **Choose Summarization Type**: Select between "Extractive Summary" or "Abstractive Summary" by clicking the respective button.
3. **Output**: The summarized text appears in the output text area below.

### Extractive Summarization Process

The extractive method:
- Preprocesses the text (lowercasing, removing URLs, emails, contractions, stopwords)
- Calculates word frequencies and normalizes them
- Scores sentences based on word importance
- Selects the top 10% of sentences with the highest scores
- Combines them to form the summary

### Abstractive Summarization Process

The abstractive method:
- Uses a transformer-based model (BART) trained on summarization tasks
- Generates new sentences that capture the essence of the original text
- Produces more fluent and natural-sounding summaries

## Technology Stack

- **Backend**: Flask (Python web framework)
- **NLP Libraries**: 
  - NLTK (Natural Language Toolkit) for text processing
  - Transformers (Hugging Face) for abstractive summarization
- **Frontend**: HTML, CSS with Google Fonts (Playfair Display)
- **Data Processing**: Pandas

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Kunj3690/Text-Summarizer.git
cd Text-Summarizer/Summarizer/Summarizer
```

2. Install required dependencies:
```bash
pip install flask pandas nltk transformers torch
```

3. Download NLTK data (the application will download these automatically, but you can also download manually):
```python
import nltk
nltk.download('stopwords')
nltk.download('punkt')
```

## Usage

1. Run the Flask application:
```bash
python app.py
```

2. Open your web browser and navigate to:
```
http://localhost:5000
```

3. Enter your text in the "Input Text" area
4. Click either "Extractive Summary" or "Abstractive Summary" button
5. View the summarized text in the "Output Text" area

## Requirements

- Python 3.7+
- Flask
- pandas
- nltk
- transformers
- torch (PyTorch)

## Project Structure

```
Summarizer/
├── app.py              # Main Flask application
├── templates/
│   └── index.html     # Frontend HTML template
└── README.md          # This file
```

## Notes

- The abstractive summarization model will be downloaded automatically on first use (requires internet connection)
- The model may take some time to load initially
- Extractive summarization is faster but may produce less fluent summaries
- Abstractive summarization produces more natural summaries but requires more computational resources

## License

This project is open source and available for educational purposes.

