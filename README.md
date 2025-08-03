

# Smart Home Energy Advisor Agent

## Problem Statement
Many households struggle with high electricity bills and lack insight into when and how energy is consumed. Without actionable recommendations, users miss opportunities to save power and reduce costs.

## Proposed Solution
The **Smart Home Energy Advisor Agent** is an agentic AI assistant that analyzes smart meter and appliance usage data to provide personalized energy-saving advice. It leverages IBM Granite AI (via watsonx.ai) for reasoning and recommendation generation, and is deployed on IBM Cloud Lite for scalability and accessibility.

## Features
- Ingests real-time and historical energy consumption data (smart meter + appliance-level)
- Uses agentic AI (ReAct-style prompt scaffolding) for interactive Q&A and recommendations
- Identifies high-usage appliances and peak-hour waste
- Suggests optimal times for running appliances (e.g., off-peak scheduling)
- Provides simple, explainable tips to reduce bill (e.g., AC tuning, load shifting)
- Supports extensibility for multilingual interfaces and external factors (weather, pricing)

## Architecture Overview
1. **Data Collection**: Smart meter / appliance data ingested and stored (e.g., Cloudant).
2. **Preprocessing**: Cleaning, anomaly handling, feature extraction.
3. **Agentic Reasoning**: Granite AI model processes structured prompt (ReAct style) to answer queries and generate tips.
4. **Backend**: Flask/Node service orchestrates data retrieval, prompt construction, and response formatting.
5. **Frontend**: Web or mobile UI for user interaction (query input, visualization, advice).
6. **Deployment**: Hosted on IBM Cloud Lite (Code Engine or Cloud Foundry), services bound include watsonx.ai and Cloudant.

## Tech Stack
- **AI/LLM**: IBM watsonx.ai Granite model
- **Database**: IBM Cloudant NoSQL
- **Compute**: IBM Code Engine / Cloud Foundry
- **Backend**: Python (Flask) or Node.js
- **Optional**: IBM Language Translator for multi-language support


## Prerequisites
- IBM Cloud account (Lite)
- watsonx.ai instance with Granite model
- Cloudant NoSQL DB instance
- IBM Cloud CLI (if deploying via CLI)


Example Queries :-


“Why is my bill so high this month?”

“What time should I run the washing machine to save money?”

“Which appliance is consuming the most energy?”

“How can I reduce AC usage without losing comfort?”
