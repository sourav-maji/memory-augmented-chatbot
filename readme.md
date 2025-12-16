# 🧠 Memory-Augmented AI Chatbot (mem0 + Qdrant + OpenAI)

A **persistent-memory AI chatbot** that remembers past conversations using **vector search**, powered by **mem0**, **Qdrant**, and **OpenAI**.

This project demonstrates how to build **ChatGPT-style long-term memory** using embeddings, semantic retrieval, and contextual prompting.

---

## 🚀 Features

- 🔁 Long-term conversational memory
- 🔍 Semantic memory retrieval with Qdrant
- 🧠 Context-aware responses using past interactions
- ⚡ Efficient embeddings (`text-embedding-3-small`)
- 💬 Interactive CLI chat loop
- 🧩 Clean, modular architecture
- 🏗️ Production-ready memory pipeline

---

## 🧱 Tech Stack

- **Python 3.9+**
- **OpenAI API**
- **mem0**
- **Qdrant (Vector Database)**
- **python-dotenv**
- **Docker (optional)**

---

## 📂 Project Structure

```bash
memory-ai-chat/
├── chat.py                # Main chat loop with memory
├── requirements.txt
├── .env                   # API keys (ignored)
├── README.md
└── docker-compose.yml     # Qdrant (optional)

```
## 🧠 Architecture

```nermaid
flowchart LR
    User --> Chat
    Chat -->|Query| MemorySearch
    MemorySearch --> Qdrant
    Qdrant --> MemorySearch
    MemorySearch -->|Relevant Memories| LLM
    LLM --> Response
    Response --> MemoryStore
    MemoryStore --> Qdrant
````
## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/sourav-maji/memory-augmented-chatbot.git

cd memory-ai-chat

```
### 2️⃣ Create Virtual Environment

```
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies
```
pip install --upgrade pip
pip install -r requirements.txt
```
### 4️⃣ Start Qdrant
```
docker compose up -d 
```

Qdrant dashboard:
```
http://localhost:6333/dashboard
```

### 5️⃣ Configure Environment Variables
```
OPENAI_API_KEY=your_openai_api_key
```
## ▶️ Run the Chatbot
```
python chat.py
```
### Example
```
👉 Enter your query: My name is Sourav
🤖 AI: Nice to meet you, Sourav!

👉 Enter your query: What is my name?
🤖 AI: Your name is Sourav.
```
The chatbot remembers users across conversations.

## 🧠 Memory Strategy
🧠 Memory Strategy
- Uses semantic similarity search
- Stores meaningful user–assistant interactions
- Prevents memory duplication
- Scales across multiple users using user_id

## 📌 Why mem0?
- Built-in memory extraction
- Vector-based memory storage
- Easy integration with OpenAI & Qdrant
- Designed specifically for LLM memory use cases