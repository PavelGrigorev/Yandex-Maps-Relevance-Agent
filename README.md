🗺️ Yandex Maps Relevance Agent
This project aims to build an LLM-based agent that assesses the relevance of organizations on Yandex.Maps based on broad search queries (e.g., "restaurant with a terrace" or "romantic jazz bar" ). These types of queries are called rubric-based : users are not looking for a specific organization but are exploring places.

The agent is designed to autonomously gather and analyze data to make accurate relevance judgments. The task is supported by annotated datasets provided by Yandex, which evaluate the relevance of organizations to given queries.

📁 Repository Structure
1. BASE.ipynb
A baseline implementation using:

A CatBoost classifier , trained on labeled training data.
A local LLM via Ollama , used as a zero-shot judge of relevance on validation data using prompt engineering (no fine-tuning).
2. Agent.ipynb
An advanced agent built using LangGraph that:

Uses a local LLM via Ollama .
Optionally performs a web search when uncertain about a decision, allowing it to gather additional context before making a judgment.
🎯 Goal
To explore how LLMs can be enhanced with tools like web search to improve their accuracy in assessing the relevance of real-world entities (in this case, businesses on a map platform) to ambiguous or broad user queries.

🔧 Requirements
Make sure you have the following installed:

Python 3.x
Jupyter Notebook
Ollama
LangChain, LangGraph
CatBoost
Requests / Search API dependencies (for web search tool)
See requirements.txt for exact package versions.

🚀 Getting Started
Install dependencies:
bash


1
pip install -r requirements.txt
Pull a suitable model via Ollama (e.g., llama3, mistral, etc.):
bash


1
ollama pull llama3
Run the notebooks:
bash


1
jupyter notebook
Start with BASE.ipynb for baselines, then proceed to Agent.ipynb for the full agent logic.
📊 Dataset
The dataset consists of annotated examples of query-organization pairs labeled for relevance. It is split into train/validation/test sets and is assumed to be located in a data/ directory.

🤝 Acknowledgments
We thank Yandex for providing the dataset and supporting this research.

🛠️ Future Work
Fine-tune LLMs on domain-specific data.
Add more tools to the agent (e.g., image analysis if available).
Evaluate performance across different categories of queries.
Implement ensemble methods combining both classical ML and LLM outputs.
📬 Contact
If you have any questions or suggestions, feel free to open an issue or contact us directly.
