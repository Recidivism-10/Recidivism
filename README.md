# Recidivism Program Ingestion and Evaluation Platform

## Project Overview

The Recidivism Validation Platform is a **single Jupyter Notebook-based application** that extracts, analyzes, embeds, and visualizes Evidence-Based Recidivism Reduction (EBRR) program data from PDFs.  
It integrates **OCR extraction**, **text embedding**, **vector database (ChromaDB)** management, and a **Streamlit web app** — all within one `.ipynb` file.

This platform supports **FedWriters** and the **Federal Bureau of Prisons (BOP)** in evaluating correctional programs under the First Step Act.

---

## Features

- 📄 **Automated PDF Text Extraction**: Using pdfplumber, PyMuPDF, and OCR (pytesseract)
- 🧹 **Text Cleaning and Chunking**: Standardizing and splitting text into analyzable chunks
- 🧠 **Embeddings and Storage**: Generating semantic embeddings with Sentence-Transformers and storing them in ChromaDB
- 🌐 **Interactive Streamlit App**: 
  - Upload and process new PDFs
  - Ask questions about processed documents
  - Visualize document similarity
  - Manage and delete documents
- ☁️ **Persistent Storage**: All embeddings and models are stored on Google Drive
- 🚀 **Public Access**: App is deployed publicly via Ngrok tunnel

---

## Installation

### Prerequisites
- Ngrok account and authtoken for public app sharing
Ensure the following libraries are installed before running the notebook:

```bash
pip install pdfplumber PyMuPDF pytesseract pdf2image pillow docling camelot chromadb
pip install streamlit==1.44.1 PyPDF2==3.0.1 joblib==1.4.2 numpy==2.0.2 pandas==2.2.2 torch==2.6.0 datasets==3.5.0 pyngrok==7.2.3 fsspec==2024.12.0 gcsfs==2024.12.0 import-ipynb
```
## Project Structure
📓 Final_Recidivism_10.ipynb   # Main Jupyter Notebook (complete code)
📁 /Colab_Chatbot/             # Google Drive folder
    ├── chroma_db/             # Persistent ChromaDB vector database
    └── saved_model/           # Pre-trained BERT and SentenceTransformer models
    
## How to Run 
<ol>
  <li>Mount Google Drive in Colab:</li>
   from google.colab import drive
drive.mount('/content/drive', force_remount=True)
</ol>


