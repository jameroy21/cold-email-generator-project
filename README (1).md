# AI-Powered Cold Email Generator

## 🎯 Project Overview

An intelligent cold email generation system that uses Large Language Models (LLMs) to create personalized, context-aware outreach emails for job applications and business development. The application scrapes company career pages, extracts relevant job postings, and generates tailored cold emails that highlight the user's skills in relation to specific job requirements.

---

## ❓ Problem Statement

Job seekers and business developers often struggle with:

- Writing personalized cold emails at scale
- Researching company-specific information for each outreach
- Crafting compelling narratives that connect their skills to company needs
- Maintaining consistency and professionalism across multiple emails

This project solves these challenges by automating the research and drafting process while maintaining a human touch through AI-powered personalization.

---

## 🛠️ Tech Stack

| Component        | Technology              |
|------------------|-------------------------|
| LLM Engine       | LLaMA 3.1 via Groq API  |
| Framework        | LangChain               |
| Vector Database  | ChromaDB                |
| Web Framework    | Streamlit               |
| Programming      | Python 3.9+             |
| Web Scraping     | BeautifulSoup4          |

---

## 🏗️ Architecture Overview

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   User Input    │────│   Web Scraper    │────│   Job Data      │
│ (Company URL)   │    │ (BeautifulSoup)  │    │   Extraction    │
└─────────────────┘    └──────────────────┘    └────────┬────────┘
                                                         │
┌─────────────────┐    ┌──────────────────┐             │
│   Generated     │────│   LLaMA 3.1      │─────────────┘
│   Cold Email    │    │   (Groq API)     │
└─────────────────┘    └──────────────────┘
                                ▲
                                │
                       ┌────────┴────────┐
                       │    ChromaDB     │
                       │   (Portfolio   │
                       │    Storage)    │
                       └────────────────┘
```

---

## ⚙️ How It Works

1. **Input Phase** — User provides a company career page URL
2. **Scraping Phase** — The system extracts job descriptions and requirements from the page
3. **Vectorization Phase** — Job details are converted to embeddings and stored in ChromaDB
4. **Matching Phase** — The system retrieves relevant portfolio projects from the vector database
5. **Generation Phase** — LLaMA 3.1 generates a personalized cold email using:
   - Extracted job requirements
   - Matched portfolio projects
   - Pre-defined prompt templates
6. **Output Phase** — The generated email is displayed for user review and customization

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.9 or higher
- Groq API key (sign up at [https://groq.com](https://groq.com))

### Step 1: Clone the Repository
```bash
git clone https://github.com/jameroy21/ai-cold-email-generator.git
cd ai-cold-email-generator
```

### Step 2: Create Virtual Environment
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Set Up Environment Variables

Create a `.env` file in the root directory:
```
GROQ_API_KEY=your_groq_api_key_here
```

### Step 5: Run the Application
```bash
streamlit run app.py
```

The application will open in your browser at `http://localhost:8501`

---

## 📖 Usage Instructions

### 1. Prepare Your Portfolio

Before generating emails, add your projects to the portfolio:
- Navigate to the **"Portfolio"** section
- Add project details including:
  - Project name
  - Tech stack used
  - Key achievements/metrics
  - Link to GitHub repository

### 2. Generate a Cold Email
- Enter the target company's career page URL
- Click **"Generate Email"**
- Review the AI-generated email
- Copy and customize as needed

### 3. Customize Output

The generated email includes:
- Personalized greeting
- Reference to specific job requirements
- Relevant portfolio project highlights
- Professional closing

---

## ✨ Key Features & Learnings

### Features Implemented
- ✅ Automated web scraping of job postings
- ✅ Vector-based semantic search for portfolio matching
- ✅ LLM-powered email generation with context awareness
- ✅ Simple, intuitive Streamlit UI
- ✅ Persistent portfolio storage with ChromaDB
- ✅ Customizable email templates

### Technical Learnings
- **RAG Architecture** — Implemented Retrieval-Augmented Generation for context-aware outputs
- **Vector Databases** — Gained hands-on experience with ChromaDB for semantic search
- **LLM Integration** — Learned to effectively prompt and control LLaMA 3.1 via Groq API
- **Web Scraping** — Developed robust scraping logic for dynamic career pages
- **Streamlit Development** — Built interactive web apps without frontend expertise

### Business Impact Understanding
- Learned the importance of personalization in cold outreach
- Understood how AI can augment (not replace) human communication
- Gained insights into the job application process from both sides

---

## 🔮 Future Improvements

- [ ] Add email sending capability via email APIs
- [ ] Implement A/B testing for email templates
- [ ] Add support for multiple LLM providers (OpenAI, Anthropic)
- [ ] Create email performance tracking dashboard
- [ ] Add multi-language support
- [ ] Implement email scheduling functionality

---

## 📦 Requirements

```
streamlit==1.28.0
langchain==0.0.325
langchain-groq==0.0.1
chromadb==0.4.15
beautifulsoup4==4.12.2
requests==2.31.0
python-dotenv==1.0.0
```

---

## 👨‍💻 About the Developer

**Jame Roy** | Data Scientist & ML Engineer

- 🔗 LinkedIn: [linkedin.com/in/jame-roy-datascience](https://linkedin.com/in/jame-roy-datascience)
- 🐙 GitHub: [github.com/jameroy21](https://github.com/jameroy21)
- 📧 Email: jrroy.nh@gmail.com

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- [Groq](https://groq.com) for providing fast LLM inference
- [LangChain](https://langchain.com) community for excellent documentation
- [Streamlit](https://streamlit.io) team for making web apps accessible to data scientists

---

⭐ **Star this repository if you find it helpful!**
