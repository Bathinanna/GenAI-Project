# GenAI-Project: MCQ Quiz Generator

An intelligent Multiple Choice Question (MCQ) quiz generator powered by Generative AI that automatically creates quiz questions from input text.

## 📋 Project Overview

This project uses Generative AI to analyze text content and automatically generate high-quality multiple-choice questions (MCQs) with answers. Perfect for educators, students, and content creators who need to quickly create quizzes from study materials, articles, or documentation.

## ✨ Features

- 🤖 AI-powered question generation from text input
- 📝 Automatic creation of multiple-choice questions with distractors
- 🎯 Customizable difficulty levels
- 💾 Export quiz questions in various formats (JSON, CSV, PDF)
- 🌐 Web-based user interface
- 📊 Question quality scoring and validation

## 🧠 Concepts to Revise

Before working with this project, it's helpful to understand these key concepts:

### Programming Concepts
- **Python Programming**: Core language for the project
  - Object-Oriented Programming (OOP)
  - File I/O operations
  - Exception handling
  - Working with APIs
  
- **Natural Language Processing (NLP)**
  - Text preprocessing and tokenization
  - Named Entity Recognition (NER)
  - Text summarization
  - Question answering systems

### AI/ML Concepts
- **Machine Learning Basics**
  - Supervised vs Unsupervised learning
  - Training and inference
  - Model evaluation metrics

- **Deep Learning**
  - Neural networks fundamentals
  - Transformer architecture
  - Attention mechanisms

## 🚀 GenAI Concepts Involved

This project leverages several Generative AI concepts:

### 1. **Large Language Models (LLMs)**
   - Understanding pre-trained language models (GPT, BERT, T5)
   - Prompt engineering for question generation
   - Fine-tuning for domain-specific tasks

### 2. **Prompt Engineering**
   - Zero-shot prompting
   - Few-shot prompting
   - Chain-of-thought prompting
   - System and user prompt design

### 3. **Text Generation**
   - Autoregressive generation
   - Temperature and top-p sampling
   - Beam search strategies
   - Controlling generation parameters

### 4. **Question Generation (QG)**
   - Answer extraction from context
   - Distractor generation
   - Question type classification
   - Answer verification

### 5. **RAG (Retrieval Augmented Generation)**
   - Document chunking strategies
   - Vector embeddings
   - Semantic search
   - Context retrieval for question generation

## 📚 Prerequisites

### Required Knowledge
- Python 3.8 or higher
- Basic understanding of REST APIs
- Familiarity with command-line interfaces
- Understanding of JSON data structures

### Technical Requirements
- Python 3.8+
- pip package manager
- Virtual environment (venv or conda)
- API keys for LLM services (OpenAI, Anthropic, or local models)

## 🛠️ Installation

```bash
# Clone the repository
git clone https://github.com/Bathinanna/GenAI-Project.git
cd GenAI-Project

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys
```

## 🎯 Usage

### Basic Usage

```python
from mcq_generator import MCQGenerator

# Initialize the generator
generator = MCQGenerator(api_key="your_api_key")

# Generate questions from text
text = """
Artificial Intelligence is the simulation of human intelligence 
processes by machines, especially computer systems.
"""

questions = generator.generate_mcqs(
    text=text,
    num_questions=5,
    difficulty="medium"
)

# Display questions
for q in questions:
    print(f"Q: {q.question}")
    print(f"Options: {q.options}")
    print(f"Answer: {q.answer}\n")
```

### Command Line Interface

```bash
# Generate MCQs from a text file
python main.py --input document.txt --output quiz.json --num-questions 10

# Specify difficulty level
python main.py --input document.txt --difficulty hard --num-questions 5

# Export to different format
python main.py --input document.txt --output quiz.pdf --format pdf
```

### Web Interface

```bash
# Start the web server
python app.py

# Open browser to http://localhost:5000
```

## 📁 Project Structure

```
GenAI-Project/
├── README.md                 # Project documentation
├── PROJECT_PROGRESS.md       # Development progress tracker
├── requirements.txt          # Python dependencies
├── .env.example             # Environment variables template
├── main.py                  # CLI entry point
├── app.py                   # Web application
├── mcq_generator/           # Core MCQ generation module
│   ├── __init__.py
│   ├── generator.py         # Main generator class
│   ├── prompts.py          # Prompt templates
│   ├── validators.py       # Question validation
│   └── exporters.py        # Export functionality
├── utils/                   # Utility functions
│   ├── __init__.py
│   ├── text_processor.py   # Text preprocessing
│   └── config.py           # Configuration management
├── templates/               # Web UI templates
│   └── index.html
├── static/                  # Static assets (CSS, JS)
│   ├── css/
│   └── js/
└── tests/                   # Unit tests
    ├── test_generator.py
    └── test_validators.py
```

## 🔧 Configuration

Create a `.env` file with the following variables:

```env
# API Configuration
OPENAI_API_KEY=your_openai_api_key
MODEL_NAME=gpt-3.5-turbo
MAX_TOKENS=2000
TEMPERATURE=0.7

# Application Settings
DEBUG=False
PORT=5000
HOST=0.0.0.0
```

## 🧪 Testing

```bash
# Run all tests
pytest tests/

# Run with coverage
pytest --cov=mcq_generator tests/

# Run specific test file
pytest tests/test_generator.py
```

## 📈 Key Technologies

- **Python 3.8+**: Primary programming language
- **OpenAI API / Anthropic Claude**: LLM for question generation
- **LangChain**: Framework for LLM application development
- **Flask/FastAPI**: Web framework for API and UI
- **NLTK/spaCy**: NLP preprocessing
- **ReportLab/FPDF**: PDF generation
- **pytest**: Testing framework

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🐛 Known Issues & Limitations

- API rate limits may affect generation speed
- Quality of questions depends on input text quality
- Some technical jargon may not generate optimal distractors

## 🗺️ Roadmap

See [PROJECT_PROGRESS.md](PROJECT_PROGRESS.md) for detailed development progress and upcoming features.

## 📧 Contact

For questions or feedback, please open an issue on GitHub.

## 🙏 Acknowledgments

- OpenAI for GPT models
- LangChain community
- Open source NLP libraries
