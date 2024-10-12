# MCA Pathfinder: Your KTU MCA Syllabus Assistant

## Introduction

Welcome to **MCA Pathfinder**, a Real-time Augmented Generation (RAG)-based application designed to help students of APJ Abdul Kalam Technological University (KTU) easily access and explore their MCA syllabus. This application is built using **Pathway**, a robust framework for live Gen AI projects, and **Docker** for seamless containerization, ensuring it's production-ready and highly scalable.

MCA Pathfinder offers real-time updates, adapting to any changes in the syllabus or other educational resources stored as **PDFs** in the project's data folder. You can even integrate the app with shared **Google Drive** files, ensuring the information remains current when collaborators edit or update the files.

---

## Table of Contents

- [What Problem It Solves](#what-problem-it-solves)
- [Architecture Overview](#architecture-overview)
- [Getting Started](#getting-started)
- [Running the RAG Service](#running-the-rag-service)
- [Demo](#demo)
- [Contributing](#contributing)
- [Contact Information](#contact-information)

---

## What Problem It Solves

MCA Pathfinder solves the issue of accessing, navigating, and staying updated with the **MCA syllabus** for KTU students. Instead of manually searching through large PDFs, students can now ask questions like, "What are the subjects for Semester 1?" or "Is there a project submission for Semester 3?" and receive real-time responses.

With data stored as **PDFs** in the project’s data folder, the application fetches and processes syllabus details dynamically. Additionally, it has the capability to connect with shared **Google Drives** or 300+ other data sources, making the project highly flexible and adaptable. Explore the **Pathway** framework for more details [here](https://github.com/pathwaycom/llm-app?tab=readme-ov-file#llm-app) and access further **Pathway** app templates [here](https://pathway.com/app-templates).

---

## Architecture Overview

### **Pathway**
The heart of the application, Pathway provides a powerful RAG framework that ensures real-time updates, in-memory scalable vector storage, and the ability to process new data on the go. It adapts to any changes in the PDFs within the data folder, updating the AI's knowledge base accordingly.

### **Docker**
To ensure seamless deployment across various environments, the application is fully containerized using Docker. This makes the app easy to deploy, test, and manage, whether running on your local machine or in production.

### **Local Data Folder**
The application ingests data stored as **PDFs** in the local data folder. These PDFs contain the latest MCA syllabus information, and the app dynamically processes them. You can extend the data ingestion capabilities by connecting to **Google Drive**, allowing the app to pull live updates when syllabus files are edited by collaborators.

---

## Getting Started

### **Prerequisites**


``` Python 3.10/3.11
Pip (check with "pip --version")
Git (check with "git --version")
Windows: Docker/WSL
OpenAI API key (or use alternatives like Google Gemini, (link unavailable), etc.)
VS Code (or any Python compatible IDE)
```

## Setup Instructions

### Clone the Repository

```bash
git clone https://github.com/yadhukrishnx/projectname.git
cd projectname
```

### Build the Docker Image

```bash
docker build -t raggem .
```
(Make sure that Docker ENgine is Started)

### Run the Docker Container
In Windows
```bash
docker run -v "${PWD}/data:/app/data" -p 8000:8000 raggem
```
In Linux/Mac
```bash
docker run -v "$(pwd)/data:/app/data" -p 8000:8000 --env-file .env raggem
```

### Checking List of Files
```bash
curl -X POST "http://localhost:8000/v1/pw_list_documents" -H "accept: */*" -H "Content-Type: application/json" 
```
### Checking List of Files
```bash
curl -X POST "http://localhost:8000/v1/pw_list_documents" -H "accept: */*" -H "Content-Type: application/json" 
```

### Update your .env File with your Gemini API Key
If you've already built a pipeline with Open AI, this is where things get slightly different. Configure your key in a .env file by providing it as follows:

GEMINI_API_KEY=*******
Replace ******* with your actual Gemini API key. Save the file as .env in the demo-question-answering folder


# Demo
![Insert demo video or GIF here]
A short demo video showcasing how the application responds to queries about the MCA syllabus.


# Contributing
I welcome contributions from developers to improve or extend this project! Please follow these guidelines:

Fork the repository.
Create a new branch (git checkout -b feature-name).
Make your changes and commit them (git commit -m 'Add new feature').
Push the branch (git push origin feature-name).
Create a Pull Request.
For any significant changes, please open an issue first to discuss what you would like to change.

