# 🤖 AI Knowledge Base Agent

A powerful RAG (Retrieval-Augmented Generation) AI agent that can answer questions based on your uploaded documents or web content. Built with Streamlit and LangChain, this application provides an intuitive interface for document-based question answering.

## 🎯 What It Does

This AI agent allows you to:
- Upload documents (PDF, TXT, DOCX, MD) and ask questions about them
- Process web content from any URL and query it
- Get intelligent, context-aware responses based on your documents
- Maintain conversation history during your session

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI Knowledge Base Agent                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────┐    ┌─────────────────┐    ┌──────────────┐ │
│  │   Document      │    │   Web Content   │    │   Chat       │ │
│  │   Upload        │    │   Processing    │    │   Interface  │ │
│  │                 │    │                 │    │              │ │
│  │ • PDF           │    │ • URL Scraping  │    │ • Questions  │ │
│  │ • TXT           │    │ • Content       │    │ • Responses  │ │
│  │ • DOCX          │    │   Extraction    │    │ • History    │ │
│  │ • MD            │    │                 │    │              │ │
│  └─────────────────┘    └─────────────────┘    └──────────────┘ │
│           │                       │                       │     │
│           └───────────────────────┼───────────────────────┘     │
│                                   │                             │
│  ┌─────────────────────────────────────────────────────────────┐ │
│  │                Document Processing Pipeline                 │ │
│  │                                                             │ │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │ │
│  │  │   Text      │  │   Text      │  │   Embedding         │ │ │
│  │  │ Extraction  │  │ Splitting   │  │   Generation        │ │ │
│  │  │             │  │             │  │                     │ │ │
│  │  │ • PyPDF     │  │ • Chunks    │  │ • HuggingFace       │ │ │
│  │  │ • Beautiful │  │ • Overlap   │  │   Embeddings        │ │ │
│  │  │   Soup      │  │ • Metadata  │  │ • all-MiniLM-L6-v2  │ │ │
│  │  │ • python-   │  │             │  │                     │ │ │
│  │  │   docx      │  │             │  │                     │ │ │
│  │  └─────────────┘  └─────────────┘  └─────────────────────┘ │ │
│  └─────────────────────────────────────────────────────────────┘ │
│                                   │                             │
│  ┌─────────────────────────────────────────────────────────────┐ │
│  │                    Vector Database                          │ │
│  │                                                             │ │
│  │  ┌─────────────────────────────────────────────────────────┐ │ │
│  │  │                    FAISS Vector Store                   │ │ │
│  │  │                                                         │ │ │
│  │  │ • In-memory storage                                     │ │ │
│  │  │ • Similarity search                                     │ │ │
│  │  │ • Session-based                                         │ │ │
│  │  │ • Cloud-compatible                                      │ │ │
│  │  └─────────────────────────────────────────────────────────┘ │ │
│  └─────────────────────────────────────────────────────────────┘ │
│                                   │                             │
│  ┌─────────────────────────────────────────────────────────────┐ │
│  │                    RAG Chain                                │ │
│  │                                                             │ │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │ │
│  │  │   Query     │  │   Context   │  │   Response          │ │ │
│  │  │ Processing  │  │ Retrieval   │  │   Generation        │ │ │
│  │  │             │  │             │  │                     │ │ │
│  │  │ • User      │  │ • Vector    │  │ • Perplexity AI     │ │ │
│  │  │   Question  │  │   Search    │  │ • Sonar Model       │ │ │
│  │  │ • Intent    │  │ • Top-K     │  │ • Context-aware     │ │ │
│  │  │   Analysis  │  │   Results   │  │   Responses         │ │ │
│  │  └─────────────┘  └─────────────┘  └─────────────────────┘ │ │
│  └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘
```

## 🚀 Features

- **📄 Document Upload**: Support for PDF, TXT, DOCX, and MD files
- **🌐 Web Content**: Process content from any publicly accessible web page
- **💬 Interactive Chat**: Ask questions about your documents with conversation history
- **🧠 RAG Technology**: Uses LangChain and FAISS for intelligent document retrieval
- **🎨 Beautiful UI**: Modern, responsive interface built with Streamlit
- **☁️ Cloud-Ready**: Optimized for Streamlit Cloud deployment

## 🛠️ Technology Stack

### Core Technologies
- **Frontend**: Streamlit 1.28.1
- **AI Framework**: LangChain
- **Vector Database**: FAISS (CPU-optimized)
- **Embeddings**: HuggingFace Transformers (all-MiniLM-L6-v2)
- **LLM**: Perplexity AI (Sonar model)

### Document Processing
- **PDF**: PyPDF
- **Web Scraping**: BeautifulSoup4
- **Word Documents**: python-docx
- **Text Processing**: LangChain Text Splitters

### Infrastructure
- **Deployment**: Streamlit Cloud
- **Environment**: Python 3.8+
- **Dependencies**: pip/requirements.txt

## 🚀 Quick Start

### Deploy to Streamlit Cloud (Recommended)

1. **Fork this repository**
2. **Go to [share.streamlit.io](https://share.streamlit.io)**
3. **Connect your GitHub repository**
4. **Set main file path to `standalone_app.py`**
5. **Add secret: `PERPLEXITY_API_KEY = "your_api_key"`**
6. **Deploy!**

Your app will be available at: `https://your-app-name.streamlit.app`

### Local Development

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/ai-knowledge-base-agent.git
cd ai-knowledge-base-agent

# Install dependencies
pip install -r requirements.txt

# Set up secrets
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
# Edit secrets.toml and add your Perplexity API key

# Run the app
streamlit run standalone_app.py
```

## 📖 Usage Guide

### 1. Document Upload
- Use the sidebar to upload PDF, TXT, DOCX, or MD files
- Documents are automatically processed and indexed
- Multiple documents can be uploaded in the same session

### 2. Web Content Processing
- Enter any publicly accessible web URL
- Content is automatically scraped and processed
- Perfect for adding articles, documentation, or web pages

### 3. Chat Interface
- Ask questions about your uploaded documents
- Get intelligent, context-aware responses
- Use example questions for inspiration
- Conversation history is maintained during the session

### 4. Database Management
- View document count in the sidebar
- Reset the database to start fresh
- All data is session-based (resets on app restart)

## 🔒 Security & Privacy

- **API Keys**: Stored securely in Streamlit Cloud secrets
- **Document Processing**: All processing happens in-memory
- **No Persistence**: Documents are not permanently stored
- **Session-Based**: Data is cleared when the app restarts
- **Privacy-First**: No data is shared with third parties

## 📁 Project Structure

```
ai-knowledge-base-agent/
├── standalone_app.py          # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                 # This documentation
├── .gitignore               # Git ignore rules
└── .streamlit/
    ├── secrets.toml.example  # Example secrets configuration
    └── secrets.toml          # Your secrets (not in git)
```

## 🔧 Configuration

### Required Secrets
- `PERPLEXITY_API_KEY`: Your Perplexity AI API key

### Optional Configuration
- Document chunk size: 500 characters
- Chunk overlap: 50 characters
- Retrieval count: 3 most relevant chunks
- Embedding model: all-MiniLM-L6-v2

## 🆘 Troubleshooting

### Common Issues

1. **"PERPLEXITY_API_KEY not found"**
   - Ensure the secret is correctly set in Streamlit Cloud
   - Check that the secret name is exactly `PERPLEXITY_API_KEY`

2. **"Error creating vectorstore"**
   - This usually indicates a dependency issue
   - Check Streamlit Cloud logs for specific error messages

3. **"Import errors"**
   - Verify all dependencies are in requirements.txt
   - Check that the main file path is `standalone_app.py`

4. **Slow performance**
   - First run downloads models (normal behavior)
   - Large documents may take time to process
   - Subsequent operations will be faster

### Getting Help

1. Check the Streamlit Cloud logs for detailed error messages
2. Verify your Perplexity API key is valid and has sufficient credits
3. Ensure your repository is public (required for free Streamlit Cloud)
4. Open an issue on GitHub with detailed error information

## 🎯 Use Cases

- **Research**: Upload research papers and ask questions
- **Documentation**: Process technical docs and get quick answers
- **Content Analysis**: Analyze articles, reports, or web content
- **Learning**: Upload educational materials and quiz yourself
- **Business**: Process company documents and policies

## 🚀 Performance

- **Document Processing**: ~1-2 seconds per document
- **Query Response**: ~2-5 seconds depending on complexity
- **Memory Usage**: Optimized for cloud environments
- **Scalability**: Handles multiple documents and long conversations

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 🙏 Acknowledgments

- **Streamlit** for the amazing web framework
- **LangChain** for the RAG implementation
- **HuggingFace** for the embedding models
- **Perplexity AI** for the language model
- **FAISS** for efficient vector search

---

**Built with ❤️ using Streamlit, LangChain, and modern AI technologies**

*Ready to deploy and start chatting with your documents!* 🚀
