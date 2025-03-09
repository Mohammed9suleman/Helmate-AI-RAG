# HelpMate AI: A Generative Search System for Insurance Policy Documents

## Overview

HelpMate AI is a robust Retrieval Augmented Generation (RAG) system designed for the insurance domain. It enables users to ask natural language queries and receive accurate, context-aware responses extracted from various insurance policy documents. The project leverages LangChain for pipeline integration and GROQ AI as the generative model, ensuring a scalable and cost-effective solution.

---

## Features

- **Generative Search**: Provides concise, contextually relevant answers to user queries.
- **Semantic Retrieval**: Efficiently retrieves document sections based on semantic relevance using SBERT embeddings.
- **Scalability**: Designed for handling diverse document collections with flexibility and efficiency.
- **Cost-Effective**: Utilizes open-source frameworks like GROQ AI and Chroma for cost efficiency.

---

## Tools and Frameworks

- **LangChain**: Framework for building pipelines and integrating LLMs.
- **GROQ AI**: Generative AI for creating context-aware responses.
- **SBERT (Sentence-BERT)**: Embedding model for semantic representation.
- **Chroma**: Vector database for text embedding storage and retrieval.
- **Text Splitters**: Used for preprocessing documents into manageable chunks.

---

## Data Source

The project uses 217 publicly available insurance policy documents. Example policies include:

- HDFC Life Sanchay Plus Policy Document
- HDFC Life Sampoorna Jeevan Policy Document

Documents are stored in the directory: `/content/drive/MyDrive/Policy-Documents/`.

---

## Solution Design

### 1. Indexing Process (Offline)
Prepares documents for fast semantic search.
- **Load Documents**: Use `DirectoryLoader` to load PDF files.
- **Split Documents**: Break documents into smaller chunks with `RecursiveCharacterTextSplitter`.
- **Generate Embeddings**: Convert text to dense vector embeddings with SBERT.
- **Store in Vector Database**: Save embeddings in a Chroma vector store for efficient retrieval.

### 2. Retrieval and Generation (Runtime)
Provides real-time answers to user queries.
- **User Query Input**: Accepts natural language input.
- **Retrieve Documents**: Performs a similarity search on the vector store.
- **Generate Answer**: Combines retrieved documents with the user query using GROQ AI.
- **Return Answer**: Displays concise, accurate responses.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repository/helpmate-ai.git
   cd helpmate-ai
   ```

2. Install dependencies:
   Use the following command to install the required Python libraries:
   ```bash
   pip install langchain groq-client chromadb sentence-transformers
   ```

3. Set up API keys for LangChain and GROQ AI:
   - Create a `.env` file in the root directory and add:
     ```
     LANGCHAIN_API_KEY=<your_langchain_key>
     GROQ_API_KEY=<your_groq_key>
     ```

4. Verify installation:
   After installation, run a small test script to ensure all dependencies are correctly installed.
   
---

## Usage

1. **Load and Preprocess Documents**:
   - Ensure documents are placed in `/content/drive/MyDrive/Policy-Documents/`.
   - Run the preprocessing script to load, split, and store embeddings.

2. **Query System**:
   - Use the runtime script to input user queries and retrieve answers.

---

## Challenges Faced

- **API Key Configuration**: Proper setup for seamless integration.
- **Document Variability**: Handling inconsistent formats and metadata.
- **Chunk Optimization**: Tuning chunk sizes for embedding accuracy.

---

## Lessons Learned

- Importance of reliable data extraction and preprocessing.
- Optimizing retrieval mechanisms for efficiency.
- Addressing input length limitations effectively.

---

## Future Enhancements

- Expand the system to handle multi-lingual documents.
- Incorporate advanced ranking mechanisms for retrieval.
- Explore additional generative AI models for enhanced performance.

---

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.
