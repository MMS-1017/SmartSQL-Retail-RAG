# 🧠 SmartSQL Retail AI Assistant — RAG-Powered NL2SQL Engine

An **LLM-powered system** that converts natural language queries into SQL to analyze **retail inventory, pricing, and discount-based revenue**. It leverages a **retrieval-augmented few-shot (RAG) approach** to dynamically select relevant examples for accurate SQL generation.

---

## 🚀 Features

- **Natural Language to SQL (NL2SQL)**: Ask questions in plain English, get precise MySQL queries executed under the hood.
- **RAG-powered Few-Shot Learning**: Dynamically selects the most relevant examples from a vector store to guide the LLM.
- **Discount-Aware Revenue Queries**: Handles joins and discount calculations using SQL `COALESCE` and aggregation.
- **Real-Time Interactive UI**: Built with Streamlit for instant query-answer feedback.
- **Prompt Constraints**: Ensures syntactically correct SQL, limits columns, uses `LIMIT` for efficiency, and handles date functions like `CURDATE()`.

---

## 🧩 Tech Stack

- **Programming Language:** Python  
- **LLM / AI Model:** Google PaLM  
- **Framework:** LangChain  
- **Database:** MySQL  
- **Vector Database:** ChromaDB  
- **Embeddings:** HuggingFace (sentence-transformers)  
- **Frontend / UI:** Streamlit  
- **Environment Management:** dotenv  

---

## 📦 Installation

1. **Clone the repository**
```bash
git clone https://github.com/your-username/smartsql-retail-rag.git
cd smartsql-retail-rag
```

2. **Create Python environment**
```bash
conda create -n smartsql python=3.10
conda activate smartsql
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set environment variables**  
Create a `.env` file:
```env
GOOGLE_API_KEY=your_google_api_key_here
```

---

## ▶️ Running the App

```bash
streamlit run app.py
```

Access the app in your browser:  
```
http://localhost:8501
```

---

## 💬 Example Queries

- How many t-shirts do we have left for Nike in XS size and white color?  
- Total inventory value for all S-size t-shirts?  
- If we sell all Levi’s t-shirts today, how much revenue will we generate (post-discount)?  
- Revenue generated from all large Nike t-shirts after discounts?  

---

## 📁 Project Structure

```
smartsql-retail-rag/
│
├── app.py                  # Streamlit UI
├── langchain_helper.py     # LLM + SQL chain + RAG logic
├── few_shots.py            # Few-shot example queries
├── requirements.txt        # Dependencies
├── .env                    # API keys (not pushed to GitHub)
└── README.md
```

---

## 🔥 How It Works

1. User types a question in natural language.  
2. The system selects the most relevant few-shot examples using **semantic similarity** (Chroma + embeddings).  
3. Google PaLM generates a **syntactically correct MySQL query**.  
4. Query executes on **MySQL database**.  
5. The system returns a **human-readable answer**, including discount-aware calculations if needed.

---

## 📊 Key Contributions

- Built a **domain-specific few-shot retrieval pipeline** for retail queries.  
- Implemented **discount-aware revenue calculations** with SQL aggregation and joins.  
- Created a **real-time interactive Streamlit interface**.  
- Designed **prompt engineering rules** to enforce SQL correctness and efficiency.

---

## ⭐ Future Improvements

- Real-time **video/streaming inventory updates**  
- CI/CD for automated deployment  
- Query caching and latency optimization  
- Adding **LangGraph agent workflow** for multi-step queries  

---

## 👨‍💻 Author

**Mohamed Mohsen**  
AI Engineer | GenAI Developer  

---
