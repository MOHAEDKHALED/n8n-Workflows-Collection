# n8n-Workflows-Collection

This repository hosts a curated collection of four practical n8n workflows, developed during an exploratory learning journey into workflow automation. These examples showcase how n8n—a powerful, open-source automation tool—can integrate AI (via OpenAI), cloud services (Google APIs), databases (Microsoft SQL), and messaging platforms (Telegram) to solve real-world problems. From personal productivity boosters to enterprise-grade error handling, these workflows demonstrate n8n's flexibility in creating no-code/low-code automations that enhance efficiency and scalability.
n8n enables seamless connections between over 200 apps and services, allowing you to build complex workflows with triggers, actions, and logic without deep programming expertise. By embedding AI agents, these workflows go beyond basic automation, incorporating intelligent decision-making and content generation.
Table of Contents

Prerequisites
Installation and Setup
Workflows Overview
1. Calendar Agent
2. SyntaxAcademy - Generate Posts Workflow
3. CRM Exception RAG Workflow
4. Telegram Assistant

Usage Guidelines
Adding Screenshots and Images
Contributing
License

Prerequisites
To run these workflows, you'll need:

An n8n instance (self-hosted via Docker or cloud-based). Install from n8n.io.
API credentials and accounts for:
OpenAI: For AI agents (e.g., GPT-4o-mini models).
Google Services: OAuth2 for Sheets, Calendar, and Gmail.
Microsoft SQL: Database connection for CRM workflows.
Telegram: Bot API token for messaging integration.
Tavily API: For web search in content generation (sign up at tavily.com).

Basic familiarity with n8n's interface, nodes, and credential setup.

Installation and Setup

Clone the Repository:textgit clone https://github.com/MOHAEDKHALED/n8n-Workflows-Collection.git
cd n8n-Workflows-Collection
Import Workflows into n8n:
Open your n8n dashboard (e.g., http://localhost:5678 for local setups).
Navigate to Workflows > Import from File.
Select each JSON file (e.g., Calnder Agent.json – note: fix any typos in filenames if needed).

Configure Credentials:
In n8n's Credentials section, add entries matching those in the JSON files (e.g., "OpenAi account", "Google Sheets account").
Test connections to ensure APIs are authorized.

Activate and Test:
Some workflows are set to active: false by default. Enable them via the toggle.
Use manual triggers or webhooks to test (e.g., send a Telegram message for the Assistant workflow).


Workflows Overview
Each workflow is self-contained in a JSON file, ready for import. Below is a professional breakdown, including key nodes, integrations, and benefits. Screenshots of workflow diagrams can be added here for visual reference (see Adding Screenshots).
1. Calendar Agent

File: Calnder Agent.json (Note: Typo in original; consider renaming to Calendar-Agent.json).
Description: An AI-driven agent that handles chat messages, logs conversations to Google Sheets, and schedules events in Google Calendar.
Key Components:
Trigger: Webhook for incoming chat messages.
AI Integration: OpenAI (GPT-4o-mini) with memory buffer for contextual responses.
Actions: Append to Sheets (messages and AI replies); Create Calendar events (with start/end, descriptions, and attendees).

Benefits: Streamlines personal and team scheduling, reducing manual entry errors. Ideal for virtual assistants or CRM extensions.
<img width="1917" height="876" alt="2222" src="https://github.com/user-attachments/assets/a348a4bc-435e-48b5-ad99-fded4610d571" />



2. SyntaxAcademy - Generate Posts Workflow

File: SyntaxAcademy - Gnerate Posts WorkFlow.json (Note: Typo "Gnerate" → "Generate"; rename for clarity).
Description: Automates blog post creation by fetching ideas from Google Sheets, searching fresh data via Tavily, generating Arabic content with AI, and updating the sheet.
Key Components:
Trigger: Manual execution.
Integrations: HTTP requests to Tavily API; AI agent for content generation (>1000 words, engaging).
Actions: Aggregate search results; Update Sheets with generated posts.

Benefits: Accelerates content production for educational platforms like SyntaxAcademy, ensuring SEO-optimized, up-to-date Arabic articles with minimal effort.

<img width="1918" height="863" alt="33" src="https://github.com/user-attachments/assets/3490d85b-2837-4035-8279-22bc42701001" />

3. CRM Exception RAG Workflow

File: CRM Exception RAG Workflow.json.
Description: Processes CRM errors via webhook, queries similar exceptions in SQL, uses Retrieval-Augmented Generation (RAG) with OpenAI for recommendations, and stores results.
Key Components:
Trigger: Webhook for exception data.
Database: Microsoft SQL queries with stored procedures.
AI: OpenAI for concise solutions (2-3 sentences, with confidence scores).
Actions: Format JSON responses; Save to database.

Benefits: Enhances technical support efficiency in enterprise CRM systems by leveraging historical data and AI for faster, accurate resolutions—reducing downtime and support tickets.
<img width="1918" height="862" alt="1111" src="https://github.com/user-attachments/assets/29b5abf2-84d3-4e71-9dbf-a26d0f3fbb1c" />

4. Telegram Assistant

File: Telegram Assistant.json.
Description: A smart Telegram bot that processes messages with AI, manages emails via Gmail, and handles Google Calendar events with conversation memory.
Key Components:
Trigger: Telegram message updates.
AI Integration: OpenAI with windowed memory for persistent context.
Actions: Send/retrieve Gmail emails; Create/retrieve Calendar events.

Benefits: Acts as a 24/7 virtual secretary, simplifying daily tasks like emailing or scheduling—perfect for remote workers or small teams to boost personal productivity.

<img width="1918" height="867" alt="44" src="https://github.com/user-attachments/assets/d6d6af97-9bcc-450e-98db-04677d0f9c90" />

Usage Guidelines

Testing: Start with manual triggers in n8n. For webhooks (e.g., CRM), use tools like Postman to simulate inputs.
Customization: Modify nodes (e.g., add error handling or branching logic) to fit your use case. Monitor executions via n8n's logs.
Scaling: Deploy n8n on a production server (e.g., via Docker Compose) for reliability. Set up webhooks securely with HTTPS.
Example Scenario: In the Telegram Assistant, send "/add event tomorrow at 10 AM" – the AI processes it, adds to Calendar, and replies.
