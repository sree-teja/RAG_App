# RAG App Using AWS Bedrock And Langchain

## Overview
This project uses a Retrieval-Augmented Generation (RAG) system that utilizes multiple PDFs as knowledge sources. The PDFs are stored as vector embeddings in a vector store. When a user asks a question, the system retrieves relevant information from these documents using AWS Bedrock models. The response is generated based on the selected model (e.g., Claude or Llama 2).

## Requirements
To run this project, you need the following Python libraries:

- `PyPDF`
- `Langchain`
- `Streamlit`
- `FAISS-CPU`
- `boto3` and AWS CLI (configured)

## Architecture
The RAG system follows these steps:

### **Data Injection**
1. Read all PDFs from a specified folder.
2. Split the documents into manageable chunks.
3. Create vector embeddings using Amazon Titan.
4. Store the embeddings in a FAISS vector database.

### **Querying**
1. Perform a similarity search in the vector store based on the user’s question.
2. Retrieve the most relevant document chunks.
3. Feed the retrieved chunks along with a prompt to an LLM model via AWS Bedrock.
4. The LLM generates an answer based on the provided context and prompt.

## Usage
Run the Streamlit application to interact with the system:
```sh
streamlit run app.py
```

Ensure that your AWS CLI credentials are properly set up before executing the program.

## Conclusion
This RAG-based system enhances LLM responses by grounding them in authoritative documents, improving accuracy and reliability. By leveraging AWS Bedrock and FAISS, it efficiently retrieves and generates contextually relevant answers.

