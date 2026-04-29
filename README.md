# ✈️ Onyx Airline AI Assistant: Intelligent Support Agent with LangGraph & Gemini API

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Gemini API](https://img.shields.io/badge/Google-Gemini_1.5_Flash-orange)
![LangGraph](https://img.shields.io/badge/LangGraph-State_Agents-brightgreen)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626)

## 📖 About The Project

In today's fast-paced world, exceptional customer service is more important than ever. The airline industry can benefit greatly from AI-powered solutions that streamline support processes and enhance the customer experience. 

This project is a sophisticated, simulated **Airline Support Agent (The Onyx Airline AI Assistant)** built using LangGraph and Google's Gemini API. It is designed to logically route, process, and respond to various airline-related customer support scenarios.

### ✨ The Vision: A Conversational AI Assistant
This agent is capable of:
*   **Searching for Flights:** Finding the best flight options based on origin, destination, dates, and passenger count.
*   **Booking Flights:** Handling reservations, managing different travel classes (Economy and Business), and capturing essential passenger details.
*   **Canceling Bookings:** Processing ticket cancellations, calculating appropriate refunds, and updating or removing bookings as needed.

## 🛠️ Key Technologies & Capabilities

To bring this vision to life, the project leverages several powerful technologies:
*   **LangGraph:** A framework for building robust, stateful conversational agents.
*   **Gemini API (`gemini-1.5-flash-latest`):** Google's cutting-edge language model offering a massive **1 million token context window**, allowing the agent to remember conversation history for natural, context-aware interactions.
*   **Function Calling:** Allows the agent to seamlessly interact with simulated airline APIs by translating natural language into specific API calls.
*   **Structured Output & JSON Mode:** Ensures precise data handling by utilizing tools that return structured JSON, efficiently processed by the agent.
*   **Retrieval Augmented Generation (RAG):** Provides the agent with up-to-date real-world information (like airport codes) through web searches using `DuckDuckGoSearchRun`.

## 🧠 System Architecture & Graph Design

The core of the project relies on a highly structured State Machine constructed with LangGraph.

### 1. State Management
*   **`FlightBookingState`**: A `TypedDict` that stores all conversation data, including messages, search parameters, flight search results, booking references, passenger details, travel class, and control flow flags.

### 2. Core Nodes
*   **`chatbot_node`**: Main controller handling search, booking, and cancellation flows with LLM integration.
*   **`collect_details_node`**: Sequentially collects passenger details and meal preferences.
*   **`finalize_booking_node`**: Validates and prepares the flight booking tool call with cleaned passenger data.
*   **`human_input_node`**: Gets and processes user input with quit/decline handling.
*   **`execute_tools_node`**: Executes and validates tools (search/book/cancel flights, web search).

### 3. Conditional Edge Routing
Dynamic flow control functions (e.g., `route_after_chatbot`, `route_after_collect_details`, `route_after_human`) ensure the conversation routes smoothly between tools, detail collection, finalization, human input, and the end of the graph based on the user's current phase.

## 💻 Simulated API Functions

The agent interacts with a simulated backend using the following core Python tools:
*   `search_flights_api()`: Simulates searching flights for specific travel classes and stores the base price.
*   `book_flight_api()`: Simulates booking a flight, requires per-passenger details, and confirms pricing.
*   `cancel_booking_api()`: Simulates cancelling tickets, calculates refunds based on booked class fare, and updates the system.

## 🚀 Getting Started

To run this notebook locally or in your own cloud environment:

### 1. Install Dependencies
```bash
pip install langchain langgraph google-generativeai requests pydantic duckduckgo-search
```

### 2. Set Up Your API Key
The code safely prioritizes Kaggle Secrets but falls back to environment variables. Set your Gemini API key locally:
*   **Windows:** `set GOOGLE_API_KEY="your_api_key_here"`
*   **Mac/Linux:** `export GOOGLE_API_KEY="your_api_key_here"`

### 3. Run the Notebook
Open `Airline_Support_Agent.ipynb` in Jupyter Notebook or JupyterLab and run the cells sequentially to start chatting with the Onyx Airline AI Assistant.

## 🌐 View on Kaggle & Read the Blog

*   **Hands-on Execution:** You can run the notebook directly in your browser, modify the code, and see how different parameters affect the results with zero setup on Kaggle: 
    👉 **[Airline Support Agent on Kaggle](https://www.kaggle.com/code/rupajiet/airline-support-agent-using-langgraph-gemini-api)**
*   **Detailed Walkthrough:** Read the full article documenting the creation of this project here: 
    👉 **[Building an Intelligent Airline Support Agent Blog Post](https://geminiagent.blogspot.com/2025/04/building-intelligent-airline-support.html)**

## 🧗 Challenges & Lessons Learned
*   **State Management:** Properly managing the conversation state within LangGraph was crucial for maintaining context and ensuring smooth transitions between different phases.
*   **Error Handling:** Implementing robust error handling was essential for gracefully dealing with invalid user input and unexpected API responses.
*   **Tool Design:** Carefully designing the tools and their descriptions was important for guiding the LLM to use them effectively.

## 🔮 Next Steps & Future Improvements
*   **Real-World API Integration:** Connecting the agent to real-world airline APIs.
*   **More Sophisticated NLP:** Improving the agent's ability to understand complex requests.
*   **Enhanced Error Recovery:** Making the agent more resilient to unexpected issues.
*   **Multilingual Support & Personalization:** Broadening reach and personalizing responses based on past interactions.
```
