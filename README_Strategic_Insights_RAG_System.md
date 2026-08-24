# Strategic Insights RAG System
A Retrieval‑Augmented Generation (RAG) application designed to help business analysts extract key insights from lengthy business reports—without manually reading the entire document.

## **1. Project Overview**
Business analysts often deal with dense, information‑heavy reports that require hours of manual review. This project demonstrates how a RAG‑based AI assistant can streamline that workflow by enabling analysts to ask natural‑language questions and instantly retrieve relevant, document‑grounded answers.

The system uses:

- Semantic search

- Vector embeddings

- Chunked document retrieval

- LLM‑based answer generation

to deliver accurate, context‑aware insights from long‑form business documents.

## **2. Business Problem & Motivation**
Organizations like venture capital firms, consulting companies, and strategy teams frequently rely on extensive reports to make high‑impact decisions. Manually reviewing these documents is slow, error‑prone, and resource‑intensive.

For example, analyzing Harvard Business Review’s “How Apple Is Organized for Innovation” requires navigating 11 pages of dense content. A RAG system allows analysts to ask questions such as:

- “How does Apple structure its teams for innovation?”

- “What leadership principles does Apple follow?”

- “What organizational changes did Tim Cook introduce?”

and receive precise answers grounded in the source document.

This improves:

- Decision‑making speed

- Research efficiency

- Analyst productivity

- Information accuracy

## **3. Solution Summary**
This project implements a RAG pipeline that:

- Loads the PDF using PyMuPDF

- Splits text into overlapping chunks using token‑based splitting

- Generates embeddings using OpenAI models

- Stores embeddings in ChromaDB

- Retrieves relevant chunks based on user queries

- Generates answers using GPT‑4o‑mini with retrieved context

The notebook includes:

- Baseline LLM responses

- Prompt‑engineered responses

- RAG‑powered responses

- Observations comparing all three approaches

## **4. Architecture Diagram**
Here is the conceptual workflow:

Code
Indexing Phase (offline / once per document)
--------------------------------------------
PDF Document → Text Extraction → Chunking → Embeddings → Vector Store (Chroma)


Query Phase (online / per question)
-----------------------------------
User Query → Query Embedding → Similarity Search in Vector Store (Chroma)
           → Top-k Relevant Chunks → LLM (GPT-4o-mini) with Context → Final Answer

If you want, I can generate a polished PNG diagram for your repo.

## **5. Tech Stack**
- Python

- Jupyter Notebook

- LangChain

- LangChain‑Community

- LangChain‑Core

- LangChain‑OpenAI

- ChromaDB

- PyMuPDF

- OpenAI GPT‑4o‑mini

- Tiktoken

- Datasets

## **6. RAG Pipeline Details**
### Document Loading
PDF loaded using PyMuPDFLoader.

### Chunking
Token‑based splitting using RecursiveCharacterTextSplitter with cl100k_base encoding.

### Embeddings
Generated using OpenAIEmbeddings.

### Vector Store
Stored and queried using ChromaDB.

### Retrieval
retriever.get_relevant_documents() fetches top‑k relevant chunks.

### LLM Answer Generation
GPT‑4o‑mini produces grounded answers using retrieved context.

## **7. How to Run the Notebook**
1. Install dependencies (already included inside the notebook).

2. Restart the runtime after installation (required for LangChain compatibility).

3. Add your OpenAI API key in the config file.

4. Run all cells sequentially.

The notebook contains:

- Installation

- Data loading

- Chunking

- Embeddings

- Retrieval

- RAG QA

- Debugging notes

## **8. Example Queries**
The notebook demonstrates answering:

- Who are the authors of the article?

- What leadership characteristics are mentioned?

- How has Apple’s leadership contributed to innovation?

The RAG system retrieves accurate answers directly from the PDF.

## **9. Key Observations**
- LLM alone → general, non‑document‑specific answers

- LLM + prompt engineering → more structured but still not grounded

- RAG pipeline → accurate, document‑verified answers

- RAG significantly improves reliability and reduces hallucinations

- Chunking and embedding quality directly affect retrieval accuracy

## **10. Repository Structure**
Code
/notebooks
    Strategic_Insights_RAG_System.ipynb

/assets
    rag_architecture.png   (optional)

problem_statement.txt      (optional)
README.md
requirements.txt
## **11. Future Enhancements**
- Add LangGraph workflow for agentic behavior

- Add UI using Streamlit or FastAPI

- Add multi‑document retrieval

- Add evaluation metrics (BLEU, ROUGE, RAGAS)

Add caching for faster retrieval
