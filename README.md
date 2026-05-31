Advanced RAG Workflow in n8n
🚀 Overview
This project implements an Advanced Retrieval-Augmented Generation (RAG) pipeline using n8n. It combines Pinecone Vector DB, OpenAI embeddings, Cohere reranker, and Ollama Chat Model to deliver accurate, context aware answers.
🛠 Steps Explained
1. Data Ingestion
•	On form submission or document upload:
o	Default Data Loader → loads raw text.
o	Recursive Character Text Splitter → breaks text into smaller chunks.
o	Embeddings OpenAI → converts chunks into vectors.
o	Pinecone Vector Store → stores vectors for retrieval.
2. Retrieval Phase
•	User sends a query via Chat node.
•	AI Agent receives the query with strict RAG rules:
o	Use only reranked context.
o	No outside knowledge.
o	If insufficient → reply: “I don’t have enough context to answer that.”
o	Keep answers concise with inline citations.
3. Vector Search + Reranking
•	Pinecone Vector Store retrieves top K relevant chunks.
•	Embeddings OpenAI ensures query is vectorized properly.
•	Cohere Reranker reorders chunks by relevance.
4. Answer Generation
•	Ollama Chat Model generates the final answer.
•	AI Agent enforces rules and formats the response.
 
