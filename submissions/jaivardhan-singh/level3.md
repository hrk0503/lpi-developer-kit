Here is the link to my Level 3 AI Agent repository:
https://github.com/jv-singh/smile-ai-agent

### My AI Agent Implementation
I built a custom AI agent using Python that interfaces directly with the LPI MCP server via subprocess stdio. My agent queries three specific LPI tools: `smile_overview`, `query_knowledge`, and `get_case_studies`. It retrieves this raw context and feeds it into a locally running `qwen2.5:1.5b` LLM via Ollama.

For explainability, my agent strictly maps the LLM's response back to the original tools. It appends a "PROVENANCE" section at the end of every answer, explicitly stating which tools were executed and the exact arguments passed to them. It also cites the sources inline (e.g., [Tool 1], [Tool 2]), ensuring the user can verify the exact origin of the generated insights.