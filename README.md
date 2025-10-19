# Build-a-Contextual-RAG-System-with-Hybrid-Search-and-Reranking
A scalable Retrieval-Augmented Generation (RAG) framework integrating hybrid semantic/keyword search, contextual chunking, and state-of-the-art reranking for optimal information retrieval and generation. Easily deployable via Google Colab.

# Table of Contents
Project Overview

Features

Installation

Usage

Workflow Example

Project Structure

Contributing

License

Contact

# Project Overview

This project implements a full-fledged Contextual RAG pipeline leveraging LangChain for document loading, embeddings, indexing, and chain orchestration. Hybrid retrieval combines semantic (vector-based) and keyword (BM25) search using reciprocal rank fusion, followed by reranking via a SOTA cross-encoder model. Fine-grained contextual chunking is performed to maximize relevant retrieval and answers via LLM prompts. Supported document types include JSON, Wikipedia, and PDF research papers.

Key Use Cases:

1. Research assistants and automated literature review

2. QA bots with domain-specific context

3. Multi-source and multi-modal document retrieval and summarization

# Features

1. Hybrid search: Semantic (OpenAI embeddings + Chroma Vector DB) & keyword (BM25) for robust retrieval

2. Contextual chunking: Automated chunk context generation enhances retrieval granularity and relevance

3. Reranking: Top candidates reranked using BAAI/bge-reranker-v2 cross-encoder

4. Rich document support: Handles JSON lines, Wikipedia, PDF research papers

5. Integrated with LLMs: Leverages OpenAI GPT-4 for answer generation (gpt-4o-mini)

6. Colab ready: Fully runnable in Google Colab with sample data and step-by-step workflow

7. Exportable and extendable: Easy to adapt for custom document types and models

# Installation

Run the notebook in Google Colab:

1. Open Build_a_Contextual_RAG_System.ipynb in Google Colab

2. Install required dependencies (automated in notebook):

     !pip install langchain==0.3.4

     !pip install langchain-openai==0.2.3

     !pip install langchain-community==0.3.3

     !pip install jq==1.8.0

     !pip install pymupdf==1.24.12

     !pip install httpx==0.27.2

     !pip install langchain-chroma==0.1.4

     !pip install rankbm25==0.2.2

3. Enter your OpenAI API key when prompted.

# Usage

Input:

JSON lines, PDF files, or Wikipedia-format documents (samples provided)

# Workflow:

1. Document loading & chunking:

     Loads bulk datasets from JSON/PDF (using LangChain loaders)

     Generates contextual chunks, appending chunk-specific context for improved retrieval

2. Embeddings & indexing:

     Chunk embeddings via OpenAI

     Indexed in Chroma Vector DB

     BM25 indexes built for keyword search

3. Hybrid search:

     Combines BM25 and semantic retriever with reciprocal rank fusion

     Retrieves top-k candidates

4. Reranking:

     Applies cross-encoder reranker for optimal candidate ordering

5. Prompted generation (RAG):

     LLM prompt answers strictly from retrieved chunks (no hallucination)

6. QA interface:

     Built-in queries and display functions for easy inspection


# Workflow Example

1. Prepare or upload your dataset as specified in the notebook.

2. Run setup and installation cells.

3. Process documents into contextual chunks using the provided functions.

4. Perform hybrid retrieval and reranking.

5. Run QA directly or modify code for your use-case.

# Contributing

Contributions are welcome!

Please open issues for bugs or suggestions.

To propose new features or improvements, submit a pull request with a clear description.


# Contact

Maintainer: Tapas Mahanand

For support/issues: use the GitHub Issues tab



