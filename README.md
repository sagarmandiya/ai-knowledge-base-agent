# 🤖 AI Knowledge Base Agent

A powerful RAG (Retrieval-Augmented Generation) AI agent that can answer questions based on your uploaded documents or web content.

## 🚀 Features

- **📄 Document Upload**: Support for PDF, TXT, DOCX, and MD files
- **🌐 Web Content**: Process content from any publicly accessible web page
- **💬 Interactive Chat**: Ask questions about your documents
- **🧠 RAG Technology**: Uses LangChain and ChromaDB for intelligent document retrieval
- **🎨 Beautiful UI**: Modern, responsive interface built with Streamlit

## 🛠️ Technology Stack

- **Frontend**: Streamlit
- **AI/ML**: LangChain, ChromaDB, HuggingFace Embeddings
- **LLM**: Perplexity AI (Sonar model)
- **Document Processing**: PyPDF, python-docx, BeautifulSoup

## 🚀 Quick Start

### Deploy to Streamlit Cloud

1. **Fork this repository**
2. **Go to [share.streamlit.io](https://share.streamlit.io)**
3. **Connect your GitHub repository**
4. **Set main file path to `standalone_app.py`**
5. **Add secret: `PERPLEXITY_API_KEY = "your_api_key"`**
6. **Deploy!**

### Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Set up secrets
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
# Edit secrets.toml and add your API key

# Run the app
streamlit run standalone_app.py
```

## 📖 Usage

1. **Upload Documents**: Use the sidebar to upload PDF, TXT, DOCX, or MD files
2. **Add Web Content**: Enter any publicly accessible web URL
3. **Ask Questions**: Use the chat interface to ask questions about your documents
4. **Manage Database**: Reset the database to start fresh

## 🔒 Security

- Your API keys are stored securely in Streamlit Cloud secrets
- Documents are processed locally and not stored permanently
- The vector database is created in memory for each session

## 📁 Project Structure

```
ai-agent/
├── standalone_app.py          # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                 # This file
└── .streamlit/
    ├── secrets.toml.example  # Example secrets configuration
    └── secrets.toml          # Your secrets (not in git)
```

## 🆘 Support

If you encounter any issues:
1. Check that your Perplexity API key is correctly set
2. Review the Streamlit Cloud logs
3. Open an issue on GitHub

---

**Built with ❤️ using Streamlit and LangChain**
