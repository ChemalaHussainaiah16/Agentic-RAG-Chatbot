
# 📄 Agentic RAG Chatbot

An interactive document-based Q&A system powered by LangChain agents, Azure OpenAI embeddings, FAISS vector store, and a clean Streamlit interface.

---

## 🚀 Features

- ✅ Upload and parse files (PDF, DOCX, PPTX, CSV, TXT, MD)
- ✅ Extract text using `IngestionAgent`
- ✅ Embed text and perform vector search using `RetrievalAgent`
- ✅ Generate contextual answers via `LLMResponseAgent` using Azure OpenAI
- ✅ Modular design using MCP (Model Context Protocol) for agent communication
- ✅ Streamlit-based UI with live chat history and collapsible context

---

## 🧠 Tech Stack

| Tool | Purpose |
|------|---------|
| **LangChain** | Agent framework and vector store interface |
| **Azure OpenAI** | Embeddings & GPT-4 LLM |
| **FAISS** | Vector similarity search |
| **Streamlit** | UI for document upload and chat |
| **Python** | Core development |
| **Pydantic** | Data validation for agents |

---

## 📂 Project Structure

```
.
├── app.py                        # Streamlit UI
├── agents/
│   ├── ingestion_agent.py        # Handles parsing uploaded files
│   ├── retrieval_agent.py        # Embeds text & retrieves relevant chunks
│   └── llm_response_agent.py     # Calls OpenAI with context & query
├── assets/                       # Icons, diagrams, and demo screenshots
│   ├── demo_upload_ui.png        # Snapshot of file upload section
│   ├── demo_question_input.png   # Snapshot of question input UI
│   ├── demo_source_context.png   # Snapshot showing retrieved context
│   ├── demo_answer_display.png   # Snapshot showing LLM response
│   └── architecture.png          # Project architecture diagram
├── .env                          # Azure API keys and endpoints
├── requirements.txt              # Required Python packages
└── README.md                     # Project overview and instructions

```

---

## ⚙️ How It Works

1. **Upload File** → Parses and sends text via `IngestionAgent`
2. **Retrieve Chunks** → Embeds and retrieves with `RetrievalAgent`
3. **Generate Answer** → Uses GPT via `LLMResponseAgent`
4. **Display** → Shows answer with source context

Agents communicate using **MCP messages** like:
```json
{
  "type": "RETRIEVAL_RESULT",
  "sender": "RetrievalAgent",
  "receiver": "LLMResponseAgent",
  "trace_id": "rag-457",
  "payload": {
    "retrieved_context": [...],
    "query": "What KPIs were tracked in Q1?"
  }
}
```

---

## 🔐 .env Configuration

```env
EMBEDDING_AZURE_OPENAI_API_KEY=your_api_key
EMBEDDING_AZURE_OPENAI_ENDPOINT=https://your-endpoint.openai.azure.com/
OPENAI_API_VERSION=2023-05-15
EMBEDDING_AZURE_OPENAI_DEPLOYMENT_NAME=your-embedding-deployment
CHAT_AZURE_OPENAI_DEPLOYMENT_NAME=your-chat-deployment
```

---

## ▶️ Run Locally

1. **Clone the repo**
```bash
git clone https://github.com/yourusername/agentic-rag-chatbot.git
cd agentic-rag-chatbot
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Add your `.env` file**

4. **Run the app**
```bash
streamlit run app.py
```

---

## Demo snaps
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/160c2a46079a3f39bc04275840e91d96cfa8910f/Photo1%20(1).png)
![image alt]()
![image alt]()
![image alt]()
![image alt]()

## 🙋‍♂️ Author

**[Chemala Hussainaiah]**  
Final year B.Tech student at Marwadi University  
🔗 [LinkedIn](www.linkedin.com/in/chemala-hussainaiah-95bab7359)  
📧 chemalahussainaiah@gmail.com

---

## ⭐ Future Improvements

- ✅ PDF chunk highlighting in output
- ✅ Add Chat History persistence
- 🟡 Support multiple document queries
- 🟡 Add authentication and logging

---

## 🧠 Inspired by

- LangChain + OpenAI agent architecture
- Azure AI Studio + FAISS document RAG demos

---

## 📝 License

This project is under the MIT License.
