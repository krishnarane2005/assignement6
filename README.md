# BiLSTM-Attention Machine Translation Assignment

> **Paper:** [Efficient Machine Translation with a BiLSTM-Attention Approach](https://arxiv.org/abs/2410.22335) (arXiv:2410.22335)
> **Task:** Deep Learning Assignment — Attention Mechanism in Seq2Seq Models (20 Marks)

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `BiLSTM_Attention_Assignment.ipynb` | **Main notebook** — all 5 parts with executed outputs |
| `Assignment_Report.md` | Full written report (6–8 page equivalent) |
| `training_log.txt` | Training results log (loss, accuracy, time) |
| `loss_comparison.png` | Training loss curves — With vs Without Attention |
| `attention_matrix.png` | Bahdanau attention heatmap visualization |
| `comparison_bar.png` | Bar chart — Loss / Accuracy / Time comparison |
| `accuracy_by_length.png` | Accuracy vs sentence length analysis |

---

## 📋 Assignment Structure

### Part 1 — Research Paper Review (4 Marks)
- Problem statement, Architecture (BiLSTM Encoder + Attention Decoder)
- Attention type: Bahdanau (Additive) Attention
- Dataset: WMT14 / eng-fra subset
- Key contributions & limitations

### Part 2 — GitHub Code Study & Execution (6 Marks)
- Official repo: [mindspore-lab/models/miniformer](https://github.com/mindspore-lab/models/tree/master/research/arxiv_papers/miniformer)
- PyTorch equivalent implemented and executed
- Training logs & output predictions recorded

### Part 3 — Implementation: With vs Without Attention (6 Marks)
- **Baseline**: BiLSTM Encoder + Vanilla LSTM Decoder (no attention)
- **Attention Model**: BiLSTM Encoder + Bahdanau Attention Decoder
- Comparison table: Loss, Accuracy, Training Time, Output Quality

### Part 4 — Result Analysis & Discussion (3 Marks)
- Attention improves: alignment, context understanding, long-sequence performance
- Limitations without attention: fixed context bottleneck, information loss

### Part 5 — Conclusion (1 Mark)
- Key findings, importance of attention, real-world applicability

---

## 🚀 How to Run

### Option 1 — Jupyter Notebook (Local)
```bash
# Install dependencies
pip install torch matplotlib

# Download dataset (auto-handled in notebook Cell 2)
# Open and run all cells:
jupyter notebook BiLSTM_Attention_Assignment.ipynb
```

### Option 2 — Google Colab
Upload `BiLSTM_Attention_Assignment.ipynb` to [Google Colab](https://colab.research.google.com/) and run all cells.

---

## 📊 Results Summary

| Metric | Without Attention | With Attention |
|--------|-------------------|----------------|
| Final Loss | Higher | **Lower** |
| Accuracy | Lower | **Higher** |
| Output Quality | Degraded on long sentences | **Aligned & complete** |
| Interpretability | None | **Attention heatmap** |

---

## 🏗️ Architecture

```
Source Sentence (French)
        │
   [Embedding Layer]
        │
   [BiLSTM Encoder] ──► h₁, h₂, ..., hₙ
        │                      │
   [Final hidden]        [Attention Layer]
        │                      │
   [LSTM Decoder] ◄──── [Context Vector cₜ]
        │
   [Softmax Output] ──► Translated Token (English)
```

**Attention (Bahdanau-style):**
```
eₜᵢ = Linear([embed_t ; hidden_t])   ← alignment score
αₜ  = softmax(eₜ)                    ← attention weights
cₜ  = Σ αₜᵢ · hᵢ                    ← context vector
```

---

## 📦 Environment

```
Python  >= 3.8
PyTorch >= 2.0
matplotlib
```

---

## 📜 Reference

> *Efficient Machine Translation with a BiLSTM-Attention Approach*, 2024.
> arXiv:2410.22335 — [https://arxiv.org/abs/2410.22335](https://arxiv.org/abs/2410.22335)
> Official code: [mindspore-lab/models](https://github.com/mindspore-lab/models/tree/master/research/arxiv_papers/miniformer)
