# HTSI – Hallucination Tracking System for AI Answers

This project is built to detect hallucinations in AI-generated responses by comparing them with trusted reference documents. It leverages semantic similarity using Sentence Transformers and FAISS vector indexing to verify whether an AI-generated answer is grounded in known content.

## 🔍 Problem Statement

Large Language Models (LLMs) can generate fluent but factually incorrect content—known as "hallucinations." This system aims to verify if an AI response is based on prior trusted information or if it likely deviates from known facts.

## 🚀 Features

- 📄 Extracts text from trusted PDF documents
- ✂️ Splits text into context-rich ~100-word chunks
- 🤖 Encodes chunks using `all-MiniLM-L6-v2` from Sentence Transformers
- 📦 Indexes chunks with FAISS for fast similarity search
- ⚠️ Detects hallucinations based on similarity threshold
- ✅ Saves and loads embeddings for persistent usage

## 🧠 How It Works

1. **Add Trusted PDFs**  
   The system extracts and chunks text from PDF files, converts them to embeddings, and builds a FAISS index.

2. **Test AI Answer**  
   The user inputs an AI-generated answer. The system checks its similarity against the trusted knowledge base.

3. **Decision**  
   If the similarity score is below a set threshold, the system flags the answer as a potential hallucination.

## 🧰 Tech Stack

- **Python**
- **Sentence Transformers (`all-MiniLM-L6-v2`)**
- **FAISS (Facebook AI Similarity Search)**
- **Torch**
- **pdfplumber**
- **Regex for chunking**

## 📁 Files

- `trusted_embeddings.pt` – Stores the embeddings of trusted chunks
- `trusted_chunks.pt` – Stores the corresponding text chunks
- `main.py` – Main logic for chunking, indexing, and hallucination detection

## 📦 Setup Instructions

```bash
pip install sentence-transformers faiss-cpu pdfplumber torch
📈 Applications
This system can be useful in:

Auditing AI-generated content

Building LLM-based assistants with citation verification

Educational tools that ensure factual correctness

Internal company tools to flag unsupported AI responses
