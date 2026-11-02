<h1 align="center">Hi, I'm Shubh Sonakiya</h1>

<p align="center">
  <b>Associate Software Engineer – AI</b> at Netsmartz<br>
  Building practical AI systems with LLMs, retrieval and intelligent document automation.
</p>

## About me

At Netsmartz I build AI applications end to end, from the model and retrieval pipelines to the FastAPI services and interfaces around them.

- **Working on:** Nimbus, a RAG chatbot over PDF, Word, text and Excel documents, and document-driven vendor and customer onboarding for Microsoft Dynamics 365 Business Central
- **Focus:** LLM applications, retrieval-augmented generation and agentic workflows, plus document AI and computer vision
- **Interested in:** taking AI systems from prototype to production-ready

## Tech stack

**Languages**<br>
![Python](https://img.shields.io/badge/Python-24283B?style=flat-square&logo=python&logoColor=FFD43B)
![C++](https://img.shields.io/badge/C%2B%2B-24283B?style=flat-square&logo=cplusplus&logoColor=659AD2)

**AI & machine learning**<br>
![scikit-learn](https://img.shields.io/badge/scikit--learn-24283B?style=flat-square&logo=scikitlearn&logoColor=F7931E)
![OpenCV](https://img.shields.io/badge/OpenCV-24283B?style=flat-square&logo=opencv&logoColor=8B7CF6)
![DeepFace](https://img.shields.io/badge/DeepFace-24283B?style=flat-square)
![YOLOv8](https://img.shields.io/badge/YOLOv8-24283B?style=flat-square&logo=yolo&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-24283B?style=flat-square)
![OpenVINO](https://img.shields.io/badge/OpenVINO-24283B?style=flat-square&logo=intel&logoColor=00C7FD)
![PaddleOCR](https://img.shields.io/badge/PaddleOCR-24283B?style=flat-square&logo=paddlepaddle&logoColor=4D9BF5)
![RapidOCR](https://img.shields.io/badge/RapidOCR-24283B?style=flat-square)

**LLM applications**<br>
![LangChain](https://img.shields.io/badge/LangChain-24283B?style=flat-square&logo=langchain&logoColor=7FC8FF)
![LangGraph](https://img.shields.io/badge/LangGraph-24283B?style=flat-square&logo=langgraph&logoColor=7FC8FF)
![Gemini API](https://img.shields.io/badge/Gemini_API-24283B?style=flat-square&logo=googlegemini&logoColor=A78BFA)

**Backend & APIs**<br>
![FastAPI](https://img.shields.io/badge/FastAPI-24283B?style=flat-square&logo=fastapi&logoColor=009688)
![Pydantic](https://img.shields.io/badge/Pydantic-24283B?style=flat-square&logo=pydantic&logoColor=E92063)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-24283B?style=flat-square&logo=sqlalchemy&logoColor=F05A3C)
![React](https://img.shields.io/badge/React-24283B?style=flat-square&logo=react&logoColor=61DAFB)

**Databases & infrastructure**<br>
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-24283B?style=flat-square&logo=postgresql&logoColor=699ECA)
![Redis](https://img.shields.io/badge/Redis-24283B?style=flat-square&logo=redis&logoColor=FF4438)
![SQLite](https://img.shields.io/badge/SQLite-24283B?style=flat-square&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-24283B?style=flat-square&logo=docker&logoColor=2496ED)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-24283B?style=flat-square&logo=googlecloud&logoColor=4285F4)

**Developer tools**<br>
![Git](https://img.shields.io/badge/Git-24283B?style=flat-square&logo=git&logoColor=F03C2E)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-24283B?style=flat-square&logo=githubactions&logoColor=2088FF)
![Jupyter](https://img.shields.io/badge/Jupyter-24283B?style=flat-square&logo=jupyter&logoColor=F37626)
![pytest](https://img.shields.io/badge/pytest-24283B?style=flat-square&logo=pytest&logoColor=0A9EDC)

## Featured projects

### Vendor Form Extractor
**Document AI for Business Central vendor onboarding** · [View repository](https://github.com/ShubhSonakiya18/Business-Central-Vendor-Extraction)

**Problem:** Onboarding a vendor means copying details from a GST certificate, a Udyam registration and a cancelled cheque into a Vendor Creation Request Form by hand.

The app reads the three documents, fills the form in Excel, then reads every written cell back and checks it against the source data. A React portal adds login, saved vendor and customer records, customer onboarding from documents, GST-registry checks on customer Excel files, and Business Central payloads.

- **Local by design:** RapidOCR plus a config-driven matching engine, so documents never leave the machine and no LLM sits in the extraction path
- **Config over code:** field labels, regex patterns, validators and Excel cell maps live in YAML, and extraction deterministically produces one 24-field canonical JSON record
- **Checked output:** 16 validators, cross-document consistency checks, and read-back verification of the filled form
- **Faster OCR:** moved OCR inference to OpenVINO, cutting median latency about 2.3× on the benchmark machine (Intel i7-12700H) with identical accuracy
- **Stack:** Python · FastAPI · SQLAlchemy + Alembic · JWT auth · React + Vite · pytest · gitleaks secret scanning in CI

<sub>Team project at Netsmartz. I'm the primary contributor.</sub>

### Face & Expression Detection
**Face recognition with expression analysis for photos and live camera feeds** · [View repository](https://github.com/ShubhSonakiya18/Facial_recognition_and_expression_detection)

**Problem:** Recognise enrolled people in photos or a live feed, and report "Unknown" instead of guessing when a face isn't enrolled.

Organisations enrol people with photos, then identify them in uploaded images or a webcam feed while each face's expression is classified. Admin dashboards cover organisations, role-based users, invitations, recognition sessions and audit logs.

- **Recognition:** 512-d FaceNet embeddings (via DeepFace) with noise augmentation, classified by a calibrated RBF SVM
- **Two-gate identity check:** a face is named only when both the SVM probability and its cosine similarity to that person's mean embedding clear their thresholds
- **Expressions:** DeepFace emotion scores, corrected by rules that target the model's known weak spots
- **Platform:** FastAPI with JWT auth and rate limiting, PostgreSQL, Redis, Google Cloud Storage for datasets and models, a React front end, and Docker Compose for the full stack

<sub>Team project at Netsmartz. I worked mainly on the recognition and expression pipelines and the React front end.</sub>

### Also at Netsmartz <sub>(private repositories)</sub>

- **Nimbus:** RAG chatbot that answers questions from PDF, Word, text and Excel documents. I work on ingestion, text extraction, chunking, retrieval and LLM response generation.
- **Tile Detection & Recommendation:** YOLOv8 finds tiles in an image, and ResNet embeddings with FAISS similarity search recommend visually similar ones.

<details>
<summary><b>Earlier projects</b></summary>
<br>

- **[Cash-Flow-Connect](https://github.com/ShubhSonakiya18/Cash-Flow-Connect):** C++ console banking system that stores accounts in a self-balancing AVL tree, with account search, deletion, deposits and file-based persistence.
- **[Waste Management System](https://github.com/ShubhSonakiya18/Nature-Nexusver1):** PHP and MySQL web app where residents report waste problems to their municipality and track complaint status.

</details>

## GitHub activity

<p align="center">
  <img src="https://github-readme-stats.shion.dev/api?username=ShubhSonakiya18&show_icons=true&hide_rank=true&include_all_commits=true&count_private=true&theme=tokyonight&hide_border=true" height="165" alt="GitHub stats">
  <img src="https://github-readme-stats.shion.dev/api/top-langs/?username=ShubhSonakiya18&layout=compact&langs_count=6&hide=html,css&theme=tokyonight&hide_border=true" height="165" alt="Most used languages">
</p>
<p align="center">
  <img src="https://streak-stats.demolab.com/?user=ShubhSonakiya18&theme=tokyonight&hide_border=true" alt="Contribution streak">
</p>

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Shubh_Sonakiya-0A66C2?style=flat-square&labelColor=24283B)](https://www.linkedin.com/in/shubh-sonakiya-964873252/)
[![Email](https://img.shields.io/badge/Email-shubhsonakiya86%40gmail.com-7C3AED?style=flat-square&logo=gmail&logoColor=white&labelColor=24283B)](mailto:shubhsonakiya86@gmail.com)

<!-- Stats cards and badges follow GPRM (https://gprm.itsvg.in) markup, restyled to one dark theme. The cards refresh on their own; edit the text sections by hand. -->
