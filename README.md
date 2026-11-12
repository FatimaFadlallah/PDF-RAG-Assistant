# PDF RAG Assistant

Ever wished you could ask questions about a PDF instead of scrolling through dozens of pages to find the information you need?

That's the idea behind this project!

I built a **PDF RAG Assistant** that lets users ask questions about multiple PDF documents and get answers based on their actual content.

Instead of simply sending a question to an LLM and hoping for the right answer, the system first searches the documents for relevant information, then gives that information to Gemini to generate a response.

## What can it do?

- Read and extract text from multiple PDF files.
- Break long documents into smaller chunks.
- Convert text into embeddings using Sentence Transformers.
- Store document chunks and their embeddings in ChromaDB.
- Search for relevant information using semantic and keyword-based retrieval.
- Use Gemini to generate answers based on the retrieved content.
- Show which PDF and page the information came from.
- Handle questions whose answers aren't available in the documents.

## How does it work?

The project follows a RAG (Retrieval-Augmented Generation) workflow:

1. **Load PDFs:** The system reads multiple PDF files and extracts their text.
2. **Chunking:** The extracted text is divided into smaller pieces to make searching more effective.
3. **Embeddings:** Each chunk is converted into a numerical representation using Sentence Transformers.
4. **Storage:** The embeddings, text, and page information are stored in ChromaDB.
5. **Retrieval:** When a user asks a question, the system searches for relevant chunks using semantic and keyword-based retrieval.
6. **Answer generation:** The retrieved information is sent to Gemini, which generates an answer based on the provided context.

## Tools & Technologies

- Python
- Google Gemini API
- Sentence Transformers (`all-MiniLM-L6-v2`)
- ChromaDB
- PyPDF
- NumPy

## Example Questions

Here are a few questions I tested:

- What is a variable in Python?
- What is a histogram?
- What is correlation?
- What is complexity science?
- What is the capital of Japan? *(An example of a question not covered by the documents.)*

The system is instructed to say when an answer cannot be found in the provided documents rather than making up information.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/FatimaFadlallah/PDF-RAG-Assistant.git
cd PDF-RAG-Assistant
```

### 2. Install the required libraries

```bash
pip install pypdf chromadb sentence-transformers google-genai numpy python-dotenv
```

### 3. Set up your API key

Create a `.env` file in the project folder:

```env
GEMINI_API_KEY=your_api_key_here
```

Replace the placeholder with your own Gemini API key.

### 4. Add your PDF files

Create a folder called `documents` and place your PDF files inside it.

The PDFs used during development are not included in this repository, so you can use your own documents.

### 5. Run the project

Open `pdf_rag_clean.ipynb` in Jupyter Notebook or VS Code and run the cells in order.

## What I Learned

Building this project gave me practical experience with the main components of a RAG pipeline, including document processing, chunking, embeddings, vector databases, information retrieval, and LLM integration.

It also helped me understand how semantic search and keyword search can complement each other when retrieving information from documents.

## Future Improvements

There is still room to improve the project. Some ideas I'd like to explore next include:

- Improving retrieval accuracy and ranking.
- Adding persistent storage to ChromaDB.
- Building a simple user interface.
- Evaluating answer quality and retrieval performance more systematically.

## Author

**Fatima Fadlallah**

Data Science & AI Graduate | Aspiring AI Engineer


