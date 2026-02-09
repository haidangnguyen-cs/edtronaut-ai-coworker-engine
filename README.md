# AI Co-worker Engine (Pseudocode)

### Overview
This repository demonstrates the system design for an **AI-powered Job Simulation Engine**, specifically tailored for the Edtronaut internship case study.

Instead of a generic chatbot, this design focuses on **Pedagogical Orchestration**—ensuring the AI behaves like a consistent role-player (e.g., Gucci CHRO) while guiding the learner toward specific objectives.

### Design Philosophy
The code is provided as **pseudocode** to prioritize architectural logic over implementation syntax. Key design decisions include:

1.  **Event-Driven Architecture:** Separating the user-facing chat loop from the heavy lifting of analysis.
2.  **Asynchronous Supervision:** The "Supervisor Agent" runs in the background to monitor learning progress without introducing latency.
3.  **Hybrid Memory:** Balancing raw conversation logs (for natural flow) with structured state flags (for enforcing business constraints).

### File Structure
- `pseudocode.py`: Contains the core logic for the Orchestrator, Supervisor, and Memory components.

### Core Components
* **`Orchestrator`**: The synchronous API layer. It constructs the prompt dynamically based on the current state and retrieved documents (RAG).
* **`SupervisorAgent`**: The asynchronous "Invisible Director". It detects stagnation or constraint violations and injects hidden hints for the *next* turn.
* **`MemoryManager`**: Optimizes the context window by pruning chit-chat and summarizing long conversations.
