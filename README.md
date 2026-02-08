# Research Paper Question Answering System using RAG

This project implements a Retrieval-Augmented Generation (RAG) pipeline to answer
domain-specific research questions using arXiv research papers. Instead of relying
on a language model’s internal knowledge, the system retrieves relevant document
chunks from a vector database and generates grounded answers based on retrieved
evidence.

---

##  Problem Motivation

Traditional LLMs often hallucinate answers when dealing with specialized academic
topics. This project addresses the problem by combining semantic retrieval with
generation, enabling reliable question answering from real research papers.

---

##  System Architecture

User Query  
→ Query Embedding  
→ FAISS Vector Database  
→ Top-K Relevant Chunks  
→ LLM with Context-Aware Prompt  
→ Grounded Answer  

---

##  Dataset

- Source: **arXiv.org**
- Domain: Vehicular Ad Hoc Networks (VANETs), Sybil attack detection, network security
- Format: Research paper PDFs
- Number of papers: ~20

---

##  Tech Stack

- Language: Python
- Environment: Google Colab
- PDF Parsing: PyMuPDF
- Text Chunking: LangChain
- Embeddings: Sentence-Transformers (all-MiniLM-L6-v2)
- Vector Database: FAISS
- LLM: FLAN-T5 (open-source)
- Storage: Google Drive
- Version Control: GitHub

---

## RAG Pipeline Steps

1. Automatically downloaded research papers from arXiv
2. Extracted and cleaned text from PDFs
3. Performed overlapping text chunking
4. Generated semantic embeddings
5. Stored embeddings in FAISS vector database
6. Retrieved relevant chunks for a user query
7. Generated grounded answers using an LLM

---

## Example Query

**Question:**  
What are the limitations of Sybil attack detection in VANETs?

**Answer (Generated):**  
- Lack of centralized authority makes identity verification difficult  
- High node mobility causes frequent topology changes  
- Privacy preservation conflicts with detection mechanisms  
- Infrastructure-free environments limit trust establishment  

---

##  How to Run

1. Open the notebooks in Google Colab  
2. Mount Google Drive  
3. Run notebooks in order:
   - Data ingestion
   - Text processing
   - Vector index creation
   - RAG question answering

---

## Key Contribution

This project demonstrates a complete, reproducible RAG pipeline for academic
question answering using real-world research documents.
