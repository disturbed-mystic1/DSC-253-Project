# DSC253-Project: Enhancing Financial Document Analysis with RAG: A Study on SEC-10K Filings Using LLaMA-3, LoRA, and Retrieval Mechanisms

This project explores the application of RAG on financial documents, particularly SEC-10k fillings. By fine-tuning the LLaMA-3 language model and using Low-Rank Adaptation (LoRA), our system is able to process financial documents efficiently and accurately. We also incorporate a powerful retrieval setup that uses dense vector embeddings and a FAISS-based vector database to ensure the results are relevant and high-performing. In this paper, we compare three SOTA open-source models and two retrieval mechanisms to highlight how our system effectively generates detailed financial insights, tackling the challenges that come with working on large, unstructured financial datasets.

**Authors**: Aryan Philip, Nandita Sanjivi, Tejas Ramesh


### Dataset
The SEC's Query API is utilized to retrieve the latest 10-K filings for a given stock ticker, focusing on key sections such as **1A: Risk Factors** and **7: Management’s Discussion and Analysis**. While these sections provide critical insights, section 8 also holds valuable data about a company's financial health and could be leveraged for more comprehensive analyses. To facilitate processing, the filings are segmented into smaller, manageable text chunks using a recursive text splitter. Each chunk is limited to 1000 characters, with a 500-character overlap, ensuring context is preserved while enabling efficient analysis.


#### Prompting the Model


#### Example

**Citation:**


**Special Thanks**: Adam Lucek for providing a walkthrough of the process on his YouTube Channel
