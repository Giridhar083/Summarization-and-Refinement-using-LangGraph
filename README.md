# LangGraph Summarization & Refinement Agent

This project implements a stateful text processing workflow using **LangGraph** and **FastAPI**. It defines an agentic workflow that splits text, generates summaries, and iteratively refines the output until it meets a specific character length constraint.

## Features

* **Stateful Workflow:** Uses `AgentState` to track text chunks, summaries, and step counts across the graph execution.
* **Cyclic Graph Architecture:** Implements a feedback loop (conditional edge) that checks the length of the summary. If the text exceeds the `length_limit`, it routes back to the refinement node.
* **Heuristic Refinement:** Uses a custom "smart refine" logic to strip filler words and truncate text to meet constraints.
* **FastAPI Integration:** The entire workflow is wrapped in a FastAPI endpoint (`/graph/run`) for easy integration.

## Installation

1. Clone this repository.
2. Install the required dependencies:

```bash
pip install -r requirements.txt
