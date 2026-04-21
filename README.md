#  NLP Preprocessing Pipeline — Dhurandar Movie Reviews

A complete Natural Language Processing (NLP) preprocessing pipeline applied to the **Dhurandar IMDb Movie Reviews** dataset (~1099 samples).

---

## 📁 Dataset

| Property | Details |
|---|---|
| Source | IMDb Reviews — Dhurandar Movie |
| Total Samples | 1099 |
| Columns Used | `rating`, `review` |
| Dropped Columns | `date`, `helpful_yes`, `helpful_no`, `username`, `title` |

---

## 🛠️ Preprocessing Steps

### 1. 📥 Load Dataset
- Loaded CSV using `pandas`
- Dropped unnecessary columns
- Retained only `rating` and `review`

### 2. 🔡 Lowercase Conversion
- Converted all review text to **lowercase** for uniformity

### 3. ✂️ Tokenization
- **Word Tokenization** using `nltk.word_tokenize()`
- **Sentence Tokenization** using `nltk.sent_tokenize()`
- Added `word_count` and `sentence_count` columns

### 4. 📊 Frequency Distribution
- Used `nltk.probability.FreqDist` to find most common words
- Plotted top 10 frequent words using `matplotlib`

### 5. ❌ Punctuation Removal
- Removed all punctuation characters using `string.punctuation`

### 6. 🌐 HTML Tag Removal
- Removed HTML tags using `regex` pattern `<.*?>`

### 7. 🔗 URL Removal
- Removed URLs matching `https://`, `http://`, and `www.` patterns

### 8. 🚫 Stopword Removal
- Used `nltk.corpus.stopwords` (English)
- Counted stopwords before removal
- Stored cleaned text in `clean_review` column
- Re-tokenized and re-counted words/sentences after removal

### 9. 😊 Emoji Removal & Count
- Counted total emojis per review before removal
- Removed emojis using Unicode range patterns via `regex`

### 10. 🏷️ Part-of-Speech (POS) Tagging
- Applied `nltk.pos_tag()` on word tokens
- Stored POS tags in `pos_tags` column

---

## 📦 Libraries Used

```python
import pandas as pd
import nltk
import string
import re
import matplotlib.pyplot as plt
from nltk import word_tokenize, sent_tokenize
from nltk.corpus import stopwords
from nltk.probability import FreqDist
```

---

## 📊 Final DataFrame Columns

| Column | Description |
|---|---|
| `rating` | IMDb rating given by reviewer |
| `review` | Cleaned review text |
| `word_tokens` | List of word tokens |
| `sentence_tokens` | List of sentence tokens |
| `word_count` | Total word count |
| `sentence_count` | Total sentence count |
| `clean_review` | Review after stopword removal |
| `clean_review_word` | Tokens of clean review |
| `clean_review_sentence` | Sentences of clean review |
| `clean_review_word_count` | Word count after cleaning |
| `clean_review_sentence_count` | Sentence count after cleaning |
| `stopword_count` | Number of stopwords removed |
| `emoji_count` | Number of emojis found |
| `pos_tags` | Part-of-speech tags |

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/your-username/your-repo-name.git
```

2. Install dependencies
```bash
pip install pandas nltk matplotlib autocorrect
```

3. Download NLTK data
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('averaged_perceptron_tagger_eng')
```

4. Run the notebook in **Google Colab** or **Jupyter Notebook**

---

## 👤 Author
