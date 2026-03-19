# Embedding Neo4j - RAG with AI

## 📋 Project Description

This project implements a **Retrieval-Augmented Generation (RAG)** system that allows you to ask questions about PDF documents using an AI. The workflow functions as follows:

1. **Ingestion**: Reads a PDF document
2. **Chunking**: Breaks the document into smaller chunks for efficient processing
3. **Embedding**: Generates embeddings (vector representations) of the chunks
4. **Storage**: Saves the embeddings in a vectorized database (Neo4j)
5. **Search**: Retrieves the top-k most relevant chunks based on the user's question
6. **Context Injection**: Injects the relevant chunks into a prompt
7. **Response**: Sends the prompt to an AI to answer based on the provided context

## 🛠️ Technology Stack

### **OpenRouter**
An AI model aggregation platform that offers:
- Access to **multiple LLM models through a single endpoint**
- **Completely free models** available
- Flexibility to switch between different AI providers without changing code
- Ideal for prototyping and development without initial costs

### **Neo4j**
A graph database with **vector search** support:
- Stores and indexes embeddings from document chunks
- Enables efficient vector searches to find semantically similar chunks
- Provides a robust and scalable way to manage large volumes of textual data
- Combines structured data (graph) with vectorized search capabilities

### **LangChain**
A framework that standardizes and orchestrates AI pipelines:
- **Standardizes prompts**: facilitates creation and management of prompt templates
- **Creates pipelines**: organizes processing steps in a logical and reusable sequence
- **Vector store integration**: connects seamlessly with Neo4j for vectorized search
- **Reusable components**: offers abstractions that simplify building complex AI applications

## 🚀 How It Works

```
PDF → Chunking → Embedding → Neo4j (Vector DB)
                                    ↓
                            User Question
                                    ↓
                    Search for K most similar chunks
                                    ↓
                    Inject chunks into prompt with context
                                    ↓
                    Call AI (OpenRouter)
                                    ↓
                            Generated Response
```

## 📦 Architecture

- **`src/`**: TypeScript source code
  - `index.ts`: Entry point
  - `documentProcessor.ts`: PDF processing and chunking
  - `ai.ts`: OpenRouter and LLM integration
  - `config.ts`: General configurations
  - `util.ts`: Utility functions

- **`neo4j/`**: Neo4j database data
- **`prompts/`**: Prompt templates
- **`answers/`**: History of generated responses

## 🔧 Requirements

- Node.js
- Docker (to run Neo4j)
- OpenRouter API key

## 📝 License

MIT
