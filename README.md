# Face-Recognition-Meta-Learning
Face recognition using Siamese CNN + Model-Agnostic Meta-Learning (MAML), implemented in TensorFlow and Jupyter, trained on the ORL Faces dataset.
# Face Recognition Using Meta‑Learning (Siamese + MAML)

This repository contains a Jupyter Notebook that trains a **Siamese Neural Network** with **Model‑Agnostic Meta‑Learning (MAML)** for face recognition on a small grayscale face dataset (PGM format).

> **Why meta‑learning?**  
> Meta‑learning helps a model **adapt quickly** to new identities with only a few examples (few‑shot learning), which is practical when you don’t have many labeled images per person.

---

## 📂 Project Contents

- `Face recognition.ipynb` — the complete, runnable notebook (data loading, preprocessing, model, training, evaluation).
- `dataset/` — grayscale face images arranged by subject folder (e.g., `s1`, `s2`, …).
- `readme.md` — (original project notes; superseded by this README).
- `System Requirements.txt` — quick dependency list.

A quick peek at the dataset layout:

```
dataset/
└── orl_faces/
    └── README
```

> Each `sX` folder represents one person and includes multiple `.pgm` images with varying pose/lighting.

---

## 🧰 Requirements

- **Python 3.8+** (3.7+ should work)
- Jupyter (or VS Code with the Jupyter extension)
- Packages in `requirements.txt`

Install everything into a virtual environment:

```bash
# create & activate a virtual env (one option)
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# install deps
pip install -r requirements.txt
```

If you prefer, the minimal set is:
```
numpy
tensorflow>=2.0
matplotlib
Pillow
scikit-learn
```

---

## 🚀 How to Run

1. **Open the notebook**  
   Launch Jupyter and open `Face recognition.ipynb`:
   ```bash
   jupyter notebook
   # or
   jupyter lab
   ```
   In VS Code, just open the notebook and select your Python interpreter (the `.venv`).

2. **Run cells top to bottom**  
   The notebook:
   - Loads images from `dataset/`
   - Preprocesses (resize/normalize)
   - Builds a **Siamese CNN** backbone
   - Trains with **MAML** (inner loop: fast adaptation; outer loop: meta‑update)
   - Evaluates with metrics such as accuracy/precision/recall and a confusion matrix

3. **Adjust hyperparameters (optional)**  
   Look for the training config cell and tweak batch size, inner/outer steps, learning rates, and train/test split.

---

## 📊 Expected Outputs

- Meta‑training loss curves over epochs
- Verification accuracy (pair similarity)
- Confusion matrix / classification report on the test split
- Example predictions/visualizations

> Results will vary by split and hyperparameters; meta‑learning typically delivers **strong few‑shot performance** relative to standard training.

---

## 🗂 Recommended Repo Structure (as uploaded)

```
.
├── Face recognition.ipynb
├── dataset/
├── requirements.txt
├── System Requirements.txt
├── README.md
└── .gitignore
```

---

## 🔒 License & Data

- Code: MIT license (see `LICENSE`).
- Dataset: These `.pgm` faces are commonly derived from educational face datasets.  
  If you distribute publicly, verify the dataset’s license/terms for redistribution.

---

## 🧽 Housekeeping

- Large/temporary files are ignored via `.gitignore` (e.g., `__pycache__/`, `.ipynb_checkpoints/`, virtualenvs).
- Keep raw data small. For very large assets, consider Git LFS or a download link instead of committing binaries.

---

## 🙋 FAQ

**Q: Can I run this without a GPU?**  
A: Yes, but training will be slower. TensorFlow CPU is fine for small experiments.

**Q: Can I add new people with a few photos each?**  
A: That’s exactly what meta‑learning is good at—fine‑tune with a handful of images per new identity.

---

## 🧭 Quick Start to Upload on GitHub (no local Git needed)

1. Create a **new repository** on GitHub.
2. Click **Add file → Upload files**.
3. Drag‑and‑drop: `Face recognition.ipynb`, `dataset/`, `requirements.txt`, `.gitignore`, `README.md`, and `LICENSE`.
4. Add a commit message like “Initial upload” and **Commit changes**.

Happy experimenting! 🎉
