# **Enhancing Search Engine Relevance for Video Subtitles (Cloning Shazam)**  

## **Background**  
In the fast-evolving landscape of digital content, effective search engines play a pivotal role in connecting users with relevant information. For platforms like Google, providing a seamless and accurate search experience is paramount. This project focuses on improving search relevance for video subtitles, enhancing the accessibility of video content.  

## **Objective**  
Develop an **advanced search engine algorithm** that efficiently retrieves subtitles based on user queries, emphasizing subtitle content. The primary goal is to leverage **Natural Language Processing (NLP)** and **Machine Learning (ML)** techniques to enhance the relevance and accuracy of search results.  

---

## **Keyword-Based vs. Semantic Search Engines**  

### **Keyword-Based Search Engine**  
- Relies on **exact keyword matches** between user queries and indexed documents.  
- Works well for **precise word occurrences** but lacks contextual understanding.  

### **Semantic Search Engine**  
- Goes beyond keyword matching to understand **meaning and context**.  
- Uses **embeddings** and similarity metrics for more relevant results.  

### **Comparison**  
| Feature | Keyword-Based Search | Semantic Search |
|---------|----------------------|----------------|
| Matching | Exact words | Context-aware |
| Understanding | Limited | Deeper meaning |
| Accuracy | Basic | Intelligent retrieval |

---

## **Core Logic: How It Works**  

### **Step 1: Preprocessing of Data**  
1. **Sampling** – If resources are limited, take a **random 10%–30%** sample.  
2. **Cleaning** – Remove **timestamps and metadata** from subtitles.  
3. **Vectorization** – Convert cleaned subtitle text into **numerical representations**.  
4. **Query Vectorization** – Encode the **user query** in the same format.  

### **Step 2: Cosine Similarity Calculation**  
- Compute **cosine similarity** between subtitle vectors and the query vector.  
- Return **top-matching** subtitle documents.  

---

## **Dataset Information**  
- **Format**: `.db` (Database file).  
- **Process**:  
  - Extract and clean subtitle data.  
  - Decode relevant text while **removing unnecessary characters**.  

---

## **Step-by-Step Implementation**  

### **Part 1: Ingesting Documents**  
1. Load **subtitle data** from `.db` format.  
2. Extract and **clean** subtitle text.  
3. Take a **30% sample** if needed (for performance).  
4. **Experiment with different vectorization techniques**:  
   - **Bag of Words (BoW)** / **TF-IDF** → Sparse vectors (keyword-based).  
   - **BERT-based SentenceTransformers** → Dense embeddings (semantic search).  

#### **Document Chunking (Must Implement)**  
- **Problem**: Large subtitle documents may **lose context** when embedded as a whole.  
- **Solution**:  
  - **Chunking strategy** → Break documents into smaller segments.  
  - **Overlapping windows** → Ensure **context continuity** in adjacent chunks.  
  - **Storage** → Store embeddings efficiently in **ChromaDB**.  

---

### **Part 2: Retrieving Documents**  
1. Accept **user search query** in **audio format**.  
2. Transcribe audio to text using **AssemblyAI**.  
3. Preprocess the **transcribed text** (clean, format).  
4. Convert the query into **embedding format** (same as subtitle embeddings).  
5. Compute **cosine similarity** between the **query and stored embeddings**.  
6. Retrieve the **most relevant** subtitle documents.  
7. Display **search results** dynamically.  

---

## **Implementation Stack**  

| Component | Technology |  
|-----------|-------------|  
| **Data Processing** | Python (pandas, numpy) |  
| **Vectorization** | SentenceTransformers, TF-IDF |  
| **Embedding Storage** | ChromaDB |  
| **Audio Transcription** | AssemblyAI |  
| **Web App Interface** | Streamlit |  

---

## **Project Benefits**  
✅ Improves **subtitle search relevance**.  
✅ Enhances **video accessibility** for users.  
✅ Leverages **NLP & ML** for smarter search results.  

---

## **Project Status**  
- **Stars**: ⭐ 0  
- **Watchers**: 👀 1  
- **Forks**: 🍴 0  
- **Languages**:  
  - Jupyter Notebook **99.7%**  
  - Python **0.3%**  
