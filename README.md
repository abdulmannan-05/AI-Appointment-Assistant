# NexSched: AI-Driven Enterprise Meeting Orchestration

NexSched is a production-grade automation suite designed to eliminate the friction of manual appointment scheduling. By leveraging **Gemini 2.5 Flash** for natural language understanding and **Make.com** for workflow orchestration, this system transforms unstructured messages from communication platforms into structured, verified calendar events.



## 🌟 The Value Proposition
Traditional schedulers require users to fill out rigid forms. NexSched allows clients and partners to request meetings in plain English. The system intelligently:
* **Parses Intent:** Extracts names, emails, dates, and times from raw text.
* **Contextual Verification:** Cross-references requests against a dynamic "Grounding Database" (Google Sheets) to ensure no conflicts with existing obligations or "no-fly" zones.
* **Human-in-the-Loop (HITL):** Provides a secure confirmation gateway before any event is finalized on the executive calendar.

## 🛠️ Technical Architecture
The system is built on a modular, decoupled architecture to ensure scalability and ease of maintenance:

1.  **The Logic Engine (Blueprint 1):** * **Trigger:** Monitors Slack channels for incoming requests.
    * **Grounding:** Performs a real-time lookup of user-defined constraints.
    * **Reasoning:** Utilizes LLM-based soft-classification to determine if a slot is "available" or "conflicted."
2.  **The Execution Layer (Blueprint 2):**
    * **Webhook Gateway:** Securely receives validated meeting data.
    * **Integration:** Synchronizes with Google Calendar and triggers professional HTML confirmation emails via Gmail.

## 🚀 Key Features
* **Dynamic Availability:** Grounded reasoning allows the AI to understand complex schedules (e.g., "Available only after 2 PM on Mondays").
* **Zero-Friction UX:** No apps for the end-user to install; works entirely through chat.
* **Automated Confirmation:** Sends immediate, professional calendar invites and email follow-ups.

---
*Developed by Abdul Mannan | Passionate about AI Automation & System Integration*