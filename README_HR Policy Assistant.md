# HR Policy Assistant — RAG‑Powered Query System
A Retrieval‑Augmented Generation (RAG) prototype that enables employees to ask natural‑language questions about company HR policies and receive accurate, contextual, and source‑grounded answers.

## **📌 Overview**
Modern organizations operate with increasingly complex HR policies — covering leave rules, reimbursements, travel norms, hybrid work expectations, compliance, and employee conduct. These policies are typically buried inside long PDF handbooks that employees struggle to navigate.

This leads to:

- HR teams repeatedly answering routine questions

- Employees misunderstanding or misapplying policies

- Delays, confusion, and reduced productivity

- Lower compliance due to unclear or inaccessible information

- This project demonstrates how NLP + RAG can transform static HR documents into an interactive, intelligent policy assistant.

## **🎯 Objective**
Build a prototype that allows employees to ask HR‑related questions and receive:

- **Accurate answers** grounded in official policy documents

- **Context‑aware responses** that handle ambiguity

- **Personalized guidance** based on role, location, or department

- **Cited sources** (document name, section, clause) to increase trust and compliance

## **🧠 What the System Can Do**
- Retrieve relevant sections from the HR handbook

- Answer employee questions in simple, clear language

- Distinguish between similar policies (e.g., sick leave vs casual leave)

- Handle follow‑up questions and ambiguous queries

- Provide actionable steps (e.g., whom to inform, required documentation)

- Cite the exact source of truth for every answer

## **💬 Example Questions the System Handles**
- *“What are the effects on the benefits I receive if my probation is extended?”*

- *“There has been a demise in my family last night. How should I inform the office, and will I be granted leave?”*

- *“What should I do if I notice suspected harassment with my female colleague?”*

## **📄 Dataset**
The system uses the Flykite Airlines Employee Handbook (PDF) as the primary knowledge source.
This document contains policies related to:

- Leave & attendance

- Travel & reimbursement

- Conduct & compliance

- Performance management

- Workplace behavior

- HR processes & escalation paths

## **🏗️ Architecture (RAG Workflow)**
### **Indexing Phase**

PDF Document → Text Extraction → Chunking → Embeddings → Vector Store (Chroma)

### **Query Phase**

User Query → Query Embedding → Similarity Search (Chroma) → Top‑k Relevant Chunks → LLM with Context → Final Answer + Source Citation

This architecture ensures:

- High retrieval accuracy

- Modular components

- Easy swapping of LLMs, retrievers, or vector stores

- Production‑grade reliability

## **⚙️ Tech Stack**
- Python

- LangChain / LangGraph

- OpenAI GPT‑4o‑mini

- ChromaDB

- PyMuPDF for PDF extraction

- Token‑based chunking

- Semantic search

## **🚀 How It Works**
1. Load and parse the HR handbook PDF

2. Chunk the text into semantically meaningful segments

3. Generate embeddings and store them in ChromaDB

4. Convert user queries into embeddings

5. Retrieve the most relevant policy chunks

6. Pass retrieved context + query to the LLM

7. Generate a grounded, source‑cited answer

Generate a grounded, source‑cited answer