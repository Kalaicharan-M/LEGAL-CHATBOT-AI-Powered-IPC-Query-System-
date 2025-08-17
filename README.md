# 🏥 Intelligent Medical Q&A Chatbot (RAG + LangChain)



An AI-powered chatbot that answers **medical questions** using **Retrieval-Augmented Generation (RAG)** with **LangChain**, **FAISS semantic search**, and integrates with both **LM Studio (local)** and **OpenAI (cloud)**. It retrieves information from trusted medical sources like **WHO, NHS, CDC, MedlinePlus, and Mayo Clinic** to provide reliable and context-aware responses.


---

## 🚀 Features

- 🔍 **FAISS Vector Search** – Retrieves relevant medical information from indexed sources  
- 🤖 **Hybrid LLM Integration** – Works with LM Studio locally or OpenAI in the cloud  
- 🛠️ **Flask Backend** – Lightweight API for query handling  
- 🎨 **Frontend UI** – Simple HTML/CSS interface for asking medical questions
---

## 🛠️ Installation

### 1. Extract Project Files
```
bashunzip Medical-Chatbot-RAG.zip
cd Medical-Chatbot-RAG
```

### 2. Create Virtual Environment
```bash
python -m venv venv
```

### 3. Activate Virtual Environment
```bash
# Windows
.\venv\Scripts\activate
```

### 4. Install Dependencies
```bash
pip install -r requirements.txt
```
Or manually:
```bash
pip install langchain langchain-community pypdfloader langchain-text-splitters sentence-transformers faiss-cpu flask openai
```

### 5. Initialize Vector Store
```bash
python back.py
```
This creates the `ipc_index/` folder containing the FAISS vector store.

---

## ⚙️ Configure LLM (Choose One)

**Option A: LM Studio (Local)**  
- Download and run LM Studio  
- Load your preferred LLM model  
- Start the local inference server (default: `http://127.0.0.1:1234`)  

**Option B: OpenAI (Cloud)**  
- Replace the OpenAI client code in `app.py` with:
```python
client = OpenAI(api_key="your-openai-key")
```

---

## ▶️ Run the Application
```bash
python app.py
```
Then open [http://localhost:5000](http://localhost:5000) in your browser.

---

## 💬 Usage
-Enter a medical question (e.g., "What are the early symptoms of diabetes?")
-The system retrieves relevant documents and generates a context-based answer
- Example output:  
  *"Common early symptoms of diabetes include frequent urination, increased thirst, and fatigue (WHO, NHS)."*

---

## 📁 Project Structure
```
Medical-Chatbot-RAG/
├── app.py              # Flask application
├── back.py             # FAISS vector store initialization
├── templates/
│   ├── index.html      # Homepage UI
│   └── answer.html     # Answer display UI
├── medical_index/      # FAISS vector store (auto-generated)
├── project_images/     # Screenshots (homepage.png, answer.png)
├── requirements.txt    # Dependencies
└── README.md           # This file

```

---

## 🧩 Troubleshooting
- **FAISS Errors** – Use Python 3.8+ and compatible `faiss-cpu`  
- **LM Studio Issues** – Ensure local server is running at `http://127.0.0.1:1234`  
- **OpenAI Errors** – Check your API key and internet connection  

---

