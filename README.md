#LLM

```text

```
# 🤖 LLM & RAG Self-Course

A hands-on learning repository for understanding **Large Language Models (LLMs), LangChain concepts, embeddings, vector stores, retrieval, prompt engineering, and Retrieval-Augmented Generation (RAG)**.

This repository was created as a self-learning project to understand how modern LLM applications work **step by step**, starting from basic LLM interactions and gradually building toward RAG-based systems.

---

## 📚 What This Project Covers


---

# 🧠 Learning Roadmap

The project follows approximately this pipeline:

```text
                    LLM APPLICATIONS
                           │
                           ▼
                    ┌─────────────┐
                    │  Chat Model │
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │   Prompts   │
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │Output Parser│
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │   Documents │
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │Text Splitting│
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │  Embeddings │
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │ Vector Store│
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │  Retriever  │
                    └──────┬──────┘
                           │
                           ▼
                         RAG
```d
```

---

# 🚀 1. LLM Basics

The project starts with basic interaction with Large Language Models.

The objective is to understand:

- What an LLM is
- How prompts are sent to an LLM
- How responses are generated
- Difference between traditional models and chat models
- Basic LLM application structure

Example:

```text
User Input
     ↓
   Prompt
     ↓
    LLM
     ↓
 Response
```

---

# 💬 2. Chat Models

The `chatmodels/` directory contains experiments with chat-based LLMs.

Chat models work with structured messages such as:

```text
System Message
       +
User Message
       ↓
   Chat Model
       ↓
Assistant Response
```

This makes it possible to build conversational applications.

---

# 📝 3. Prompt Engineering

The `prompts/` directory focuses on creating and managing prompts.

A prompt controls how the LLM should process the input.

For example:

```text
You are a helpful machine learning tutor.

Explain the following concept in simple language:

{concept}
```

Prompt templates make it possible to reuse the same structure with different inputs.

---

# 🔎 4. Output Parsers

The `outputparser/` directory explores how LLM responses can be converted into structured formats.

Instead of simply receiving:

```text
"The answer is 42."
```

an output parser can help transform the model output into a structured representation.

For example:

```json
{
    "answer": 42
}
```

This becomes especially useful when building applications that need predictable outputs.

---

# 📄 5. Document Loaders

The repository includes different document loading approaches.

### PDF Loader

```text
pdf_loader.py
```

Used to load information from PDF documents.

### CSV Loader

```text
csv_loader.py
```

Used to process structured CSV data.

### Directory Loader

```text
directory_loader.py
```

Used to load multiple documents from a directory.

The general workflow is:

```text
Document
   ↓
Document Loader
   ↓
Document Objects
   ↓
Text Processing
```

---

# ✂️ 6. Text Splitting

Large documents cannot always be directly passed to an LLM.

Therefore, documents are divided into smaller pieces called **chunks**.

```text
Large Document
      ↓
 ┌───────────────┐
 │    Chunk 1    │
 ├───────────────┤
 │    Chunk 2    │
 ├───────────────┤
 │    Chunk 3    │
 ├───────────────┤
 │    Chunk 4    │
 └───────────────┘
```

The `textsplitter/` directory contains experiments with document chunking.

Important concepts include:

- Chunk size
- Chunk overlap
- Recursive splitting
- Maintaining contextual information

---

# 🧠 7. Embeddings

The `embeddings/` directory explores how text can be represented as numerical vectors.

For example:

```text
"Machine Learning"
        ↓
Embedding Model
        ↓
[0.12, -0.34, 0.87, ...]
```

Texts with similar meanings tend to have similar vector representations.

This allows semantic search.

---

# 🗄️ 8. Vector Stores

The `vectorstore/` directory explores storing and searching embeddings.

The basic idea is:

```text
Documents
    ↓
Embeddings
    ↓
Vector Store
    ↓
Similarity Search
```

When a user asks a question, the question is also converted into an embedding.

The system then searches for vectors that are closest to the query.

---

# 🔍 9. Retrievers

The `retrievers/` directory explores document retrieval.

A retriever receives a query:

```text
"What is deep learning?"
```

and searches the knowledge base for relevant information.

```text
User Query
    ↓
Query Embedding
    ↓
Similarity Search
    ↓
Relevant Documents
```

The retrieved documents can then be passed to an LLM.

---

# 🤖 10. Retrieval-Augmented Generation (RAG)

The concepts learned throughout the repository eventually come together in **RAG**.

RAG combines:

```text
Retrieval
    +
Generation
```

The complete workflow is:

```text
             User Question
                   │
                   ▼
            Query Embedding
                   │
                   ▼
             Vector Store
                   │
                   ▼
          Relevant Documents
                   │
                   ▼
             Retrieved Context
                   │
                   ├──────────────┐
                   │              │
                   ▼              ▼
             User Question + Context
                   │
                   ▼
                  LLM
                   │
                   ▼
             Generated Answer
```

Instead of relying only on the knowledge stored in the LLM, the system retrieves relevant external information and provides it as context.

---

# 🧩 RAG Components

A typical RAG system can be broken down into:

| Component | Purpose |
|---|---|
| Document Loader | Loads external documents |
| Text Splitter | Divides documents into chunks |
| Embedding Model | Converts text into vectors |
| Vector Store | Stores embeddings |
| Retriever | Finds relevant chunks |
| Prompt | Combines query and context |
| LLM | Generates the final response |
| Output Parser | Structures the response |

---

# 🎯 Learning Objectives

The main objective of this repository is to build a strong understanding of the components behind modern LLM applications.

By working through this project, I explored:

### LLM Fundamentals

- How LLM applications work
- Chat models
- Prompt construction
- Model interaction

### Document Processing

- PDF loading
- CSV loading
- Directory loading
- Text splitting
- Chunking strategies

### Semantic Search

- Text embeddings
- Vector representations
- Similarity search
- Vector stores

### RAG

- Retrieval
- Context augmentation
- LLM generation
- End-to-end RAG pipelines

---

# 🔬 Learning Approach

Rather than treating RAG as a single black-box framework, this repository explores the individual components separately.

```text
LLM
 ↓
Chat Models
 ↓
Prompts
 ↓
Output Parsers
 ↓
Document Loading
 ↓
Text Splitting
 ↓
Embeddings
 ↓
Vector Stores
 ↓
Retrievers
 ↓
RAG
```

This approach helps understand **what happens inside an LLM application at each stage**.




```

That makes the GitHub repository immediately show **your learning progression from LLM basics → RAG** rather than looking like a collection of unrelated folders.
