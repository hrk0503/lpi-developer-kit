# Level 3 — Rahul Bijarnia

## Repository Link
https://github.com/RahulBijarnia1/lpi-level3-agent

## What I Built
I built an AI agent that takes a user query and generates explainable answers by combining multiple LPI tools and a local LLM.

## Tools Used
- smile_overview → provides SMILE methodology context  
- query_knowledge → provides domain knowledge  
- get_case_studies → provides real-world examples  

## How It Works
- Accepts user input  
- Calls multiple LPI tools  
- Combines outputs  
- Sends data to LLM (Ollama)  
- Generates final answer  

## Explainability
The agent shows:
- SMILE output  
- Knowledge output  
- Case studies  

This allows users to trace how the answer was generated.

## How to Run
pip install -r requirements.txt  
python agent.py "your query"
