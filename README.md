# Legal Chatbot (IPC Query Assistant)  

An AI-powered chatbot that answers legal questions about Indian Penal Code (IPC) sections using local/cloud LLMs (LM Studio or OpenAI) and semantic search with FAISS.  

## Features  
- **FAISS Vector Search**: Retrieve relevant IPC sections from embeddings  
- **Hybrid LLM Integration**: Use either local LM Studio or OpenAI for responses  
- **Flask Backend**: Robust API for query processing  
- **Responsive UI**: Clean HTML/CSS frontend  

## Installation  

##1. Extract Project Files

unzip Legal-Chatbot-IPC.zip  
cd Legal-Chatbot-IPC

##2.Create Virtual Environment

python -m venv venv  

##3.Activate Virtual Environment

.\venv\Scripts\activate  

##4.Install Dependencies

pip install langchain langchain-community pypdfloader langchain-text-splitters sentence-transformers faiss-cpu flask openai  

##5.Initialize Vector Store

python back.py  

This will create the ipc_index folder containing the FAISS vector store.

##6.Configure LLM (Choose One Option)

Option A: LM Studio (Local)

Download and run LM Studio

Load your preferred LLM model in LM Studio

Start the local inference server (default: http://127.0.0.1:1234)

Option B: OpenAI (Cloud)

Replace the OpenAI client code in app.py with:
client = OpenAI(api_key="your-openai-key")  # Add your actual API key  

##7.Run the Application

python app.py  

##8.Access the Chatbot

Open http://localhost:5000 in your browser.

##Usage

1.Enter your legal question (e.g., "What is the IPC section for theft?")

2.Submit to receive an answer with relevant IPC sections

3.Example output: "Theft is punishable under IPC Section 378."

##Project Structure

Legal-Chatbot-IPC/  
├── app.py                # Main Flask application  
├── back.py               # FAISS vector store initialization  
├── templates/  
│   ├── index.html        # Homepage UI  
│   └── sec.html          # Answer display UI  
├── ipc_index/            # FAISS vector store (auto-generated)  
├── requirements.txt      # Dependencies (auto-generated via pip freeze)  
└── README.md             # This file  


##Troubleshooting

1.FAISS Errors: Ensure you're using compatible Python (3.8+) and faiss-cpu

2.LM Studio Issues: Verify the local server is running at http://127.0.0.1:1234

3.OpenAI Errors: Check your API key and internet connection

##Customization

1.To modify the legal corpus: Update the PDFs processed by back.py

2.To change the LLM: Adjust the model name in either LM Studio or OpenAI client

##Screenshots
    Query Interface	                             Response Example
https://screenshots/query.png          	https://screenshots/response.png

```bash

