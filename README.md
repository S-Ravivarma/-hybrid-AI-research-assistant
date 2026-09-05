# Hybrid AI Research Assistant

A hybrid Large Language Model (LLM) based research assistant built using LangChain and Streamlit. The application uses Google Gemini 2.5 Flash as the primary cloud-based language model and automatically falls back to a locally running Llama 3 8B model through Ollama when the cloud model is unavailable.

The project demonstrates a practical cloud-to-local LLM fallback architecture with conversational memory, structured prompting, and an interactive Streamlit chat interface.

---

## Project Overview

Modern AI applications often depend on external cloud-based Large Language Models. While cloud models provide strong performance, they can become temporarily unavailable due to network problems, service interruptions, API limitations, or configuration issues.

This project addresses that reliability problem by implementing a hybrid LLM architecture.

The application first attempts to generate a response using Google Gemini 2.5 Flash. If the cloud model fails, the system automatically switches to Llama 3 8B running locally through Ollama.

The user can continue interacting with the application without manually switching models.

---

## Key Features

### Hybrid LLM Architecture

The application uses two different LLM providers:

- Primary Model: Google Gemini 2.5 Flash
- Fallback Model: Llama 3 8B through Ollama

The cloud model is attempted first. If an exception occurs, the application automatically invokes the local model.

```text
User
 |
 v
Streamlit Chat Interface
 |
 v
Gemini 2.5 Flash
 |
 +---- Success ----> Response
 |
 +---- Failure
          |
          v
     Llama 3 8B
       Ollama
          |
          v
       Response
