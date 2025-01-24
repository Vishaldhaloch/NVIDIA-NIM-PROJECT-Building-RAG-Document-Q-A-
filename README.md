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
   2. **Create a Conda Environment:**
    ```bash
   conda create -n nvidia-rag python=3.8 -y
   
3. **Activate the Environment:**
    ```bash
    conda activate nvidia-rag
  
4. **Install Dependencies:**
   Install the required libraries using requirements.txt:
    ```bash 
    pip install -r requirements.txt
   
5. **Set Up Environment Variables:**
   Create a .env file in the project root with the following content:
    ```bash
    NVIDIA_API_KEY=your_nvidia_api_key

  
1. **How to Run**
   Start the task execution by running the following Python script:
     ```bash
     streamlit run app.py
   
2. **Enter Your Query:**
    - In the Streamlit app, type your query (e.g., "What is the 2020 U.S. census data?") in the text box and click the "Document Embedding" button to prepare the document embeddings.

3. **View the Results:**
    - The system will generate an answer based on the documents available in the database, showing related document chunks in the "Document Similarity Search" section.
    - 
**Code Overview**
 **NVIDIA LLM Integration::**
   - The ChatNVIDIA class from Langchain is used to interface with Nvidia's LLM. It processes the user input, integrates the retrieved document chunks, and produces an answer.

**Document Ingestion & Embedding:**
 - The PyPDFDirectoryLoader loads documents, which are then split into chunks using the RecursiveCharacterTextSplitter. These chunks are transformed into 
   embeddings and stored in FAISS for efficient retrieval.

**Q&A Logic:**
 - When a user query is entered, the app triggers the vector_embedding() function to load and embed documents. The relevant documents are then retrieved using the 
   FAISS vector store and passed into the model to generate an answer.

