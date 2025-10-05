# NeuralWaves: Autonomous AI-Driven Radio Station

[<image-card alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" ></image-card>](https://opensource.org/licenses/MIT)
[<image-card alt="GitHub issues" src="https://img.shields.io/github/issues/phdametyildiz/NeuralWaves" ></image-card>](https://github.com/phdametyildiz/NeuralWaves/issues)
[<image-card alt="GitHub stars" src="https://img.shields.io/github/stars/phdametyildiz/NeuralWaves" ></image-card>](https://github.com/phdametyildiz/NeuralWaves/stargazers)

## Project Overview

NeuralWaves is an open-source project that simulates an autonomous AI-powered radio station. The system generates dynamic playlists, inserts spoken announcements (e.g., song facts, news, or artist insights), handles listener interactions via text messages, and manages "topic of the day" discussions. It features multiple AI moderators with distinct personas, who host shows solo or collaboratively based on an automated air-plan schedule. Future expansions include advertisement management.

This project is **primarily intended as a demonstrator for different technologies**. It showcases modern software engineering practices and technologies in a real-world application context. By building NeuralWaves, you can explore how AI integrates with microservices, containerization, and agile development to create scalable, intelligent systems. The codebase is modular, well-documented, and encourages contributions to illustrate iterative development.

## Key Features

- **Autonomous Playlist Generation**: Curates music sequences based on genres, trends, and moderator personas.
- **TTS Announcements**: AI-generated spoken content for news, facts, and transitions using text-to-speech.
- **Listener Interaction**: Text-based inbox for messages, with moderation and persona-driven responses.
- **Moderator Personas and Scheduling**: Multiple AI hosts with unique characters; automated hourly schedules supporting co-hosting.
- **Event Handling**: Adapts to important events by adjusting content or schedules.
- **Streaming Broadcast**: Live audio streaming with seamless mixing of songs and announcements.

## Technologies Used and Their Application

NeuralWaves deliberately incorporates a range of technologies to demonstrate their practical use in software development. Below, we highlight key ones, explaining **how** and **to what extent** they are applied:

- **Artificial Intelligence (AI) and Machine Learning**:
  - **Extent**: Core to the project—used for content generation (e.g., announcements, responses) and decision-making (e.g., playlist curation, sentiment analysis for moderation).
  - **How Applied**: Pre-trained open-source models from Hugging Face (e.g., Phi-3-mini for text generation) and Coqui TTS for speech synthesis. Personas are infused via prompt engineering in LLMs, demonstrating natural language processing (NLP), inference optimization (CPU-only for accessibility), and ethical AI (e.g., bias in personas). No custom training is required, focusing on integration rather than from-scratch ML.

- **Microservice Architecture**:
  - **Extent**: Full implementation across 6-8 services (Scheduling, Moderator, Playlist, Announcement, Interaction, Streaming).
  - **How Applied**: Each service is independent, communicating via REST APIs (FastAPI) or message queues. This demonstrates domain-driven design, scalability (e.g., scaling TTS-heavy services), and fault tolerance. 

- **Containerization with Docker**:
  - **Extent**: All services are containerized; Docker Compose handles local multi-service runs.
  - **How Applied**: Each microservice has its own Dockerfile for building images, ensuring reproducibility across environments (e.g., Windows to Linux). T

- **Cloud Computing**:
  - **Extent**: Local-first, but designed for easy cloud migration (e.g., to AWS/EC2 or Heroku free tiers).
  - **How Applied**: Services use cloud-agnostic tools (e.g., SQLite for DB, but extensible to PostgreSQL on cloud). Deployment scripts simulate cloud workflows, demonstrating concepts like auto-scaling, load balancing, and serverless (e.g., potential Lambda integration for announcements). The project can easily be extended to real cloud hosts for hands-on DevOps experience.

- **Agile Methods**:
  - **Extent**: Embedded in the project's structure and guidelines.
  - **How Applied**: Development follows iterative sprints (e.g., MVP with core services, then expansions like ads). GitHub Issues track user stories/tasks, Pull Requests enforce reviews, and branches (e.g., feature/add-persona) promote collaboration. This illustrates Scrum/Kanban in practice, with emphasis on testing (Pytest) and CI/CD (via GitHub Actions placeholders).

Other supporting tech: Python (backend), FastAPI (APIs), Icecast/Liquidsoap (streaming), MusicBrainz API (metadata), and YAML/JSON for configs. The project avoids licensed APIs, relying on public/open-source resources for accessibility.

## Getting Started

### Prerequisites
- Windows 10/11
- Git, Python 3.10, VS Code, Docker Desktop, WSL (Ubuntu)
- Public-domain music files (e.g., from Free Music Archive)

### Installation
1. Clone the repo: `git clone https://github.com/yourusername/NeuralWaves.git`
2. Set up virtual env: `python -m venv neuralwaves_env` and activate.
3. Install deps: `pip install -r requirements.txt`
4. Download models: Run scripts in `scripts/` or manually via Python.
5. Build/Run: `docker-compose up --build`
6. Access: Stream at http://localhost:8000/neuralwaves; Interact via WebSocket at ws://localhost:800X/ws

For detailed Windows setup, see [SETUP.md](SETUP.md) (add your guide here).

### Running Tests
`pytest tests/`

## Contributing
We welcome contributions! Follow agile practices: Create issues for features/bugs, use feature branches, and submit PRs. See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
Built with open-source tools for educational purposes. Inspired by AI radio concepts—fork and learn!


## Human Acknowledgment
The above Text as well as most of the code comes from AI Tools. The curated prompts and responses will at a later stage also be published to demonstrate the current power and capabilities of the tools. The goal is to only use the free tier of these Tools. We will see, how far we can get.
For the time being, here will be the list of the Tools used so far. This list will be updatet every time something new was used.

### GROK
The initial project structure and this Readme file (except some minor changes by myself) were generated with GROK in Version 4 with the preset "Automatic".
Automatic means, GROK itself decides if it gives me a fast answer, or if it uses the expert mode with longer "thinking".
