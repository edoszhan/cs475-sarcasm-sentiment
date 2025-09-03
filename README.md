# CS475 Sarcasm & Sentiment Classification

## 📌 Goal
Detect sarcasm and analyze sentiment in short social text.  
We explore both **text-only** and **multimodal (text + image)** setups.

---

## 📂 Data & Labeling
- **`datasets/jokes.csv`**: public jokes corpus (sarcastic = 1 candidates).  
- **University/community comments**: gathered non-sarcastic = 0 candidates (sampled 5k).  
- Combined 5k sarcastic + 5k non-sarcastic = **10k rows total**.  

Processed datasets:
- **`datasets/combined_comment.csv`**: merged 10k rows.  
- **`datasets/cleaned_combined_comment.csv`**: normalized & cleaned text (with team’s labels).  
- **`datasets/original.csv`**: reference sample.  

---

## ⚙️ Methods
Implemented in **[`src/test.ipynb`](src/test.ipynb)** and **[`src/main.ipynb`](src/main.ipynb)**:

- **Text-only baseline**  
  - CountVectorizer + Logistic Regression on cleaned comments.  

- **Sentiment analysis**  
  - VADER sentiment tagging (positive / neutral / negative).  
  - Analyzed distribution vs sarcasm labels.  

- **Multimodal prototype**  
  - Compact text embeddings (BERT tokenizer).  
  - Paired images (when available) processed via simple CNN.  
  - Fused with MLP for joint classification.  

---

## 📊 Results (held-out test sets)

- **Text-only baseline**  
  - Accuracy: ~0.81  
  - Weighted F1: ~0.81  

- **Multimodal prototype** (small paired subset)  
  - Accuracy: ~0.60  
  - Precision: ~0.63  
  - Recall: ~0.60  
  - F1: ~0.59  

- **Sentiment distribution**  
  - Majority labeled **neutral** for both sarcastic & non-sarcastic.  
  - Weak correlation between sentiment polarity and sarcasm.  

---

## 🚀 Next Steps
- Improve multimodal alignment (better image-text fusion).  
- Explore transformer-based sarcasm detection models.  
- Expand dataset with more balanced sarcastic image-text pairs.  
