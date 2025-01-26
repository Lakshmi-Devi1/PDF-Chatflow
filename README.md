# PDF ChatFlow

PDF ChatFlow is a tool that allows users to interact with PDF documents through a chat interface. By uploading a PDF, users can ask questions, and the system will respond with answers based on the content of the PDF. This is powered by Google’s Gemini API and advanced AI techniques to process and retrieve relevant information.

## Problem
Manually searching through large PDF documents (e.g., research papers, reports, or contracts) can be time-consuming. PDF ChatFlow simplifies this by enabling users to extract information from these documents more efficiently.

### Key Challenges:
1. **Manual Search Limitation**: Finding relevant information in PDFs using traditional search methods is hard.
2. **Large Text Volume**: PDFs can be too lengthy to navigate easily.
3. **Contextual Answering**: Extracting context-based answers from PDFs requires understanding the document's content.

## Solution

The PDF ChatFlow solves these challenges by:
1. **Text Extraction**: Extracts text from uploaded PDF files.
2. **Text Chunking**: Breaks the extracted text into smaller chunks for better processing.
3. **Embedding & Vectorization**: Converts text chunks into numerical vectors for efficient searching.
4. **AI-Powered Q&A**: Uses Google’s Gemini API to answer user questions based on the PDF content.
5. **Streamlit Interface**: A simple web interface for users to upload PDFs and ask questions.

## Tech Stack

- **Python**: Core programming language.
- **Streamlit**: For building the user interface.
- **PyPDF2**: To extract text from PDFs.
- **LangChain**: For text splitting and Q&A chains.
- **Gemini API**: For generating embeddings and generating responses.
- **FAISS**: For efficient vector search.
- **dotenv**: For managing API keys securely.

## How It Works

1. **Upload PDF**: User uploads PDF(s) through the Streamlit interface.
2. **Text Extraction**: The system extracts all text from the PDF.
3. **Text Chunking**: Text is split into smaller chunks for easier processing.
4. **Vectorization**: Text chunks are converted into vectors for efficient searching.
5. **Query Processing**: When the user asks a question, the system finds the relevant sections and generates a response based on the document's content.

## Running the Project

### 1. Set Up Development Environment
- Install Python and set up a virtual environment:
  ```bash
  python -m venv chatflow_env
  source chatflow_env/bin/activate  # On Windows: chatflow_env\Scripts\activate
  ```
- Install dependencies:
  ```bash
  pip install streamlit pypdf2 langchain langchain-google-genai faiss-cpu google-generativeai python-dotenv
  ```
- Add your Google API key in a `.env` file:
  ```
  GOOGLE_API_KEY=your_google_api_key_here
  ```

### 2. Run the Application
- Start the app:
  ```bash
  streamlit run your_script_name.py
  ```
- Open the app in your browser at `http://localhost:8501`.
- Upload PDFs and ask questions via the interface!

## Code Overview

- **Text Extraction**: `get_pdf_text()` reads and extracts text from PDFs.
- **Text Chunking**: `get_text_chunks()` splits large text into smaller chunks.
- **Embedding & Search**: `get_vector_store()` creates and stores vector embeddings for text chunks.
- **Q&A Chain**: `get_conversational_chain()` sets up the system to answer questions.
- **User Input**: `user_input()` processes the query and generates a response.
