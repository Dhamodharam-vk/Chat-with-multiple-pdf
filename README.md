# 🩺 Medical Chatbot: Retrieval Augmented Generation (RAG)

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Framework-Streamlit-red)](https://streamlit.io/)
[![Orchestration](https://img.shields.io/badge/RAG-LangChain-darkgreen)](https://www.langchain.com/)
[![VectorDB](https://img.shields.io/badge/VectorDB-FAISS-purple)](https://github.com/facebookresearch/faiss)

---

## 🌟 Project Goal

This project implements an intelligent **Retrieval Augmented Generation (RAG)** system designed to assist medical professionals. It enables doctors to quickly and accurately analyze proprietary patient data (uploaded via PDF files) by grounding a Large Language Model (LLM) in specific, relevant medical records.

## ✨ Core RAG Architecture

The RAG workflow ensures that the LLM generates reliable diagnoses and suggestions based solely on the private knowledge base:

1.  **Ingestion:** Patient records (PDFs) are processed, embedded, and stored as searchable vectors in the **FAISS** database.
2.  **Query & Retrieval:** The doctor's natural language query is used to retrieve the most semantically relevant data chunks from the vector store.
3.  **Generation:** The retrieved context is combined with the original query and sent to the LLM (URI AI) to produce a factual, grounded response.

## 🛠️ Technology Stack

| Component | Library/Tool | Role |
| :--- | :--- | :--- |
| **User Interface** | `streamlit` | Creates the interactive, easy-to-use chat and file upload interface. |
| **RAG/Orchestration** | `langchain` | Manages the full pipeline (document loading, indexing, and retrieval). |
| **Vector Store** | `FAISS` | Provides fast, in-memory indexing and searching of vector embeddings. |
| **PDF Processing** | `PyPDF` | Extracts text content from PDF patient records. |
| **Language Model** | `URI AI` | Generates the final, context-aware medical analysis and responses. |

## 🚀 Future Enhancements

We are planning the following updates to enhance the application's performance and scalability:

* **Cloud Integration:** Support for document storage via AWS S3, Azure Blobs, and Google Drive.
* **Performance Optimization:** Implementation of dedicated memory and caching layers.
* **Multimodality:** Adding speech-to-text input and integration with messaging services (e.g., WhatsApp, Email).
* **Enterprise Deployment:** Containerization and deployment on cloud platforms (e.g., AWS, GCP) for production use.

---

## 💻 Getting Started

### Prerequisites

* Python 3.8+
* An API Key for the URI AI service.

### Installation and Run

1.  **Clone the repository:**
    ```bash
    git clone [YOUR_REPOSITORY_LINK_HERE]
    cd medical-chatbot-rag
    ```

2.  **Create a virtual environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use: .\venv\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: You will need to create a `requirements.txt` listing all the libraries above.)*

4.  **Set Environment Variables:**
    Set your URI AI API key in your environment:
    ```bash
    export URI_AI_API_KEY="YOUR_SECRET_API_KEY"
    ```

5.  **Run the application:**
    ```bash
    streamlit run app.py
    ```
---
