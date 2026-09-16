# 🧠 AI Therapist RAG System

A Retrieval-Augmented Generation (RAG) system designed to answer therapy-related questions using a CBT (Cognitive Behavioral Therapy) knowledge base.

This project was developed as part of **Day 2 Lab** and implements the RAG pipeline in two approaches:

* **Part A:** Manual RAG Pipeline using Python, Embeddings, and ChromaDB
* **Part B:** RAG Pipeline using LangGraph and LangSmith

## 🎯 Project Overview

The system retrieves relevant information from a therapy knowledge base and uses it to provide grounded responses.

The knowledge base contains **13 therapy-related documents** covering topics such as:

* CBT Fundamentals
* Cognitive Triangle
* Cognitive Distortions
* Thought Records
* Anxiety Management
* Relaxation Techniques
* Behavioral Activation
* Sleep Hygiene
* Stress Management
* Mindfulness
* Exposure Therapy
* Journaling Exercises
* Crisis Intervention

## ✨ Key Features

* 🚨 **Crisis Detection** using keyword matching
* 🔍 **Semantic Retrieval** using embeddings
* 🧠 **Sentence Transformers** with `all-MiniLM-L6-v2`
* 🗄️ **ChromaDB Vector Store**
* 📊 **Cosine Similarity** and relevance scoring
* 🔄 **Reranking** of retrieved documents
* 📝 **Grounded responses with citations**
* 📈 **Relevance score thresholds**
* 🕸️ **LangGraph workflow**
* 📊 **LangSmith integration**

## 🛠️ Technologies Used

* Python
* Sentence Transformers
* ChromaDB
* NumPy
* Scikit-learn
* LangChain
* LangGraph
* LangSmith

## 🔄 RAG Pipeline

```text
User Query
    ↓
Crisis Detection
    ↓
Query Embedding
    ↓
Vector Search
    ↓
Retrieve Relevant Documents
    ↓
Reranking
    ↓
Relevance Threshold Check
    ↓
Grounded Response
    ↓
Citations
```

## 🧩 Part A — Manual RAG Pipeline

The first part builds the RAG pipeline manually without relying on a RAG framework.

### 1. Crisis Detection

Before retrieval or any LLM call, the system checks the user's query for predefined crisis-related keywords.

The function returns:

```text
True  → Crisis detected
False → No crisis detected
```

### 2. Embeddings & Vector Store

The project uses:

```text
all-MiniLM-L6-v2
```

to convert the therapy documents into numerical embeddings.

The embeddings have a dimension of **384**, and the 13 documents are stored in a ChromaDB collection called:

```text
therapy_kb
```

### 3. Retrieval

For each query, the system retrieves the most relevant documents and calculates relevance using cosine similarity.

Example queries include:

* How do I deal with anxiety?
* What is the cognitive triangle?
* How can I sleep better?

## 🧩 Part B — LangGraph & LangSmith

The second part demonstrates how the same RAG workflow can be structured using **LangGraph** and monitored using **LangSmith**.

This provides a more structured approach that is closer to production-style AI workflows.

## 📊 Example Retrieval

For example, when asking:

```text
What is the cognitive triangle?
```

the system retrieves the corresponding CBT document as the most relevant result.

The retrieved result contains:

* Source
* Chapter
* Page
* Category
* Relevance score
* Document content

## 📁 Project Structure

```text
ai-therapist-rag-system/
│
├── Day2_Walaa_Omar_Hassan.ipynb
└── README.md
```

## ⚠️ Important Note

This project is an educational demonstration of a RAG system. It is **not a substitute for professional mental health care or clinical diagnosis**.

## 👩‍💻 Author

**Walaa Omar Hassan**

Computer Science Student | Data Science & AI Enthusiast
