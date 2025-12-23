# IssueLenz: GitHub Issues Scraper & Summarizer Using LLMs

**IssueLenz** is a full-stack, data-centric web application developed as a **Final Year Design Project (FYDP)**.  
The system is implemented entirely in **Python**, with **Streamlit** used to build the user interface and **LangChain-based Large Language Models (LLMs)** handling issue summarization and analysis.

The application enables users to fetch GitHub issues, apply filters such as labels and date ranges, generate concise summaries, and export the processed results in multiple formats. The goal is to reduce the time and cognitive effort required to review large volumes of issues in modern software repositories.

---

## Project Overview

Large GitHub repositories often accumulate hundreds or thousands of issues, many of which are lengthy, repetitive, or outdated. Reviewing these issues manually can be slow and inefficient, especially for maintainers and new contributors.

IssueLenz addresses this problem by adding an intelligent summarization layer on top of the GitHub REST API. Instead of reading each issue in full, users are presented with short, structured summaries that preserve the key technical details while removing unnecessary verbosity.

In practice, the system:
- Retrieves issues from public GitHub repositories
- Applies user-defined filters such as labels and date ranges
- Generates readable summaries using large language models
- Exports the results in structured formats for further use

---

## Scope of the Project

This repository contains the **complete implementation of IssueLenz**, including both the Streamlit-based interface and the backend processing logic.

### Key components included:
- Integration with the GitHub REST API, including pagination handling
- Automatic handling of API rate limits, with optional Personal Access Token (PAT) support
- Issue filtering and preprocessing workflows
- Abstractive summarization using LangChain
- Support for multiple LLM providers (OpenAI, Hugging Face, Ollama / DeepSeek)
- Session-based caching to avoid redundant summarization
- Export functionality for JSON, Word, and Excel formats
- Dockerized deployment using Docker and Docker Compose

---

## System Architecture (High Level)

IssueLenz follows a layered architecture to maintain clarity and separation of concerns:

- **Presentation Layer (Streamlit)**  
  Manages user input, model selection, and display of summarized issues

- **Application Logic Layer**  
  Handles issue retrieval, preprocessing, summarization workflows, caching, and export logic

- **External Services Layer**  
  Integrates with the GitHub REST API and external LLM providers

This modular design improves maintainability and allows individual components to be extended or replaced with minimal changes to the overall system.

---

## Key Features

- GitHub repository parsing and issue fetching  
- Abstractive issue summarization using LLMs  
- Automatic handling of GitHub API rate limits  
- Optional Personal Access Token (PAT) support  
- Export of summaries in JSON, Word (.docx), and Excel (.xlsx)  
- Fully containerized deployment using Docker  

---

## Results and Impact
Evaluation of IssueLenz on medium to large GitHub repositories produced the following outcomes:
- Reduced manual issue review time by approximately 40%
- Increased issue processing throughput by around 25%
- Average summarization response time of approximately 13 seconds
- Successfully handled large repositories while operating within GitHub API rate limits
---

## Technology Stack

- Python 3.11  
- Streamlit  
- LangChain  
- OpenAI, Hugging Face, Ollama (DeepSeek)  
- GitHub REST API  
- Pandas, Requests  
- Docker and Docker Compose  

---

## Running the Project

### Using Docker (recommended)
The application is fully containerized using Docker and Docker Compose.
- Ensure Docker and Docker Compose are installed on your system
- Clone the repository
- Run the following command from the project root:
```bash
docker-compose up --build
```
Once the containers are running, the Streamlit interface will be accessible via the local host address displayed in the terminal.
### Running Locally (Without Docker)

To run the project directly on your local machine:
- Ensure Python 3.11 is installed
- Create and activate a virtual environment (recommended)
- Install the required dependencies
- Launch the Streamlit application
```bash
pip install -r requirements.txt
streamlit run app.py
```
The application will start locally and can be accessed through the browser using the URL provided by Streamlit.

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

