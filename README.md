# 🧠 Legal Chatbot (IPC Query Assistant)

An AI-powered chatbot that answers legal questions about Indian Penal Code (IPC) sections using local or cloud-based LLMs (LM Studio or OpenAI) and semantic search via FAISS.

---

## 🚀 Features

- 🔍 **FAISS Vector Search** – Retrieves relevant IPC sections using embeddings  
- 🤖 **Hybrid LLM Integration** – Supports both LM Studio (local) and OpenAI (cloud)  
- 🛠️ **Flask Backend** – Robust API for query processing  
- 🎨 **Responsive UI** – Clean HTML/CSS frontend  

---

## 🛠️ Installation

### 1. Extract Project Files
```bash
unzip Legal-Chatbot-IPC.zip
cd Legal-Chatbot-IPC
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
- Enter your legal question (e.g., *"What is the IPC section for theft?"*)  
- Submit to receive an answer with relevant IPC sections  
- Example output:  
  *"Theft is punishable under IPC Section 378."*

---

## 📷 Screenshots

**Question Page**  
![Question Page](https://github.com/Kalaicharan-M/LEGAL-CHATBOT-AI-Powered-IPC-Query-System-/blob/main/project%20images/Screenshot%202025-08-09%20161623.png?raw=true)

**Answer Page**  
![Answer Page](https://github.com/Kalaicharan-M/LEGAL-CHATBOT-AI-Powered-IPC-Query-System-/blob/main/project%20images/Screenshot%202025-08-09%20161651.png?raw=true)

---

## 📁 Project Structure
```
Legal-Chatbot-IPC/
├── app.py              # Main Flask application
├── back.py             # FAISS vector store initialization
├── templates/
│   ├── index.html      # Homepage UI
│   └── sec.html        # Answer display UI
├── ipc_index/          # FAISS vector store (auto-generated)
├── requirements.txt    # Dependencies
└── README.md           # This file
```

---

## 🧩 Troubleshooting
- **FAISS Errors** – Use Python 3.8+ and compatible `faiss-cpu`  
- **LM Studio Issues** – Ensure local server is running at `http://127.0.0.1:1234`  
- **OpenAI Errors** – Check your API key and internet connection  

---

## 🛠️ Customization
- **Modify Legal Corpus** – Replace or update PDFs processed by `back.py`  
- **Switch LLMs** – Adjust the model name in LM Studio or OpenAI client  
