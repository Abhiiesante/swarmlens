# LangGraph-style RAG Q&A Agent (Gemini-only)

This workspace contains a compact Jupyter notebook demonstrating a small RAG pipeline with a 4-node workflow: `plan` -> `retrieve` -> `answer` -> `reflect`.

Files added:
- `notebooks/langgraph_gemini_rag.ipynb` — main demo notebook (Jupyter).\n- `data/renewable_energy_overview.txt` and `data/solar_wind_benefits.txt` — small sample documents prepopulated for quick testing.\n- `requirements.txt` — suggested packages to install.

Quick setup
1. Create & activate a Python virtual environment (recommended). Example (PowerShell):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install requirements:

```powershell
pip install -r requirements.txt
```

3. Configure Gemini credentials:
- Option A (API key): set environment variable `GEMINI_API_KEY`.
- Option B (service account): set `GOOGLE_APPLICATION_CREDENTIALS` to the path of your service account JSON.

4. Launch Jupyter and open the notebook:

```powershell
jupyter lab  # or jupyter notebook
```

Notes & caveats
- The `google.generativeai` client API surface may change; if `genai.generate` fails, consult the package documentation and adapt the `answer_node` call accordingly.
- The notebook uses HuggingFace `sentence-transformers/all-MiniLM-L6-v2` via LangChain's `HuggingFaceEmbeddings`. This runs locally and may download the model on first use.
- ChromaDB is configured to persist in `./chroma_db`.

Optional: Kaggle datasets
- If you want to populate `./data/` using Kaggle, configure the Kaggle CLI and use the Kaggle API to download a dataset into `./data/`. The notebook can be extended to call a Kaggle helper function.

Walkthrough readiness
If selected for a code walkthrough, I'm ready to go line-by-line through the notebook. If you'd like, I can also add a small Streamlit or Gradio UI and a simple evaluation cell (BLEU/ROUGE/BERTScore) as a follow-up.
