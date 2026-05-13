# Hybrid-ML-LLM-Conversational-System

🚀 Overview

The Enterprise AI Knowledge Assistant is a production-oriented conversational AI system designed to deliver accurate, explainable, and reliable responses in enterprise environments. The project uses a hybrid Machine Learning and Retrieval-Augmented Generation (RAG) architecture, combining traditional ML models with modern vector-based information retrieval.

Unlike LLM-only chatbots, this system emphasizes confidence-aware intent routing, document-grounded responses, and safe fallback handling, reflecting real-world ML engineering best practices.

🧠 Key Features

✅ Hybrid ML–RAG Architecture

✅ Confidence-Aware Intent Classification

✅ Deterministic Handling of FAQs & Policies

✅ Vector-Based Knowledge Retrieval (RAG)

✅ Safe Fallback for Low-Confidence Queries

✅ Production-Oriented Project Structure

✅ LLM-Agnostic (Pluggable LLM Layer)

🏗️ System Architecture
User Query
   ↓
FastAPI Endpoint
   ↓
Intent Classifier (Traditional ML)
   ↓
Confidence Threshold Check
   ├── FAQ / Policy → Structured Response
   ├── Knowledge   → RAG Pipeline (Vector Search)
   └── Low Confidence → Safe Fallback
   ↓
Final Response

🧩 Why Hybrid ML + RAG?
Challenge	LLM-Only	Hybrid Approach
Hallucinations	❌ High	✅ Reduced
Latency	❌ Higher	✅ Optimized
Cost Control	❌ Expensive	✅ Efficient
Explainability	❌ Low	✅ High
Enterprise Safety	❌ Risky	✅ Reliable
📂 Project Structure
enterprise-ai-knowledge-assistant/
├── api/
│   ├── main.py
│   └── routes.py
│
├── intent/
│   ├── training/
│   │   └── train_intent.py
│   ├── inference/
│   │   └── intent_router.py
│   └── model_registry/
│       └── intent_model_v1.pkl
│
├── rag/
│   ├── ingestion/
│   ├── chunking/
│   ├── vector_store/
│   └── retrieval/
│
├── data/
│   ├── intents.csv
│   └── knowledge_docs/
│
├── monitoring/
│   └── metrics.py
│
├── config/
├── tests/
├── requirements.txt
└── README.md

🧠 Intent Classification

The system uses a traditional ML pipeline for intent detection:

TF-IDF Vectorization

Logistic Regression Classifier

Probability-Based Confidence Scoring

Each intent has a configurable confidence threshold to decide whether the prediction is accepted or routed to fallback handling.

Example output:

{
  "intent": "knowledge",
  "confidence": 0.82,
  "accepted": true,
  "threshold": 0.65
}

📚 Retrieval-Augmented Generation (RAG)

For knowledge-based queries:

Enterprise documents are chunked

Converted into embeddings

Stored in a vector database (FAISS)

Relevant chunks are retrieved at query time

Responses are generated strictly from retrieved context

This ensures grounded, non-hallucinated answers.

🛠️ Tech Stack

Python

Scikit-learn – Intent classification

Sentence Transformers – Text embeddings

FAISS – Vector similarity search

FastAPI – API layer

SQL / File-based Storage – Metadata & logs

⚙️ Installation
git clone https://github.com/Hirosh07/Hybrid-ML-LLM-Conversational-System.git
cd Hybrid-ML-LLM-Conversational-system
pip install -r requirements.txt

▶️ Running the Intent Classifier
cd intent/inference
python intent_router.py


Type queries and observe confidence-based routing decisions.

🧪 Example Use Cases

Internal enterprise knowledge assistant

HR policy & FAQ automation

IT support query routing

Safe conversational AI systems

LLM cost-optimized chat platforms

📈 Production Considerations

Model versioning & retraining

Confidence threshold tuning

Logging & observability

Pluggable LLM integration

Dockerized deployment (future)

💼 ML Engineer Talking Points

Confidence-aware intent routing

ML vs LLM responsibility split

Cost and latency optimization

Hallucination prevention using RAG

Production-ready ML architecture

🔮 Future Enhancements

Online feature store

Model drift detection

Async API with caching

LLM integration (OpenAI / Azure / Local)

Monitoring dashboards

📄 License

MIT License

👤 Author

Anavi Gupta  

AI Student | AI/ML Enthusiastic
