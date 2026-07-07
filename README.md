#  Traditional vs. Vector Database: Search Architecture Comparison

This repository provides a practical, FastAPI-based proof of concept comparing traditional relational database search (exact keyword matching) with vector database search (semantic meaning matching). 

**The Use Case:** Querying unstructured tenant chat transcripts within a Property Management system.

## 🎯 Purpose of this Repository

As applications increasingly rely on unstructured data, traditional exact-match queries often fall short of user expectations. The purpose of this project is to demonstrate the concrete advantages of vector embeddings over standard SQL `LIKE` operators when handling natural language.

In this demonstration, I prove that while a traditional relational database is highly efficient for structured data, it suffers a 0% recall rate when users search using synonyms or concepts. Conversely, the vector database interprets semantic intent, successfully retrieving accurate records even with zero keyword overlap.

## ⚙️ What This Project Does

This project spins up a backend API using **FastAPI** that simultaneously queries two distinct in-memory databases against the same dataset:

1. **Traditional Relational DB (SQLite):** Represents the legacy approach. Uses SQL `LIKE` queries to find exact alphanumeric matches.
2. **Vector DB (ChromaDB):** Represents the modern, AI-driven approach. Converts text into high-dimensional mathematical vectors (embeddings) to calculate the geometric distance (semantic similarity) between the search query and the records.

### The Dataset
A mock collection of unstructured tenant messages:
* *"The heating in apartment 4B is broken and it is freezing."*
* *"I need to renew my lease for another year."*
* *"Can I pay my rent using a credit card?"*
* *"The lock on the main courtyard gate is jammed."*

  Scenario 01

<img width="622" height="543" alt="image" src="https://github.com/user-attachments/assets/b0fc6499-a377-4e77-8ba7-2c54f4ea83ea" />


  Scenario 02
  HVAC issue refers to any malfunction, inefficiency, or failure in your Heating, Ventilation, and Air Conditioning system.

  <img width="672" height="447" alt="image" src="https://github.com/user-attachments/assets/3509d998-08df-4f78-b708-de28f65dadae" />




---

## 🚀 How to Evaluate and Run the Project

You can evaluate this project either locally or instantly via Google Colab.


### Run Locally

**1. Clone the repository and install dependencies:**
```bash
git clone [https://github.com/yourusername/vector-vs-traditional-db.git](https://github.com/yourusername/vector-vs-traditional-db.git)
cd vector-vs-traditional-db
pip install fastapi uvicorn chromadb sqlite3 pydantic requests
