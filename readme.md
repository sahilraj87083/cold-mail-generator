# Cold Mail Generator with LangChain + Groq

This project automates the process of **scraping job postings**, extracting relevant job details, and generating **personalized cold emails** using **LangChain** and **Groq’s LLMs**.  

It is designed for **business development executives** to quickly create professional cold emails tailored to job postings found on company career pages.  

---

## 🚀 Features
- Extracts **job postings** (role, experience, skills, description) from scraped website text.  
- Converts unstructured scraped text into clean **structured JSON**.  
- Automatically generates **cold emails** personalized to the job description.  
- Integrates **AtliQ’s portfolio links** into the generated email to showcase relevant expertise.  
- Uses **LangChain + Groq LLMs** (`llama-3.3-70b-versatile`) for accurate parsing and high-quality text generation.  

---

## 📂 Project Structure
├── chain.py # Core Chain class (job extraction + email generation)
├── .env # Environment variables (API keys)
├── requirements.txt # Dependencies
├── README.md # Project documentation




---

## 🔧 Installation

1. **Clone the repository**
    ```bash
        git clone https://github.com/your-username/cold-mail-generator.git
        cd cold-mail-generator
    ```
Create a virtual environment

python -m venv venv
source venv/bin/activate    # For Mac/Linux
venv\Scripts\activate       # For Windows


Install dependencies

pip install -r requirements.txt


Set up environment variables
Create a .env file in the root directory:

GROQ_API_KEY=your_groq_api_key_here

⚡ Usage
1. Extract Jobs from Scraped Text
from chain import Chain

chain = Chain()
scraped_text = "..."  # your scraped career page text
jobs = chain.extract_jobs(scraped_text)
print(jobs)

2. Generate a Cold Email
job = jobs[0]  # pick a job from extracted list
portfolio_links = [
    "https://your-portfolio-link-1.com",
    "https://your-portfolio-link-2.com"
]

email = chain.write_mail(job, portfolio_links)
print(email)

📦 Example Output
Extracted Job JSON
[
  {
    "role": "Software Engineer",
    "experience": "3+ years",
    "skills": ["Python", "Django", "REST APIs"],
    "description": "We are looking for a software engineer to build scalable web applications."
  }
]

Generated Cold Email
Dear Hiring Manager,

I came across your job posting for a Software Engineer requiring expertise in Python, Django, and REST APIs. At AtliQ, we specialize in AI & Software Consulting, delivering solutions that optimize processes, reduce costs, and scale efficiently...

[Rest of email body...]




