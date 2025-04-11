# Local RAG Stack with Ollama, Deepseek, Qdrant & OpenWebUI

I initially wrote a prototype of a RAG app using Python and Streamlit. While it worked for local MVP use, adding all the features I wanted would have taken too much time and effort.

Instead there is a simple `docker-compose` setup that integrates everything out of the box and runs locally without extra code.

## 🚀 What's Included

This stack includes the following services:

- **Ollama**  
  A local LLM runtime for running models like `deepseek-llm:7b-chat`.

- **Deepseek-LLM:7b-chat**  
  Automatically pulled and loaded via a helper container at startup.

- **Qdrant**  
  A high-performance vector database used for storing and retrieving embeddings.

- **OpenWebUI**  
  A sleek interface to interact with the model, manage documents, and run RAG-based queries.

## 📦 How to Use

1. Clone the repo and navigate to the project folder.
2. Run:

   ```bash
   docker-compose up


## Use cases

I use this local stack for two main purposes:

### 1. Simple Prompting  
You can chat directly with DeepSeek using OpenWebUI like any regular LLM chat interface.

### 2. Retrieval-Augmented Generation (RAG)  
To enable RAG, upload your document(s) in **OpenWebUI → Workspace → Knowledge**. Once uploaded, you can reference them in your prompt by using the `#` symbol followed by the document name.

For example:

```text
#MyDoc What does this document say about data retention policies?