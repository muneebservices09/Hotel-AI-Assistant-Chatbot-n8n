# 🤖 Hotel-AI-Assistant-Chatbot

![n8n](https://img.shields.io/badge/Workflow-n8n-FF6C37?style=flat&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/AI-GPT--4o-412991?style=flat&logo=openai&logoColor=white)
![Pinecone](https://img.shields.io/badge/Database-Pinecone-262730?style=flat&logo=pinecone&logoColor=white)
![Google Drive](https://img.shields.io/badge/Source-Google_Drive-4285F4?style=flat&logo=googledrive&logoColor=white)
![RAG](https://img.shields.io/badge/Architecture-RAG-blue?style=flat)

---

## 🚀 The Solution: Neural Knowledge Retrieval
Generic AI models often lack the specific, up-to-date knowledge required for specialized hospitality support. This project is a **Production-Grade RAG (Retrieval-Augmented Generation) AI Agent** designed to act as an expert concierge for the hotel industry. 

By bridging **n8n orchestration** with **Pinecone's vector memory**, the chatbot doesn't just "guess" answers—it retrieves exact facts from the hotel's private knowledge base (PDFs, Policies, Amenities) before generating a response. This ensures 100% factual accuracy and context-aware guest support. 🏨🤖✨

---

## 📊 Business Impact & Engineering Outcomes
This RAG-based approach transforms standard customer service into a high-precision intelligence engine:

*   **⚡ Elimination of Hallucinations:** By forcing the AI to "read" the hotel's documents before speaking, the risk of incorrect information is virtually eliminated.
*   **📚 Unlimited Knowledge Scaling:** The system can ingest thousands of pages of hotel data (menu items, floor plans, local guides) without overwhelming the AI's prompt limit.
*   **⏱️ 24/7 Expert Support:** Provides guests with instant, detailed answers to complex questions like *"What are the specific spa policies for children?"* or *"Can I see the technical specifications of the conference room?"*
*   **🛠️ Automated Brain Updates:** New documents uploaded to Google Drive are automatically processed and "learned" by the AI via the ingestion pipeline.

---

## ✅ Problems Solved
- **🛑 Outdated AI Knowledge:** Standard LLMs have a training cutoff. This system uses "Live" data from your own documents. 📂
- **🛑 Generic Responses:** Replaces "I think the hotel has a pool" with "The rooftop pool is open from 6 AM to 10 PM and is located on the 42nd floor." 🎯
- **🛑 Manual Data Entry:** Automatically splits and embeds large documents, removing the need for humans to format text for the AI. 🔄
- **🛑 Search Friction:** Guests don't have to read long PDFs; they simply ask the AI, which finds the exact paragraph for them instantly. 💬

---

## 🖼️ System Architecture

### 1. Chat & Semantic Query Workflow
The "Front-end" logic that handles user queries, performs vector lookups, and synthesizes the final response.
<div align="center">
  <img src="images/RAG%20AI%20Agent%201.png.jpeg" width="100%" alt="n8n Chat Workflow Architecture" style="border-radius:10px; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);"/>
</div>

### 2. Autonomous Data Ingestion (The "Brain" Builder)
The backend pipeline that downloads, chunks, embeds, and stores private documents into the vector database.
<div align="center">
  <img src="images/RAG%20AI%20Agent%202.png.jpeg" width="100%" alt="n8n Data Ingestion Architecture" style="border-radius:10px; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);"/>
</div>

---

## 🧠 Core Technical Pillars

### 1. 📂 Automated Document Ingress (Google Drive)
The system monitors a secure **Google Drive** folder. When new hotel manuals or policy docs are added, the workflow downloads them and prepares them for neural processing, acting as a bridge between static files and active AI memory.

### 2. ✂️ Recursive Semantic Chunking
To ensure the AI retrieves the most relevant information, I utilized a **Recursive Character Text Splitter**. This breaks down large documents into smaller, semantically coherent "chunks," ensuring that the vector search returns precise context rather than irrelevant noise.

### 3. 🧠 Vector Embedding & Storage (OpenAI + Pinecone)
- **OpenAI Embeddings:** Every text chunk is converted into a 1536-dimension numerical vector using `text-embedding-ada-002`.
- **Pinecone DB:** These vectors are stored in a high-speed index. This allows the system to perform **Semantic Search**, finding information based on *meaning* rather than just keywords. 🔍📐

### 4. 🎙️ Context-Aware Reasoning (GPT-4o)
When a guest asks a question, the workflow performs a "similarity search" in Pinecone. The most relevant chunks are fed into **GPT-4o** as "System Context," instructing the AI to *only* answer using the provided facts. This creates a highly focused and reliable hotel assistant. 🧠⚡

---

## 🛠️ Technical Stack
| Layer | Technology |
| :--- | :--- |
| **🔄 Automation** | **n8n** (State Management & Orchestration) |
| **🧠 AI Brain** | **OpenAI GPT-4o** (Reasoning & Context Synthesis) |
| **💾 Vector Store** | **Pinecone** (Semantic Long-term Memory) |
| **🔎 Embedding** | **OpenAI text-embedding-ada-002** |
| **📂 Data Source** | **Google Drive API** (Unstructured Knowledge Base) |
| **📜 Scripting** | **Recursive Character Text Splitter** (Data Optimization) |

---

## ✍️ Author
**Muneeb Ali Khan**
- **GitHub:** [@Muneeb20019](https://github.com/Muneeb20019)
- **LinkedIn:** [Muneeb Ali Khan](https://www.linkedin.com/in/muneeb-ali-khan-2a1675365)

---

## 📜 License
This project is licensed under the MIT License.
