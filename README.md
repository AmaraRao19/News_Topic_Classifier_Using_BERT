# News Topic Classifier Using BERT

## Objective
Fine-tune a pre-trained BERT transformer model to classify news headlines into topic categories (World, Sports, Business, Sci/Tech) using the AG News dataset. The model predicts the topic for a given news headline.

---

## Dataset

| Property       | Detail |
|----------------|--------|
| Name           | AG News Dataset |
| Source         | Hugging Face Datasets (`ag_news`) |
| Number of Classes | 4 |
| Classes        | World, Sports, Business, Sci/Tech |
| Number of Training Samples | 120,000|
| Number of Test Samples     | 7,600 |
| Features       | `text` (headline), `label` |

---

## Methodology / Approach

1. Load the AG News dataset from Hugging Face.  
2. Preprocess the text: tokenization using `BertTokenizer`.  
3. Fine-tune pre-trained `bert-base-uncased` model for classification.  
4. Train using Hugging Face `Trainer` API .  
5. Evaluate using **Accuracy** and **Weighted F1-Score**.  
6. Deploy the model using **Gradio** for live interaction.  

---

## Key Design Choices

- Used **BERT (`bert-base-uncased`)** due to strong performance on NLP tasks.  
- Subset of dataset used to **fit GPU memory**.  
- Batch size = 4, 1 epoch, fp16 enabled .  
- Evaluation metrics: **Accuracy & F1-Score (weighted)**.  
- Deployment: **Gradio** for interactive testing.  

---

## Key Results / Observations

| Metric          | Score |
|-----------------|-------|
| Accuracy        | 0.88  |
| F1-Score        | 0.87  |

**Observations:**
- Class distribution is roughly balanced → model performs well.  
- Text length varies across categories (visualized using boxplot).  
- Subset training still gives good performance due to pre-trained knowledge.  

---

## Project Structure
News-Topic-Classifier-BERT/
│
├─ News_Topic_Classifier_Using_BERT.ipynb # Colab notebook with full project
├─ README.md # Project description
├─ requirements.txt # Python packages
├─ plots/ # Optional folder for boxplots, count plots

---

## Setup & Run

1. Clone the repo:
```bash
git clone https://github.com/<your-username>/News-Topic-Classifier-BERT.git
cd News-Topic-Classifier-BERT
