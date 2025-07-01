# Text Search Experiments

**Advanced text search implementation** comparing keyword-based and semantic search approaches on structured Vietnamese healthcare data.

## 🔍 Search Methods
- **BM25 Algorithm**: Keyword-based search optimized for Vietnamese text
- **Vector Search**: Semantic search using LlamaIndex + Qdrant vector database
- **Retrieval Evaluation**: Retrieval evaluation with LlamaIndex

![text search illustration](./public/image-1.png)

## 🛠️ Technical Architecture

### Environment Setup Details

#### Virtual Environment
Python virtual environments isolate project dependencies, preventing version conflicts between projects. Similar to Node.js modules, they can be deleted and recreated as needed.

```bash
# Create virtual environment
python -m venv .venv

# Activate (macOS/Linux)
source .venv/bin/activate

# Activate (Windows)
.venv\bin\activate.ps1
```

#### UV Package Manager
[UV](https://docs.astral.sh/uv/) is an extremely fast Python package manager written in Rust, providing:
- Fast dependency resolution
- Version conflict prevention
- Project isolation
- Compatible with pip

#### Dependencies
- **LlamaIndex**: Document indexing and retrieval framework
- **Qdrant**: Vector database for semantic search
- **OpenAI**: Embeddings and language models
- **PyVi**: Vietnamese text tokenization
- **Pandas**: Data manipulation and analysis

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- OpenAI API key (for embeddings and LLM)
- Qdrant instance (local or cloud)

### Setup Instructions

1. **Activate Virtual Environment**
   ```bash
   # macOS/Linux
   source ./.venv/bin/activate
   
   # Windows
   ./.venv/bin/activate.ps1
   ```

2. **Install Dependencies**
   ```bash
   uv pip install -r reqs.txt
   # or
   pip install -r reqs.txt
   ```

3. **Configure Environment**
   - Copy `.env_vars.txt` to `.env`
   - Add your OpenAI API key
   - Configure Qdrant connection settings

4. **VS Code Setup**
   - Press `Shift + Command + P` → `Python: Select Interpreter`
   - Choose the interpreter from `.venv/bin/python`
   - Press `Shift + Command + P` → `Developer: Reload Window` (if needed)

## 📁 Project Structure

```
├── data/
│   ├── 20250612.json                    # Structured healthcare documents
│   ├── Report_MappingCSYT_20250507.xlsx # Validation mapping data
│   └── eval_dataset.json               # Generated evaluation dataset
├── notebooks/
│   ├── keyword_search_bm25.ipynb       # BM25 keyword search implementation
│   ├── search_qdrant.ipynb             # Vector search with LlamaIndex + Qdrant
│   └── retrieval_evaluation.ipynb      # Search performance evaluation
├── reqs.txt                            # Python dependencies
└── .env                                # Environment variables
```

### Key Files
- **BM25 Search**: `keyword_search_bm25.ipynb` - Traditional keyword-based search
- **Vector Search**: `search_qdrant.ipynb` - Semantic search implementation  
- **Evaluation**: `retrieval_evaluation.ipynb` - Evaluate information retrieval 

## 💭 Framework Comparison: LlamaIndex vs Direct Implementation

### LlamaIndex Pros
- **Unified Interface**: "One framework for all" - consistent syntax across different AI tools
- **Rapid Prototyping**: Quick setup for common RAG patterns
- **Ecosystem Integration**: Works with multiple vector databases, LLMs, and embedding models

### LlamaIndex Cons
- **Documentation Complexity**: Information density makes it harder to understand actual implementation
- **Over-abstraction**: Simple tasks become unnecessarily complex
- **Learning Overhead**: Requires understanding LlamaIndex-specific patterns vs. core concepts

### Personal Recommendation
For learning and production use, I prefer **direct implementation** with individual tools:

1. **Clearer Documentation**: Tools like Qdrant have more focused, practical documentation
2. **Better Understanding**: Working directly with APIs teaches core concepts
3. **Flexibility**: Easier to customize and optimize for specific use cases
4. **Tool Familiarity**: Understanding individual tools makes debugging easier

**When to use LlamaIndex**: Large teams needing standardized patterns, or when rapidly prototyping with multiple AI tools.

## 📚 References

### Core Technologies
- **[Python Virtual Environments](https://docs.python.org/3/library/venv.html)** - Environment isolation
- **[UV Package Manager](https://docs.astral.sh/uv/)** - Fast Python package management
- **[PyPI](https://pypi.org/)** - Python package repository

### Search & Vector Databases  
- **[Qdrant](https://qdrant.tech/)** - Vector database documentation
- **[Qdrant Collections](https://qdrant.tech/documentation/concepts/collections/)** - Collection management
- **[LlamaIndex](https://www.llamaindex.ai/)** - RAG framework documentation

### Natural Language Processing
- **[OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings?lang=python)** - Text embedding API
- **[BM25 Algorithm](https://www.elastic.co/blog/practical-bm25-part-2-the-bm25-algorithm-and-its-variables)** - Elasticsearch BM25 guide
- **[BM25 for Vietnamese](https://ndquy.github.io/posts/okapi-bm-25-tim-kiem-tieng-viet/)** - Vietnamese text search implementation

### Evaluation & Analysis
- **[LlamaIndex Retrieval Evaluation](https://docs.llamaindex.ai/en/stable/examples/evaluation/retrieval/retriever_eval/)** - Performance evaluation methods
- **[Information Retrieval Metrics](https://www.pinecone.io/learn/offline-evaluation/)** - Evaluation measures guide
- **[NumPy & Pandas Guide](https://faculty.washington.edu/otoomet/machinelearning-py/numpy-and-pandas.html)** - Data manipulation (UW)

---
<!-- 
## 📋 TODO
- [ ] Add performance benchmarks
- [ ] Implement hybrid search (BM25 + Vector)
- [ ] Add multilingual support
- [ ] Create web interface
- [ ] Add automated testing -->
