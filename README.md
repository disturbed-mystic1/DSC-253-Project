# DSC253-Project: Enhancing Financial Document Analysis with RAG: A Study on SEC-10K Filings Using LLaMA-3 and Retrieval Mechanisms

This project explores the application of RAG on financial documents, particularly SEC-10k fillings. By fine-tuning the LLaMA-3 language model and using Low-Rank Adaptation (LoRA), our system is able to process financial documents efficiently and accurately. We also incorporate a powerful retrieval setup that uses dense vector embeddings and a FAISS-based vector database to ensure the results are relevant and high-performing. In this paper, we compare three SOTA open-source models and two retrieval mechanisms to highlight how our system effectively generates detailed financial insights, tackling the challenges that come with working on large, unstructured financial datasets.

**Authors**: Aryan Philip, Nandita Sanjivi, Tejas Ramesh


### Dataset
The SEC's Query API is utilized to retrieve the latest 10-K filings for a given stock ticker, focusing on key sections such as **1A: Risk Factors** and **7: Management’s Discussion and Analysis**. While these sections provide critical insights, section 8 also holds valuable data about a company's financial health and could be leveraged for more comprehensive analyses. To facilitate processing, the filings are segmented into smaller, manageable text chunks using a recursive text splitter. Each chunk is limited to 1000 characters, with a 500-character overlap, ensuring context is preserved while enabling efficient analysis.


### Prompting the Model
Two methods are employed for retrieval. Initially, it uses a similarity-based method to identify documents that closely match the user query based on vector embeddings. However, to avoid redundancy and ensure a diverse set of information, the incorporation of Maximum Marginal Relevance (MMR) is performed. MMR selects documents that are not only relevant but also distinct from one another, thereby providing a broader range of perspectives. This combination allows the system to retrieve a comprehensive set of documents that enriches the context for subsequent processing. After retrieving relevant documents, it constructs prompts that guide the LLaMA-3 language model in generating responses. The prompts are formulated by embedding both the user query and the retrieved document chunks, ensuring that the model has access to pertinent information. This structured prompting enables the model to produce coherent and contextually accurate answers, effectively leveraging the insights from the retrieved documents.

### Datasets

The datasets cleaned_candidates.csv and cleaned_references.csv provide the responses and reference answer from the Llama3 8B-instruct model respectively.

#### Notebooks

To run the notebooks please clone this repository and change the directory to your working directory.

```python
git clone https://github.com/your-github/DSC-253-Project.git
```
```bash
cd DSC-253-Project
```
To run the QA please execute DSC253Project.ipynb in colab and the metrics can be run metrics.ipynb. 

To replicate the results for the ROUGE and BLEU score comparison among different models, copy and add the code from ROUGE_BLEU_comparison.ipynb to DSC253Project.ipynb and execute those cells.


#### Example

What Ticker Would you Like to Analyze? AAPL

What would you like to know about AAPL's form 10-K? What were the major sources of profit? 
The major sources of profit are net sales from the Americas, Europe, Greater China, Japan, and Rest of Asia Pacific segments.

What would you like to know about AAPL's form 10-K? What were the contributions from the Asia region?
The contributions from the Asia region were 96,169 million in 2024, which represents a 13% increase compared to 2023 and a 9% increase compared to 2022.




**Special Thanks**: [Adam Lucek](https://www.youtube.com/@AdamLucek) for providing a walkthrough of the process on his [YouTube Channel](https://youtu.be/GfjUJ1TnI-o?feature=shared)
