# ✈️ Airline Support Agent using LangGraph & Gemini API

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Gemini API](https://img.shields.io/badge/Google-Gemini_API-orange)
![LangGraph](https://img.shields.io/badge/LangGraph-State_Agents-brightgreen)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626)

## 📖 About The Project

This project implements an intelligent, state-driven **Airline Support Agent** designed to handle customer queries efficiently. Built using **LangGraph** for robust conversational routing and workflow management, and powered by **Google's Gemini API** for natural language understanding and generation. 

This notebook demonstrates how to build a production-ready AI agent that can logically route, process, and respond to various airline-related customer support scenarios (e.g., baggage claims, flight rebooking, cancellations, and general FAQs).

🎓 **Context:** *This project was developed as part of the **Google Gen AI Intensive Course**, focusing on practical applications of Large Language Models (LLMs) and advanced agentic frameworks.*

## ✨ Features
* **Stateful Conversations:** Uses LangGraph to manage the conversational state, ensuring the agent remembers context across multi-turn interactions.
* **Intelligent Routing:** Automatically classifies user intent and routes the query to the appropriate sub-agent or workflow (e.g., separating a refund request from a baggage inquiry).
* **Secure API Handling:** Includes robust API key management with built-in fallbacks for both Kaggle `UserSecrets` and local environment variables.
* **Powered by Gemini:** Leverages the advanced reasoning capabilities of Google's Gemini models for highly accurate and empathetic customer responses.

## 🛠️ Tech Stack
* **Language:** Python
* **LLM:** Google Gemini API
* **Agent Framework:** LangGraph / LangChain
* **Environment:** Jupyter Notebook (Originally developed on Kaggle)

## 🚀 Getting Started

To run this notebook locally or in your own cloud environment, follow these steps:

### Prerequisites
1. You will need a **Google Gemini API Key**. You can get one from [Google AI Studio](https://aistudio.google.com/).
2. Python 3.8 or higher installed on your system.

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/airline-support-agent.git
   cd airline-support-agent
   ```
2. Install the required libraries. You can run this in your terminal or directly inside a notebook cell:

```bash
pip install langchain langgraph google-generativeai langchain-google-genai
```

## Running the Notebook

* Set up your API key as an environment variable.
* On Windows: set GOOGLE_API_KEY="your_api_key_here"
* On Mac/Linux: export GOOGLE_API_KEY="your_api_key_here"
* (Alternatively, you can create a .env file if you are using python-dotenv).
  
Open the Jupyter Notebook:

```bash
jupyter notebook "airline-support-agent-using-langgraph-gemini-api.ipynb"
```
Run the cells sequentially. The code is designed to automatically detect your environment variables and configure the Gemini API securely.

🌐 View on Kaggle

If you'd like to see the original execution environment or run it with zero setup, you can view the original Kaggle notebook here:

👉 [Airline Support Agent on Kaggle](https://www.google.com/url?sa=E&q=https%3A%2F%2Fwww.kaggle.com%2Fcode%2Frupajiet%2Fairline-support-agent-using-langgraph-gemini-api)

🤝 Acknowledgments

* **Google Gen AI Intensive Course Capstone 2025 Q1** for the foundational knowledge and project inspiration.
* **Kaggle** for providing the original computing environment.
* The maintainers of LangChain and LangGraph for their incredible agentic frameworks.
