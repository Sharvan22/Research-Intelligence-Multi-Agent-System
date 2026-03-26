# Research Intelligence AI: Multi-Agent Extraction & Verification Pipeline

## 🚀 Overview
In high-density fields like venture capital, legal research, and academia, the bottleneck is often **Information Density vs. Decision Speed**. This project solves that by automating the transition from a raw PDF to a verified, structured Research Brief.

This system is built using **n8n** and **Google Gemini**, employing a multi-agent architecture that prioritizes accuracy and academic integrity over simple summarization.

## 🧠 Architecture: The Multi-Agent Design
Rather than using a single "catch-all" prompt, this workflow utilizes a **Separation of Concerns** strategy. By dividing the workload, the system avoids context-window clutter and maintains high precision.

### The Agents:
1. **The Boss Agent (Orchestrator):** Coordinates the sub-agents and ensures the final output follows a professional "Executive Brief" structure.
2. **The Summary Agent:** Distills the core thesis and executive summary.
3. **The Paper Analyzer:** Focuses on technical methodology and data points.
4. **The Citation Extractor:** Specifically pulls and formats academic references to maintain source integrity.
5. **The Key Insights Agent:** Translates dry data into actionable strategic recommendations.

## 🛡️ The "Secret Sauce": The Reviewer Loop
The defining feature of this system is the **Reviewer Agent**. In a production environment, AI "hallucinations" are a critical failure. 

* **Verification Gate:** After the sub-agents complete their tasks, the Reviewer Agent audits the combined output against the source text.
* **Quality Scoring:** It assigns a score based on accuracy and adherence to instructions.
* **Recursive Feedback:** If the score is below the threshold, the system triggers a **feedback loop**, forcing the agents to re-process the data until it meets quality standards.

## 🛠️ Tech Stack
- **Orchestration:** n8n
- **LLM:** Google Gemini (1.5 Pro / Flash)
- **Integration:** Gmail API (OAuth2)
- **Data Handling:** Binary PDF Processing & JavaScript Sanitization

## 📋 Key Features
- **Form-Triggered:** Easy-to-use interface for PDF uploads or URL submission.
- **Production-Grade Output:** Delivers a custom HTML-formatted email that is stakeholder-ready.
- **State Management:** Uses n8n expressions to pass complex JSON objects between nodes without data loss.

## 🛠️ How to Use
1.  **Export:** Import the `workflow.json` into your n8n instance.
2.  **Credentials:** Set up your Google Gemini API and Gmail OAuth2 credentials.
3.  **Execute:** Trigger the "On form submission" node and upload a research PDF.

---
**Developed by Sharvan Mehta** *Building Agentic Workflows for a Data-Driven World.*
