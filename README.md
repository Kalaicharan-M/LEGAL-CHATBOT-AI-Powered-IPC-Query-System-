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
```bash
unzip Medical-Chatbot-RAG.zip
cd Medical-Chatbot-RAG
2. Create Virtual Environment
bash
Copy
Edit
python -m venv venv
3. Activate Virtual Environment
bash
Copy
Edit
# Windows
.\venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
4. Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
Or manually:

bash
Copy
Edit
pip install langchain langchain-community faiss-cpu sentence-transformers unstructured requests beautifulsoup4 flask openai
5. Initialize Vector Store
bash
Copy
Edit
python back.py
This creates the medical_index/ folder containing the FAISS vector store.

⚙️ Configure LLM (Choose One)
🔹 Option A: LM Studio (Local)
Download and run LM Studio

Load your preferred LLM model (e.g., LLaMA-3 8B Instruct)

Start the local inference server (default: http://127.0.0.1:1234)

python
Copy
Edit
from langchain_community.llms import OpenAI
llm = OpenAI(model="local-model", base_url="http://127.0.0.1:1234", temperature=0)
🔹 Option B: OpenAI (Cloud)
Replace in app.py:

python
Copy
Edit
from langchain_openai import ChatOpenAI
llm = ChatOpenAI(model="gpt-4o-mini", temperature=0)
Set your API key:

bash
Copy
Edit
# macOS/Linux
export OPENAI_API_KEY="your_api_key_here"

# Windows PowerShell
setx OPENAI_API_KEY "your_api_key_here"
▶️ Run the Application
bash
Copy
Edit
python app.py
Then open: http://localhost:5000 in your browser.

💬 Usage
Enter a medical question (e.g., "What are the early symptoms of diabetes?")

The system retrieves relevant documents and generates a context-based answer

Example Output:
"Common early symptoms of diabetes include frequent urination, increased thirst, and fatigue (WHO, NHS)."

📷 Screenshots
Homepage

Answer Page

📁 Project Structure
graphql
Copy
Edit
Medical-Chatbot-RAG/
├── app.py              # Flask application
├── back.py             # FAISS vector store initialization
├── templates/
│   ├── index.html      # Homepage UI
│   └── answer.html     # Answer display UI
├── medical_index/      # FAISS vector store (auto-generated)
├── requirements.txt    # Dependencies
└── README.md           # This file
🧩 Troubleshooting
FAISS Errors → Use Python 3.8+ with compatible faiss-cpu

LM Studio Issues → Ensure local inference server is running at http://127.0.0.1:1234

OpenAI Errors → Verify API key and internet connection

🌟 Future Work
🎤 Voice Support – Add speech-to-text & text-to-speech

🌍 Multilingual Queries – Support multiple languages

📊 ICD-11/SNOMED Mapping – Map symptoms to medical codes

📰 Real-Time Health Updates – Fetch live health news

🧠 Advanced Symptom Checker – Interactive diagnostic assistance

📌 Example Query
User: "What are the signs of a heart attack?"
Bot: "Signs include chest pain or pressure, shortness of breath, nausea, and lightheadedness (WHO, Mayo Clinic, NHS)."
