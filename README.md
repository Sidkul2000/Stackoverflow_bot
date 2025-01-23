# StackOverflow Assistant Bot

## Project Overview
The **StackOverflow Assistant Bot** is a dialogue chatbot designed to:
- Answer programming-related questions using a StackOverflow dataset.
- Engage in general chit-chat for non-programming questions.

The bot leverages a pre-trained neural network engine from **ChatterBot** for chit-chat functionality.

---

## Data Sources
The project relies on two main datasets:
1. **`tagged_posts.tsv`**: StackOverflow posts tagged with programming languages (positive samples).
2. **`dialogues.tsv`**: Dialogue phrases from movie subtitles (negative samples).

---

## Key Components
The following models and artifacts are generated during the project:
- **`intent_recognizer.pkl`**: A model for recognizing user intent.
- **`tag_classifier.pkl`**: A model for classifying programming languages.
- **`tfidf_vectorizer.pkl`**: A vectorizer used during training for text preprocessing.
- **`thread_embeddings_by_tags/`**: A directory containing thread embeddings, organized by tags.

---

## Project Structure
- **`utils.py`**: Contains reusable functions for the notebook and scripts.
- **`setup_google_colab.py`**: Script for setting up the project in Google Colab.

---

## Functionality

### Part I: Intent and Language Recognition
The bot:
1. **Identifies User Intent**  
   Distinguishes between programming-related questions and general dialogue.
2. **Predicts Programming Language**  
   For programming-related queries, it predicts the relevant language to optimize search speed.

---

### Data Preparation
- Applies **TF-IDF Transformation** for text preprocessing.
- Implements the `tfidf_features()` function to perform the transformation and save the vectorizer.

### Text Classification
The project utilizes two datasets:
1. **Dialogue Data**: A sample of 200,000 entries from `dialogues.tsv`.
2. **StackOverflow Data**: A sample of 200,000 entries from `tagged_posts.tsv`.

---

## Installation and Setup

To set up the project locally:

```bash
# Clone the repository
git clone [repository_url]

# Install dependencies
pip install -r requirements.txt

# Download necessary data files
python download_data.py
```

Usage
Below is a simple example of how to use the bot:

```bash
from stackoverflow_bot import StackOverflowBot

# Initialize the bot
bot = StackOverflowBot()

# Query the bot
response = bot.get_response("How do I use a list comprehension in Python?")
print(response)
```
