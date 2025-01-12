# Agentic AI RAG System with Pinecone and Gemini (Local PDFs)

This project implements a Retrieval Augmented Generation (RAG) system that answers questions based on two local PDF documents stored in Google Drive. It uses Pinecone as a vector database for efficient retrieval of relevant information and Gemini (or another LLM) to generate natural language responses.

## Overview

This RAG system operates as follows:

1.  **Data Loading:** Two PDF files are loaded from a designated Google Drive folder using `PyPDFDirectoryLoader`.
2.  **Text Chunking:** The extracted text from both PDFs is divided into smaller chunks to optimize retrieval and manage context for the LLM.
3.  **Embedding Generation:** Sentence embeddings are created for each text chunk using the "sentence-transformers/all-mpnet-base-v2" Hugging Face model.
4.  **Vector Database Storage:** The text chunks and their corresponding embeddings are stored in a Pinecone vector database.
5.  **Retrieval and Question Answering:** When a user asks a question, the system generates an embedding for the query, retrieves the most similar text chunks from Pinecone, and uses Gemini (or an alternative LLM) to generate a natural language answer based on the retrieved context.

## Technologies Used

*   **Pinecone:** Vector database for storing and retrieving embeddings.
*   **Hugging Face Transformers:** For generating sentence embeddings using "sentence-transformers/all-mpnet-base-v2".
*   **Gemini (or alternative LLM):** Large Language Model for generating natural language responses.
*   **Python:** Programming language for implementation.
*   **LangChain (Optional but highly recommended):** For streamlining the RAG pipeline.
*   **PyPDFDirectoryLoader (LangChain):** For loading PDF documents from a directory.
