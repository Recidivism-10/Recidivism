# Recidivism Program Ingestion and Evaluation Platform

## 📘 Project Overview

The **Recidivism Validation Platform** is a single Jupyter Notebook-based application that **extracts, analyzes, embeds, and visualizes** Evidence-Based Recidivism Reduction (EBRR) program data from PDFs.  
It integrates **OCR extraction**, **text embedding**, **ChromaDB vector database** management, and a **Streamlit web app** — all within one `.ipynb` file.

This platform supports **FedWriters** and the **Federal Bureau of Prisons (BOP)** in evaluating correctional programs under the **First Step Act**.

---

## ✨ Features

- 📄 **Automated PDF Text Extraction**  
  Uses `pdfplumber`, `PyMuPDF`, and `pytesseract` for OCR and layout-aware parsing.
  
- 🧹 **Text Cleaning and Chunking**  
  Normalizes and segments text for semantic analysis.
  
- 🧠 **Embeddings and Storage**  
  Generates Sentence-Transformer embeddings and stores them in `ChromaDB`.

- 🌐 **Interactive Streamlit App**
  - Upload and process new PDFs
  - Query processed documents using semantic search
  - Visualize document similarities
  - Manage and delete stored files

- ☁️ **Persistent Storage**  
  All models and vector stores persist on **Google Drive**.

- 🚀 **Public Access via Ngrok**  
  Streamlit app is shared securely using Ngrok tunnels.

---

## 🛠 Installation

### Prerequisites
- Ngrok account and **authtoken** for public sharing.
- Ensure the following libraries are installed:

```bash
pip install pdfplumber PyMuPDF pytesseract pdf2image pillow docling camelot chromadb
pip install streamlit==1.44.1 PyPDF2==3.0.1 joblib==1.4.2 numpy==2.0.2 pandas==2.2.2 torch==2.6.0 datasets==3.5.0 pyngrok==7.2.3 fsspec==2024.12.0 gcsfs==2024.12.0 import-ipynb
```

---

## 📂 Project Structure

```text
📓 Final_Recidivism_10.ipynb   # Main Jupyter Notebook
📁 /Colab_Chatbot/             # Google Drive storage
    ├── chroma_db/             # Persistent vector DB
    └── saved_model/           # BERT & SentenceTransformer models
```

---

## ▶️ How to Run

1. **Mount Google Drive in Colab**
   ```python
   from google.colab import drive
   drive.mount('/content/drive', force_remount=True)
   ```

2. **Directory Setup (auto-created if not found)**
   ```text
   /content/drive/MyDrive/Colab_Chatbot/
       ├── chroma_db/
       └── saved_model/
   ```

3. **Install dependencies** using pip.

4. **Upload PDFs** into Google Drive or use the Streamlit app.

5. **Run notebook cells sequentially**:
   - Extract text from PDFs
   - Clean & chunk content
   - Generate embeddings
   - Store embeddings in ChromaDB
   - Launch Streamlit app

6. **Access the Streamlit App**
   After launching, you’ll see:
   ```text
   ✅ Streamlit app is live at: https://<your-ngrok-id>.ngrok-free.app
   ```

---

## 🧪 Functionalities

### 🔍 Chatbot Tab
- Semantic document search
- Summarized answers via T5 model

### 📤 PDF Upload Tab
- Upload PDFs
- Automatic extraction and storage

### 🗂 Manage Files Tab
- Delete or manage stored documents
- Maintain ChromaDB content

---

## 📚 References

- [Federal Bureau of Prisons - EBRR Programs](https://www.bop.gov/inmates/fsa/docs/evidence_based_recidivism_reduction_programs.pdf)  
- [Crime Solutions - Recidivism Programs Database](https://crimesolutions.ojp.gov/topics/Recidivism)  
- [The First Step Act Overview (CRS Report)](https://www.congress.gov/crs-product/R45558)

---

## 🙏 Acknowledgments

- **FedWriters** — Project Sponsor  
- **George Mason University DAEN Program**

---

## 👥 Contributors

| Name                      | Role           | LinkedIn                                                                                             | GitHub                                               |
|---------------------------|----------------|------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Jagadeesh Varma Gadiraju  | Scrum Master   | [Jagadeesh Varma](https://www.linkedin.com/in/gadiraju-jagadeesh-varma-472a34237)                   | [JagadeeshVarma64](https://github.com/JagadeeshVarma64) |
| Vinay Kumar Narava        | Product Owner  | [Vinay Narava](https://www.linkedin.com/in/vinaynarava/)                                             | [vinaykumar-0007](https://github.com/vinaykumar-0007) |
| Raghu Manjumatha          | Developer      | [Raghu Manjumatha](https://www.linkedin.com/in/raghu-manjunatha/)                                    | [RaghuManjunatha](https://github.com/RaghuManjunatha) |
| Saihith Reddy Suram       | Developer      | [Saihith Reddy](https://www.linkedin.com/in/saihith-reddy/)                                          | [SaihithReddySuram](https://github.com/SaihithReddySuram) |
| Srija Anasuri             | Developer      | [Srija Anasuri](http://www.linkedin.com/in/srijaanasuri-)                                            | [SrijaAnasuriGMU](https://github.com/SrijaAnasuriGMU) |
| Gnaneshwar Reddy Vemunuri | Developer      | [Gnaneshwar Reddy](https://www.linkedin.com/in/gnaneshwar-reddy-59465b1b2/)                          | [gnaneshwar151120](https://github.com/gnaneshwar151120) |



---

## ⚠️ Notes

- Ngrok tunnels on the free plan may reset every 2 hours.
- Ensure persistent model/data storage on **Google Drive**.

