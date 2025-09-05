Retrieval-Augmented Generation (RAG) Chatbot

This repository contains a Jupyter Notebook that demonstrates how to build a simple Retrieval-Augmented Generation (RAG) chatbot using LangChain, OpenAI, and ChromaDB. The notebook guides you through the entire process, from loading a document to generating answers based on its content.

![RAG Workflow](https://miro.medium.com/v2/resize:fit:824/1*GK56xmDIWtNQAD_jnBIt2g.png)

## Overview

Retrieval-Augmented Generation (RAG) is a technique that enhances the accuracy and reliability of Large Language Models (LLMs) by grounding them in external knowledge bases. Instead of relying solely on its pre-trained knowledge, the model first retrieves relevant information from a specified document source and then uses that information to generate a response.

This notebook implements the following workflow:
1.  **Load Document**: Ingest a PDF document using LangChain's `PyPDFLoader`.
2.  **Split & Chunk**: Break the document into smaller, semantically meaningful chunks using `RecursiveCharacterTextSplitter`.
3.  **Embed**: Convert the text chunks into numerical vector representations (embeddings) using OpenAI's `text-embedding-3-large` model.
4.  **Store**: Store these embeddings in a `ChromaDB` vector store for efficient retrieval.
5.  **Retrieve**: Given a user question, perform a similarity search in the vector store to find the most relevant chunks.
6.  **Generate**: Pass the original question and the retrieved context to an LLM (like GPT-4o) to generate a final, context-aware answer.

## Technologies Used

-   **Python 3.10+**
-   **LangChain**: A framework for developing applications powered by language models.
-   **OpenAI**: For generating text embeddings and the final chat response.
-   **ChromaDB**: An open-source vector database for storing and querying embeddings.
-   **PyPDF**: A library to read and extract text from PDF files.
-   **Jupyter Notebook**: For interactive development and demonstration.

## Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites

-   An [OpenAI API Key](https://platform.openai.com/account/api-keys).

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    cd your-repo-name
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(You can create a `requirements.txt` file with the content from the first code cell in the notebook, or simply run the pip install commands from the notebook.)*

4.  **Set up your environment variables:**
    -   Create a file named `.env` in the root of the project directory.
    -   Add your OpenAI API key to this file:
        ```
        OPENAI_API_KEY="your-openai-api-key-here"
        ```

5.  **Add your data source:**
    -   Place the PDF file you want to use as the knowledge base into the appropriate directory.
    -   Update the `file_path` variable in the notebook to point to your PDF file. For example:
        ```python
        file_path = "path/to/your/document.pdf"
        ```

### Running the Notebook

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
2.  Open the `LAB_GenAI_RAG_Chatbot.ipynb` file.
3.  Run the cells sequentially from top to bottom.

##  exercice 
1. `Exercice1`: Write a user question that someone might ask about your book’s topic or content.
2. `Exercice2`: Write a prompt that is relevant and tailored to the content and style of your book.
3. `Exercice3`: Tune parameters like `temperature`, and `penalties` to control how creative, focused, or varied the model's responses are.
4. `Exercice4`: add your keywords