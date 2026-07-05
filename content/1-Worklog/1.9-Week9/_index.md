---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Fully build the Frontend platform using React.js and React Flow for network diagram drawing.
* Successfully initialize and configure the Python/FastAPI Backend server for business logic processing.
* Successfully integrate Google Gemini API into the Backend for AI analysis tasks.
* Complete the two-way API connection flow (Frontend ↔ Backend): send network topology as JSON and receive AI responses.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Create `.gitignore` to protect sensitive files and ignore local environment <br> - Initialize Git Repository and set up branch structure (dev, frontend-ui, backend-api) <br> - Link local repo to GitHub and push initial source code | 15/06/2026 | 15/06/2026 | <https://git-scm.com/doc> |
| 3   | - Create and activate Python virtual environment (venv), set up `requirements.txt` <br> - Program `main.py` to initialize FastAPI server running on Uvicorn <br> - Configure CORSMiddleware to allow Frontend API calls without CORS errors | 16/06/2026 | 16/06/2026 | <https://fastapi.tiangolo.com/> |
| 4   | - Use Vite to scaffold React Frontend, install `reactflow` <br> - Clean default boilerplate, configure empty full-screen canvas <br> - Fix ESLint warnings about unused variables/libraries | 17/06/2026 | 17/06/2026 | <https://vitejs.dev/guide/> |
| 5   | - Design Sidebar component with network devices (Firewall, Router, Server, PC) <br> - Apply HTML Drag and Drop API with React Flow to drag devices onto canvas <br> - Build control Panel (top-right): Gen AI, Save, Scan Attack | 18/06/2026 | 18/06/2026 | <https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API> |
| 6   | - Install `google-generativeai` in Backend, secure API key via `.env` <br> - Handle Save button: extract graph data to JSON via `toObject()` <br> - Write async `fetch()` function to send JSON to port 8000 and display AI analysis | 19/06/2026 | 19/06/2026 | <https://ai.google.dev/docs> <br> <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API> |

### Week 9 Achievements:

* User interface runs smoothly with drag-and-drop network architecture design.
* Network data collected and converted to standard JSON, perfectly matching LLM input requirements.
* FastAPI server ready to listen and handle HTTP requests, successfully connected to Google AI Studio.
* Full data pipeline from user interaction → Frontend → Backend → AI → UI display works stably.
