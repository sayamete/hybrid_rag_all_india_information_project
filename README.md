# 🇮🇳 India Information RAG Chatbot

A **Retrieval-Augmented Generation (RAG)** based AI chatbot that can answer questions about **India** using a knowledge base containing information about India's history, geography, culture, states, economy, and other important topics.

The project combines **document retrieval + vector database + Large Language Model (LLM)** to provide context-aware and knowledge-grounded answers.

---

## 🚀 Project Overview

This project is designed to demonstrate how a **RAG pipeline** works in a real-world application.

Instead of asking an LLM to answer directly from its internal knowledge, the system:

1. Loads information from documents/web sources.
2. Splits the information into smaller chunks.
3. Converts the chunks into vector embeddings.
4. Stores the embeddings in a vector database.
5. Retrieves the most relevant information based on the user's question.
6. Sends the retrieved context to the LLM.
7. Generates a final answer based on the retrieved information.

### 🔄 RAG Pipeline

```text
User Question
      ↓
Query
      ↓
Retriever
      ↓
Vector Database
      ↓
Relevant Documents
      ↓
Context + Question
      ↓
Large Language Model
      ↓
Generated Answer
```

---

## ✨ Features

* 🇮🇳 Information about India
* 📚 History and historical events
* 🗺️ Geography of India
* 🏛️ States and Union Territories
* 👥 Population and demographics
* 💰 Economy and development
* 🎭 Culture and traditions
* 🌏 General information about India
* 🔍 Semantic document retrieval
* 🤖 LLM-powered question answering
* 📄 PDF/Web document ingestion
* 🧠 Context-aware responses
* 💾 Vector database for efficient retrieval

---

## 🛠️ Technologies Used

* **Python**
* **LangChain**
* **LangChain Community**
* **ChromaDB**
* **Groq / LLM**
* **Hugging Face Embeddings**
* **PyPDF**
* **WebBaseLoader**
* **Streamlit**
* **Vector Embeddings**
* **Retrieval-Augmented Generation (RAG)**

---

## 🧩 Architecture

```text
                ┌─────────────────────┐
                │   Data Sources      │
                │                     │
                │ PDFs / Web Pages    │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Document Loader    │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Text Splitter     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │     Embeddings      │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │     ChromaDB        │
                │   Vector Database   │
                └──────────┬──────────┘
                           │
                    User Question
                           │
                           ▼
                ┌─────────────────────┐
                │     Retriever       │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Groq LLM Model    │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │    Final Answer     │
                └─────────────────────┘
```

---

## 📂 Project Structure

```text
India-RAG-Chatbot/
│
├── data/
│   ├── india.pdf
│   ├── india_history.pdf
│   └── india_geography.pdf
│
├── chroma_db/
│
├── app.py
├── rag.py
├── requirements.txt
├── README.md
└── .env
```

> The exact file structure may vary depending on your implementation.

---

## ⚙️ How It Works

### 1. Document Loading

The project collects information about India from documents and web resources.

Example sources can include:

* India overview
* History of India
* Geography of India
* Culture
* Economy
* States and Union Territories

---

### 2. Text Splitting

Large documents are divided into smaller chunks using a text splitter.

This makes it easier for the retrieval system to find the most relevant information.

```python
from langchain_text_splitters import RecursiveCharacterTextSplitter

splitter = RecursiveCharacterTextSplitter(
    chunk_size=1000,
    chunk_overlap=200
)
```

---

### 3. Embedding Generation

Each text chunk is converted into a numerical vector using an embedding model.

These vectors represent the semantic meaning of the text.

---

### 4. Vector Database

The generated embeddings are stored in **ChromaDB**.

When a user asks a question, the system searches the vector database to find the most relevant chunks.

---

### 5. Retrieval

For example, if the user asks:

> "Who was the first Prime Minister of India?"

The retriever searches the knowledge base and finds relevant information about India's independence and early political history.

---

### 6. LLM Generation

The retrieved context is passed to the LLM along with the user's question.

The model then generates an answer using the retrieved information.

---

## 💬 Example Questions

You can ask questions such as:

```text
Who was the first Prime Minister of India?

When did India gain independence?

What is the capital of India?

How many states are there in India?

What are the major geographical regions of India?

Tell me about the history of India.

What are the major rivers of India?

What is India's economy based on?

Tell me about Indian culture and traditions.
```

---

## 🖥️ Running the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/India-RAG-Chatbot.git
```

### 2. Move into the Project Directory

```bash
cd India-RAG-Chatbot
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

---

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 5. Add API Key

Create a `.env` file:

```env
GROQ_API_KEY=your_api_key_here
```

**Important:** Never upload your API key to GitHub.

Add this to `.gitignore`:

```text
.env
.venv/
__pycache__/
chroma_db/
```

---

### 6. Run the Application

If you are using Streamlit:

```bash
streamlit run app.py
```

The application will then open in your browser.

---

## 📦 Requirements

Example dependencies:

```text
langchain
langchain-community
langchain-text-splitters
langchain-groq
chromadb
streamlit
pypdf
python-dotenv
sentence-transformers
```

Install them using:

```bash
pip install -r requirements.txt
```

---

## 🎯 Objectives

The main objectives of this project are:

* Understand the fundamentals of **RAG**
* Learn how document retrieval works
* Work with **vector databases**
* Generate and use embeddings
* Integrate an LLM with retrieved context
* Build a practical AI question-answering application
* Create an interactive interface using Streamlit

---

## 🔮 Future Improvements

Possible future improvements include:

* 🌐 Support for multiple languages
* 🎤 Voice-based question answering
* 📊 Interactive information dashboards
* 🖼️ Image-based information retrieval
* 📚 Addition of more Indian knowledge sources
* 🔎 Improved semantic search
* 💬 Conversation memory
* ⚡ Faster retrieval
* 📱 Mobile-friendly interface
* 📈 RAG evaluation and performance metrics

---

## ⚠️ Disclaimer

This project is created for **educational and demonstration purposes**.

The accuracy of generated answers depends on the quality of the underlying documents, retrieval process, embeddings, and language model.

---

## 👨‍💻 Author

**Sayan Mete**

This project was created as a practical implementation of **Retrieval-Augmented Generation (RAG)** using Python, LangChain, ChromaDB, and an LLM.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub!

---

## 📜 License

This project is available for educational and personal use.
