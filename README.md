📘 Semantic Book Recommendation System
<img width="3168" height="1775" alt="image" src="https://github.com/user-attachments/assets/0166b6f0-4e90-4cdc-a9f9-a3b425ebaa8e" />
<img width="3168" height="1775" alt="image" src="https://github.com/user-attachments/assets/0a64e343-f3e6-4f46-95ab-e53034334cf7" />


🧠 Overview
The Semantic Book Recommendation System is an LLM-powered book recommender that leverages natural language understanding, emotion analysis, and semantic embeddings to suggest books matching user intent, tone, and genre.
It builds an enriched dataset from raw book metadata, categorizes content using zero-shot classification, extracts emotional embeddings from text, and enables contextual recommendations through a Gradio-based dashboard.

⚙️ Technical Workflow
- Loaded 7k+ book metadata using kagglehub, cleaned missing fields, and derived features like age_of_book and words_in_description.
- Created a combined tagged_description field (isbn13 + description) and saved text data for embedding.
- Used LangChain’s TextLoader and CharacterTextSplitter to prepare documents for vectorization.
- Generated semantic embeddings with sentence-transformers/all-MiniLM-L6-v2 and stored them in a Chroma vector database.
- Simplified complex genres into broader categories and filled missing ones using zero-shot classification (facebook/bart-large-mnli).
- Extracted emotional scores (joy, fear, anger, sadness, surprise, etc.) using j-hartmann/emotion-english-distilroberta-base.
- Combined all results into books_with_emotions.csv for the final enriched dataset.
- Built a semantic similarity-based recommendation engine using LangChain + Chroma for context-aware book retrieval.
- Filtered and ranked recommendations by user-selected category and tone.
- Deployed a Gradio-based dashboard to query, visualize, and interact with book recommendations in real time.

🧩 System Components
| Layer           | Technology                              | Purpose                                                   |
| --------------- | --------------------------------------- | --------------------------------------------------------- |
| Data Ingestion  | `kagglehub`, `pandas`, `numpy`          | Load and preprocess book dataset                          |
| Visualization   | `seaborn`, `matplotlib`                 | Heatmaps and correlation matrices                         |
| NLP Processing  | `LangChain`, `HuggingFace Transformers` | Text embedding, zero-shot classification, emotion tagging |
| Vector Database | `Chroma`                                | Efficient similarity search                               |
| Interface       | `Gradio`                                | Interactive book recommendation dashboard                 |
| Configuration   | `dotenv`                                | Secure environment management                             |

🧭 Example Query
- “A Book Describing Inner Peace”
- Tone: Happy
- Category: Nonfiction
📚 Output: 16 semantically matched book recommendations ranked by joy emotion and relevance.

🚀 Highlights
- Semantic search via transformer embeddings
- Emotion-aware ranking mechanism
- Auto-category enrichment using zero-shot NLP
- Clean, interactive Gradio interface
- Fully reproducible pipeline from raw data → recommendations
