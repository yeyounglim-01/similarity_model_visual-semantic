# Trademark Semantic Similarity Analysis

AI-powered trademark analysis system using Azure OpenAI and semantic embeddings to compare trademark images and detect similarity.

## 🎯 Overview

This project analyzes trademark images using GPT-5.1 vision capabilities and generates semantic embeddings to:
- Generate detailed text descriptions from trademark images
- Create semantic embeddings for similarity comparison
- Calculate similarity scores between target and candidate trademarks
- Generate comprehensive analysis reports

### Key Features
- **Vision-based Analysis**: Uses Azure OpenAI's GPT-5.1 to analyze trademark images
- **Semantic Embeddings**: Converts descriptions to embeddings using text-embedding-3-large
- **Similarity Scoring**: Calculates cosine similarity between trademark embeddings
- **Batch Processing**: Handles multiple trademark comparisons efficiently
- **Configurable**: Easy environment-based configuration

---

## 📋 Requirements

- Python 3.8+
- Azure OpenAI API access
- Internet connection for API calls

## 🚀 Quick Start

### 1. Clone & Setup
```bash
git clone https://github.com/yeyounglim-01/semanticmodel.git
cd semanticmodel
python -m venv venv
venv\Scripts\activate  # Windows
source venv/bin/activate  # macOS/Linux
pip install -r requirements.txt
```

### 2. Configure Environment
```bash
cp .env.example .env
# Edit .env with your Azure OpenAI credentials
```

### 3. Run Analysis
```bash
python trademark_analysis.py
```

---

## 📁 Project Structure

```
semanticmodel/
├── config.py                         # Configuration management
├── trademark_analysis.py             # Main analysis logic
├── compare.py                        # Similarity comparison
├── requirements.txt                  # Python dependencies
├── .env.example                      # Environment template
├── .gitignore                        # Git exclusions
├── README.md                         # Project documentation
├── docs_SETUP_GUIDE_KO.md           # Korean setup guide
├── 00_GITHUB_UPLOAD_CHECKLIST.md    # Upload checklist & guide
└── GITHUB_GUIDELINE.md              # File analysis guidelines
```

---

## 📊 How It Works

1. **Image Analysis**: GPT-5.1 analyzes trademark images and generates descriptions
2. **Embeddings**: Text descriptions are converted to semantic vectors
3. **Similarity**: Cosine similarity calculates likeness between trademarks
4. **Results**: Rankings saved to CSV/JSON format

---

## 💡 Usage Examples

### Basic Analysis
```python
from compare import analyze_similarity

results = analyze_similarity("data.jsonl")
print(results)
```

### Output Format
```json
{
  "TARGET_logo.jpg": [
    ("candidate1.jpg", 0.95),
    ("candidate2.jpg", 0.87)
  ]
}
```

---

## 🔧 Configuration

Edit `.env` file with your settings:

```env
# Azure OpenAI Configuration
AZURE_API_KEY=your_actual_api_key_here
AZURE_API_VERSION=2024-05-01-preview
AZURE_ENDPOINT=https://your-resource-name.openai.azure.com/

# Model Configuration
MODEL_NAME=gpt-5.1-chat
EMBEDDING_MODEL=text-embedding-3-large

# Path Configuration
TARGET_DIR=./test_images/target
CANDIDATE_DIR=./test_images/candidates
OUTPUT_FILE=data.jsonl

# Rate Limit (seconds)
SLEEP_TIME=0.5
```

---

## 🔐 Security

- API keys stored in `.env` (never committed)
- `.gitignore` prevents accidental credential leaks
- All sensitive data managed via environment variables

---

## 📚 Additional Documentation

- **[docs_SETUP_GUIDE_KO.md](docs_SETUP_GUIDE_KO.md)** - Korean setup guide
- **[00_GITHUB_UPLOAD_CHECKLIST.md](00_GITHUB_UPLOAD_CHECKLIST.md)** - Complete checklist
- **[GITHUB_GUIDELINE.md](GITHUB_GUIDELINE.md)** - File analysis guide

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| AZURE_API_KEY error | Check `.env` file exists with valid key |
| Image not found | Verify `TARGET_DIR` and `CANDIDATE_DIR` paths |
| API timeout | Check internet connection, increase `SLEEP_TIME` |
| ModuleNotFoundError | Run `pip install -r requirements.txt` |

---

## 📧 Support

For questions or issues, please open an issue on GitHub.

---

## 📝 License

MIT License

---

## Version History

- **v1.0** (March 2026): Initial release
  - Trademark image analysis
  - Similarity comparison
  - CSV/JSON reporting
