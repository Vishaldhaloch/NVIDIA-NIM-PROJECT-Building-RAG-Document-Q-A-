# Nvidia-NIM
# RAG Document Q&A with Nvidia NIM and Langchain

This project demonstrates how to build a **Retrieval-Augmented Generation (RAG) Document Q&A system** using **Nvidia NIM** (NVIDIA's large language model) and **Langchain**. The system ingests document data, creates vector embeddings, and utilizes Nvidia's model for answering user queries based on those documents.

---

## Project Structure

1. **app.py**  
   This is the main Streamlit app that allows users to input their queries, triggers document embedding, and provides Q&A responses.

2. **NVIDIAEmbeddings & ChatNVIDIA**  
   The custom classes for embeddings and chat completions using Nvidia's NIM models (meta/llama3-70b-instruct).

3. **Data Loading & Preprocessing:**  
   Utilizes `PyPDFDirectoryLoader` to load document data and processes it into chunks for efficient querying and retrieval.

4. **Prompt Templates:**  
   The Chat Prompt Templates are configured for Q&A purposes, ensuring that the model answers based on the context provided in the document chunks.

---

## Features

- **NVIDIA LLM Integration:**  
   The system leverages Nvidia's large language model (`meta/llama3-70b-instruct`) to perform high-quality inference for document-based Q&A.

- **Document Embedding with FAISS:**  
   Documents are embedded into vector representations using Nvidia embeddings, which are stored in a **FAISS** vector store for fast retrieval.

- **Retrieval-Augmented Generation (RAG):**  
   The system retrieves relevant documents based on the query and combines them with the language model to generate precise answers.

- **Streamlit Interface:**  
   A user-friendly interface that allows users to interact with the system, provide queries, and view the responses in real-time.

---

## Installation and Setup

### Prerequisites

1. **Python 3.7 or higher**  
   Ensure you have Python 3.7+ installed.

2. **Anaconda or Miniconda Installed:**  
   You should have either Anaconda or Miniconda installed. You can download it from [here](https://www.anaconda.com/products/individual).

3. **NVIDIA API Key:**  
   You will need an API key for **NVIDIA NIM** to access the LLM services. You can generate one from [NVIDIA](https://developer.nvidia.com/).

### Setting Up the Environment

1. **Clone the Repository:**
   ```bash
   git clone <repository_url>
   cd <repository_folder>
