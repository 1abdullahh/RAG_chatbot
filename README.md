# 📄 Multi-Format RAG Agent
Steamlit link: https://ragchatbot-1abdullahh.streamlit.app/ 

A professional Retrieval-Augmented Generation (RAG) application built with Python, Streamlit, LangChain, FAISS, and OpenAI.

The application allows users to upload documents and images, index their content, and ask questions that are answered strictly from the uploaded files. It supports multiple file formats and provides source references for retrieved content.

✨ Features

🔐 OpenAI API Key Validation

Validates the API key before the application starts.

The key is kept only in the current Streamlit session.

💬 Interactive Chat Interface

ChatGPT-style conversation interface.

Multiple independent chat sessions.

Chat history maintained during the active session.

Automatic chat titles based on the first question.

📎 Multi-Format File Upload

PDF

Microsoft Word (.docx)

Microsoft PowerPoint (.pptx)

CSV

Excel (.xlsx, .xls)

Images (.png, .jpg, .jpeg)

🔎 RAG-Based Question Answering

Uploaded content is split into searchable chunks.

OpenAI embeddings are used to create vector representations.

FAISS is used for similarity search.

Only relevant chunks are retrieved for answering questions.

🧠 Source-Grounded Answers

Answers are generated only from retrieved document context.

If the information cannot be found, the assistant responds:

"I couldn't find that in the document."

Sources include the file name and location, such as page, slide, row, sheet, or OCR.

🖼️ Image OCR

Text can be extracted from uploaded images using Tesseract OCR.

⚙️ Configurable RAG Settings

Select the OpenAI chat model.

Adjust chunk size.

Adjust chunk overlap.

Control the number of retrieved chunks (top-k).

🏗️ How It Works

User uploads files
        ↓
File-specific loader
        ↓
Text/content extraction
        ↓
Text chunking
        ↓
OpenAI Embeddings
        ↓
FAISS Vector Store
        ↓
Similarity Search
        ↓
Relevant Context
        ↓
OpenAI Chat Model
        ↓
Grounded Answer + Sources

🧰 Tech Stack

Technology

Purpose

Python

Core application language

Streamlit

Web interface and chat UI

LangChain

RAG pipeline and document processing

OpenAI

Chat models and embeddings

FAISS

Vector similarity search

PyPDF

PDF text extraction

python-docx

Word document processing

python-pptx

PowerPoint processing

Pandas

CSV and Excel processing

Pillow

Image handling

Tesseract OCR

Text extraction from images

📁 Supported File Types

Format

Processing

.pdf

PDF text extraction with page information

.docx

Word paragraph extraction

.pptx

Slide-by-slide text extraction

.csv

Row-based document creation

.xlsx / .xls

Sheet-based document extraction

.png / .jpg / .jpeg

OCR text extraction

🚀 Getting Started

1. Clone the Repository

git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_PROJECT_FOLDER>

2. Create a Virtual Environment

macOS / Linux

python3 -m venv .venv
source .venv/bin/activate

Windows

python -m venv .venv
.venv\Scripts\activate

3. Install Dependencies

pip install -r requirements.txt

4. Install Tesseract OCR

Tesseract is required for processing image files.

macOS

brew install tesseract

Ubuntu / Debian

sudo apt-get update
sudo apt-get install tesseract-ocr

If you only use PDF, Word, PowerPoint, CSV, or Excel files, Tesseract is not required for those formats.

5. Run the Application

Replace the filename below with the actual Python file name in your repository:

streamlit run app.py

Streamlit will provide a local URL, usually:

http://localhost:8501

🔑 OpenAI API Key

When the application starts, it asks for an OpenAI API key.

The application:

Accepts the API key through a password field.

Validates the key using the OpenAI API.

Stores it in the current Streamlit session.

Uses it for chat completions and embeddings.

Do not commit your API key to GitHub.

For production deployments, use your hosting platform's secret/environment-variable management instead of hard-coding credentials.

💡 How to Use

Start the Streamlit application.

Enter and validate your OpenAI API key.

Create a new chat if needed.

Click the + attachment button in the chat input.

Upload one or more supported files.

Ask a question about the uploaded content.

The application indexes the files automatically.

Review the answer and expand Sources (retrieved chunks) to inspect the retrieved content.

Example Questions

What is the main purpose of this document?

Summarize the key points from the presentation.

What does the report say about revenue?

Which row contains the highest sales value?

What information is available on page 5?

⚙️ RAG Configuration

The sidebar provides controls for the retrieval pipeline:

Chat Model — Select the OpenAI model used to generate answers.

Chunk Size — Controls the approximate size of text chunks.

Chunk Overlap — Controls how much text overlaps between neighboring chunks.

Retrieved Chunks (k) — Controls how many relevant chunks are retrieved for each question.

Changing chunk size or overlap causes the application's index to be rebuilt for the current chat.

🔒 Security Notes

Never publish your OpenAI API key in source code.

Never commit .env files containing real secrets.

Add sensitive files to .gitignore.

Use environment variables or a secure secrets manager for deployment.

Uploaded files and chat data are maintained in Streamlit session state by this application; they are not implemented as a permanent database.

⚠️ Important Notes

Image processing depends on the Tesseract OCR engine being installed on the host system.

The quality of answers depends on the text successfully extracted from uploaded files.

Scanned PDFs may require OCR support if their content is image-based rather than selectable text.

Large documents may require additional processing time while they are being indexed.

OpenAI API usage may incur costs according to the selected models and API account.

📦 Requirements

The project uses the following main Python packages:

streamlit
langchain-core
langchain-openai
langchain-community
langchain-text-splitters
faiss-cpu
pypdf
openai
python-docx
python-pptx
pandas
openpyxl
pytesseract
pillow

See requirements.txt for the project's dependency versions.

📂 Suggested Project Structure

multi-format-rag-agent/
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore

If your Python source file has a different name, keep that filename in the repository and update the run command accordingly.

🎯 Project Purpose

This project demonstrates how a modern RAG-based document assistant can combine document ingestion, text extraction, embeddings, vector search, and large language models into a single user-friendly application.

It is suitable for learning and demonstrating:

Retrieval-Augmented Generation

Semantic search

Vector databases

LangChain workflows

Document question answering

Multi-format document processing

OCR integration

Streamlit application development

📄 License

Add your preferred license here, for example:

MIT License

If this project is intended for public distribution, include a complete LICENSE file in the repository.

Built With

Python • Streamlit • LangChain • OpenAI • FAISS • Pandas • Tesseract OCR
