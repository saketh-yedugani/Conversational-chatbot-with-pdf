# Conversational RAG with PDFs 📄🤖

This project is a **Conversational Retrieval-Augmented Generation (RAG)** application built using **Streamlit**, **LangChain**, **Groq LLMs**, and **ChromaDB**.  
It allows users to upload one or more PDF files and ask questions about their content while maintaining **chat history across multiple turns**.

---

## 🚀 Features

- 📂 Upload and query **multiple PDF files**
- 💬 **Multi turn conversational Q&A** with chat history
- 🧠 History-aware question reformulation
- 🔎 Semantic search using **HuggingFace embeddings**
- ⚡ Fast inference using **Groq (LLaMA 3.1)**
- 🗂 Vector storage with **Chroma**
- 🧩 Session-based memory management

---

## 🏗 Architecture Overview

1. **PDF Upload**
   - PDFs are uploaded via Streamlit and temporarily stored on disk.
   - `PyPDFLoader` extracts text from the PDFs.

2. **Text Chunking & Embeddings**
   - Documents are split using `RecursiveCharacterTextSplitter`.
   - Embeddings are generated using `all-MiniLM-L6-v2`.

3. **Vector Store**
   - Embeddings are stored in **ChromaDB** for similarity search.

4. **History-Aware Retrieval**
   - User questions are reformulated into standalone questions using chat history.
   - Relevant chunks are retrieved from the vector store.

5. **Answer Generation**
   - Retrieved context is passed to the Groq-powered LLM.
   - Responses are concise and grounded in document context.

---

## 🧠 Tech Stack

- **Frontend**: Streamlit  
- **LLM**: Groq (`llama-3.1-8b-instant`)  
- **Framework**: LangChain  
- **Vector DB**: Chroma  
- **Embeddings**: HuggingFace (`all-MiniLM-L6-v2`)  
- **PDF Parsing**: PyPDFLoader  

