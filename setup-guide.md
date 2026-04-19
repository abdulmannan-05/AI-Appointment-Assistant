# Implementation & Configuration Guide

Follow these steps to deploy the NexSched Orchestration suite into your Make.com environment.

## 📋 Prerequisites
* A **Make.com** account (Core or Pro recommended).
* **Google Cloud Console** access (for Gemini API and Google Calendar API).
* A **Slack** workspace with permissions to create a private App/Bot.
* A **Google Sheet** to serve as your Grounding Database.

## 🏗️ Step 1: Grounding Database Setup
1.  Create a new Google Sheet named `User_Preferences`.
2.  In `Sheet1`, define your "Constraint" column.
3.  Add your unavailable hours or weekly schedule in plain text (e.g., "Monday: 09:00 - 13:00 is busy").

## 🏗️ Step 2: Import Blueprints
1.  **Logic Engine:** Import `Automating Appointment Booking.blueprint.json` into a new Make.com scenario.
2.  **Execution Engine:** Import `Integration Webhook for Appointment Booking.blueprint.json` into a second scenario.
3.  **Note:** Upon import, you must re-authenticate your Slack, Google, and Gemini connections.

## 🏗️ Step 3: Webhook Configuration
1.  In the **Execution Engine** scenario, copy the Webhook URL from the first module.
2.  In the **Logic Engine** scenario, locate the Slack "Confirm & Book" button module.
3.  Update the URL in the button block to your unique Webhook URL, ensuring the query parameters (`?name={{...}}&email={{...}}`) remain intact.

## 🏗️ Step 4: System Instruction Fine-Tuning
The Gemini module contains a `system_instruction` block. You can customize the "Persona" here to match your brand voice. 
* **Default:** Professional Scheduling Assistant.
* **Custom:** Friendly Concierge, Executive Admin, etc.

## 🧪 Testing the Workflow
1.  Post a message in your designated Slack channel: 
    * *"Hey, I'd like to book a meeting with Abdul for tomorrow at 10:00 AM. My email is client@example.com"*
2.  Check your Slack DMs for the **Confirmation Button**.
3.  Click **Confirm & Book** and verify the entry in Google Calendar.

---
**Security Note:** Do not share your blueprint files publicly without removing your specific `__IMTCONN__` IDs and Webhook strings.