# 🔍 Multi-Source RAG Knowledge Assistant

> 🏆 Developed during a 3-member hackathon. This repository contains my maintained version of the project, preserving the original development history and future improvements.

A Retrieval-Augmented Generation (RAG) system that enables intelligent question answering over multiple document sources including PDFs, CSV files, websites, YouTube videos, and audio files through automated ingestion, semantic retrieval, and LLM-powered responses.

---

# ✨ Features

### 📄 Multi-Source Document Ingestion

Supports processing and indexing of:

- PDF documents
- CSV datasets
- Websites
- YouTube videos
- Audio files (MP3, WAV, M4A)

Each source has a dedicated processing pipeline for extracting and normalizing textual content.

---

### 🧠 Intelligent Retrieval

- Semantic document chunking using LangChain SemanticChunker
- Sentence-Transformer embeddings
- Configurable Top-K retrieval
- Similarity score filtering
- Source attribution for retrieved chunks

---

### 🤖 AI Question Answering

- Together AI integration
- Meta-Llama-3.1-8B-Instruct-Turbo
- Context-aware answer generation
- Confidence-based retrieval workflow

---

### 📚 Collection Management

- Create multiple document collections
- Switch between collections
- Delete collections
- Remove individual documents
- Persistent storage across application restarts

---

### 📑 Rich Document Processing

#### PDF

- Text extraction using pdfplumber
- OCR for scanned PDFs using pytesseract
- Image extraction
- Embedded hyperlink discovery
- Automatic webpage extraction from detected links

#### CSV

- Column summaries
- Data type detection
- Numeric statistics
- Sample previews

#### Websites

- Main content extraction using Trafilatura
- HTML parsing using BeautifulSoup
- One-level internal link crawling

#### YouTube

- Audio extraction using yt-dlp
- FFmpeg conversion
- Speech transcription using Whisper

#### Audio

- Local Whisper transcription
- Automatic preprocessing

---

### ⚡ Additional Features

- Keyword extraction using RAKE + NLTK
- Automatic file monitoring with Watchdog
- Similarity score visualization
- Collection explorer
- Temporary file cleanup
- Interactive Streamlit interface

---

# 🏗 Architecture

```
                   +----------------------+
                   |      Streamlit UI    |
                   +----------+-----------+
                              |
                              |
                    User Upload / Query
                              |
                              v
                +--------------------------+
                | Document Processing Layer|
                +--------------------------+
          PDF | CSV | Website | Audio | YouTube
                              |
                              v
                  Semantic Chunk Generation
                              |
                              v
                  Sentence Transformer Embeddings
                              |
                              v
                  Custom Vector Store (FAISS)
                              |
                              v
                 Retrieval + Similarity Ranking
                              |
                              v
            Together AI (Llama 3.1 Instruct Turbo)
                              |
                              v
                    Generated Response
```

---

# 🛠 Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | Python 3.11 |
| Frontend | Streamlit |
| LLM | Together AI (Meta Llama 3.1 8B Instruct Turbo) |
| Embeddings | Sentence Transformers |
| Vector Search | FAISS |
| Document Processing | pdfplumber, pandas, BeautifulSoup, pytesseract |
| Audio Processing | Whisper, yt-dlp |
| NLP | LangChain, NLTK, RAKE |
| Monitoring | Watchdog |

---

# 📂 Project Structure

```
multi-source-rag-system/

├── app.py
├── utils/
│   ├── document_processor.py
│   ├── rag_engine.py
│   ├── vector_store.py
│   ├── file_monitor.py
│   └── ...
├── data/
├── uploads/
├── temp/
├── requirements.txt
└── README.md
```

---

# 🚀 Installation

```bash
git clone https://github.com/sahil23102/multi-source-rag-system.git

cd multi-source-rag-system

pip install -r requirements.txt
```

---

# ▶ Running

```bash
streamlit run app.py
```

---

# 🔎 Workflow

1. Create a document collection.
2. Upload PDFs, CSVs, websites, YouTube links, or audio files.
3. Documents are processed and indexed.
4. Ask natural language questions.
5. The system retrieves relevant context.
6. Llama 3.1 generates answers grounded in retrieved documents.

---

# 🚧 Future Improvements

- FastAPI backend
- Next.js frontend
- PostgreSQL metadata storage
- Redis caching
- Cross-encoder reranking
- Hybrid keyword + embedding retrieval
- Docker deployment
- Authentication & multi-user support

---

# 📄 License

This repository is intended for educational and portfolio purposes.