An AI-powered mentor that provides startup advice in the persona of Paul Graham.

This project implements a **Retrieval-Augmented Generation (RAG)** system designed to act as a "Digital Twin" of Y Combinator co-founder Paul Graham. By ingesting his essays and lecture transcripts, this tool offers instant, tactical, and contrarian advice to founders, democratizing access to elite-level mentorship.

---

## Repository Structure

* **`Startup_Mentor_RAG.ipynb`**: The core Jupyter Notebook containing the data ingestion pipeline, RAG logic, prompt engineering, and Gradio application code.
* **`Data.zip`**: Contains the knowledge base:
* Scraped essays from `paulgraham.com`.


* Transcripts from the "How to Start a Startup" YouTube lecture series.


* The pre-computed FAISS vector store database.


* **`The YC Startup Mentor.pdf`**: Project presentation slide deck detailing the business use case, architecture, and evaluation metrics.
* **`Live QnA Demo...mov`**: A video demonstration of the app in action, showcasing real-time interaction with the Digital Twin.

---

## Problem & Solution

**The Problem:** High-quality startup advice is buried in thousands of essays and hours of video. Founders often feel isolated and lack access to elite mentorship (less than 2% get into YC), while standard search engines yield generic "SEO fluff" .

**The Solution:** An AI Digital Twin that:

1. **Ingests** Paul Graham's specific worldview.
2. **Retrieves** relevant context using semantic search.
3. 
**Generates** answers in a specific persona (direct, slightly contrarian, authoritative) rather than a generic AI assistant tone.



---

## Technical Architecture

This project utilizes a RAG pipeline to ground LLM responses in factual data.

* 
**Ingestion:** HTML parsing (BeautifulSoup) of essays and transcript downloads.


* 
**Chunking:** Recursive Character Text Splitting (Chunk size: 2000) to preserve the logical flow of dense arguments.


* 
**Embeddings:** `sentence-transformers/all-mpnet-base-v2` (HuggingFace) for high semantic accuracy (768 dimensions).


* 
**Vector Store:** FAISS (Facebook AI Similarity Search) for sub-millisecond local retrieval.


* 
**LLM:** Gemini Pro.


* 
**User Interface:** Gradio Chat Interface.



---


## Usage

1. Unzip `Data.zip`.
2. Install requirements (e.g., `langchain`, `faiss-cpu`, `gradio`, `google-generativeai`).
3. Add your Gemini API Key.
4. Run `Startup_Mentor_RAG.ipynb` to launch the local Gradio server.
