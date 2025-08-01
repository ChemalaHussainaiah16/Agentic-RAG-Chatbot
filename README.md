
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
## Architecture
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/446b164d6f491bacf6cf191406f08f858a9c76f4/Architecture.png)

## Demo snaps
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/160c2a46079a3f39bc04275840e91d96cfa8910f/Photo1%20(1).png)
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/ccda2dcc79514fde33c7270a4109478fa1a29554/Photo1%20(2).png)
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/2e5f65d7dbf61eec7fbcbf8de489e40714742fbc/Photo1%20(3).png)
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/4d729e19eac602932a536bd546b4ae4119987ce9/Photo1%20(4).png)
![image alt](https://github.com/ChemalaHussainaiah16/Agentic-RAG-Chatbot/blob/cad26d1b03ed7dae990b235e03f4e83b31270257/Photo1%20(5).png)

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
