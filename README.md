# ADSP-32027 — Gen AI Midterm Project

A reproducible notebook showcasing a small GenAI / RAG-style pipeline with clear defaults, evaluation, and run instructions.  
Repository: https://github.com/klxd2000/ADSP-32027-Gen-AI-Midterm-Project

## 🔗 Online
- 📓 Full notebook: [`GenAI_Midterm.ipynb`](./GenAI_Midterm.ipynb)
- 🧹 Clean preview (for GitHub rendering): [`GenAI_Midterm_clean.ipynb`](./GenAI_Midterm_clean.ipynb)
- ▶️ Open in Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/klxd2000/ADSP-32027-Gen-AI-Midterm-Project/blob/main/GenAI_Midterm.ipynb)
- 🌐 (Optional) GitHub Pages snapshot: will be available at `https://klxd2000.github.io/ADSP-32027-Gen-AI-Midterm-Project/` once Pages is enabled (see “Export HTML & Pages”).

## 📌 Summary
- **Goal:** demonstrate a compact retrieval + generation setup with sensible defaults and transparent evaluation.
- **Approach:** embeddings + vector search (e.g., FAISS) + structured prompting; keep a single “config cell” to drive the pipeline.
- **Outcome:** a restartable, top‑down notebook that reports retrieval metrics (e.g., Precision@k / Recall@k) and shows example answers.

## 🗂 Repository Structure
```
.
├─ GenAI_Midterm.ipynb          # main notebook (full, executable)
├─ GenAI_Midterm_clean.ipynb    # cleaned preview without widget metadata (for GitHub rendering)
├─ GenAI_Midterm.py             # optional: script version converted from the notebook
├─ docs/
│  └─ post.html                 # optional: exported HTML snapshot for GitHub Pages
└─ assets/                      # optional figures/screenshots
```

## 🚀 Quick Start
```bash
# Python 3.10+ recommended
git clone https://github.com/klxd2000/ADSP-32027-Gen-AI-Midterm-Project.git
cd ADSP-32027-Gen-AI-Midterm-Project
pip install -r requirements.txt  # or install the packages listed below
jupyter lab  # or: jupyter notebook
```
Open `GenAI_Midterm.ipynb` and **Run All** from top to bottom.

## 🧩 Environment
Typical packages used:
- `numpy`, `pandas`, `scikit-learn`, `matplotlib`
- (Optional depending on your code) `torch`, `transformers`, `faiss-cpu`, `ipywidgets`

> If you don’t maintain a `requirements.txt`, you can start with:
> ```bash
> pip install numpy pandas scikit-learn matplotlib
> ```
> and add others as the notebook requests.

## ⚙️ Configuration
At the top of the notebook, define a simple **config cell** with reproducible defaults:
```python
DATA_PATH = "path/to/data"               # adjust as needed
MODEL_NAME = "BAAI/bge-small-en-v1.5"    # example embedding model
TOP_K = 5
SEED = 42
```
Downstream code should reference these variables rather than hidden widget state.

## 🧪 Evaluation
- **Metrics:** report retrieval metrics such as **Precision@k** and **Recall@k** (and optional MRR/NDCG/ARHR if relevant).
- **How to interpret:** briefly explain each metric and what “good” looks like.
- **Results:** include a small table/plot; you can place images under `assets/` and reference them here.

## 🔁 Reproducibility
- Fix random seeds (NumPy/Torch).
- Provide data prep steps or a small sample dataset if applicable.
- Verify the notebook runs from a fresh kernel via **Restart & Run All** (no manual state required).

## ❓ FAQ
- **GitHub preview shows a widget error.** Use `GenAI_Midterm_clean.ipynb` (no widget metadata) or publish an HTML snapshot.
- **Colab widgets do not display.** Try `pip install -q ipywidgets==8` and enable the custom widget manager where needed.

## 📦 Export HTML & Pages (Optional)
Create a static “blog-like” snapshot and host it with GitHub Pages:
```bash
pip install jupyter nbconvert
jupyter nbconvert --to html GenAI_Midterm.ipynb --output docs/post.html
```
Then open **Settings → Pages**:
- **Source:** *Deploy from a branch*
- **Branch:** `main`, **Folder:** `/docs`

After publishing, visit: `https://klxd2000.github.io/ADSP-32027-Gen-AI-Midterm-Project/`

## 🙏 Acknowledgements
List datasets, libraries, and references you used or were inspired by.

## 📜 License
MIT
