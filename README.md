# n8n-Workflows-Collection
This repository contains four n8n workflows (automation projects) that demonstrate the power of n8n in integrating AI, Google services, databases, and messaging platforms. These workflows were built during my learning journey with n8n, focusing on real-world automation scenarios like calendar management, content generation, error handling in CRM, and personal assistants.
n8n is an open-source workflow automation tool that allows you to connect apps and services without heavy coding. These examples show how AI (via OpenAI) can be embedded into automated processes to make life easier and boost productivity.
Table of Contents

Prerequisites
Installation
Workflows Overview
1. Calendar Agent
2. SyntaxAcademy - Generate Posts Workflow
3. CRM Exception RAG Workflow
4. Telegram Assistant

Usage
Contributing
License

Prerequisites

An n8n instance (self-hosted or cloud). Download from n8n.io.
Accounts and API keys for:
OpenAI (for AI agents).
Google (Sheets, Calendar, Gmail OAuth).
Microsoft SQL (for CRM workflow).
Telegram (for Telegram Assistant).
Tavily API (for content generation).

Basic knowledge of n8n nodes and workflows.

Installation

Clone this repository:textgit clone https://github.com/MOHAEDKHALED/n8n-Workflows-Collection.git
Open n8n in your browser (e.g., http://localhost:5678 if self-hosted).
Import each workflow:
Go to n8n dashboard > Workflows > Import from File.
Select the JSON file for each workflow (e.g., Calnder Agent.json).

Configure credentials:
Add your API keys and OAuth credentials in n8n's Credentials section.
For example, create "OpenAi account", "Google Sheets account", etc., as referenced in the JSON files.

Activate workflows as needed (some are set to active: false by default).

Workflows Overview
1. Calendar Agent

Description: An AI-powered chat agent that processes incoming messages, saves conversations to Google Sheets, and adds events to Google Calendar.
Key Features:
Triggers on chat messages via webhook.
Uses OpenAI (GPT-4o-mini) for processing.
Saves user messages and AI responses in Sheets.
Creates calendar events with details like start/end times and descriptions.

Benefits: Automates personal scheduling and logging, ideal for virtual assistants or team coordination.
File: Calnder Agent.json

2. SyntaxAcademy - Generate Posts Workflow

Description: A content generation pipeline that fetches ideas from Google Sheets, searches for fresh data via Tavily API, generates Arabic blog posts using AI, and updates the sheet.
Key Features:
Manual trigger.
Web search integration for up-to-date info.
AI agent (GPT-4o-mini) to write engaging posts (>1000 words).
Aggregates and updates data in Sheets.

Benefits: Speeds up content creation for blogs or academies like SyntaxAcademy, ensuring high-quality, SEO-friendly Arabic content.
File: SyntaxAcademy - Gnerate Posts WorkFlow.json

3. CRM Exception RAG Workflow

Description: Handles CRM exceptions via webhook, searches for similar issues in a SQL database, uses RAG (Retrieval-Augmented Generation) with OpenAI to suggest solutions, and saves recommendations.
Key Features:
Webhook trigger for incoming exceptions.
SQL queries for similar exceptions.
OpenAI (GPT-4o-mini) for concise recommendations (2-3 sentences).
Formats and responds with JSON, saves to DB.

Benefits: Improves technical support efficiency in CRM systems by reducing resolution time for recurring errors through hybrid AI-database analysis.
File: CRM Exception RAG Workflow.json

4. Telegram Assistant

Description: A Telegram bot that processes messages with AI, sends emails via Gmail, manages Google Calendar events, and maintains conversation memory.
Key Features:
Triggers on Telegram messages.
AI agent with memory for context-aware responses.
Integrates Gmail for email sending/retrieval.
Calendar operations for events.

Benefits: Acts as a 24/7 personal secretary, streamlining daily tasks like emailing or scheduling without switching apps.
File: Telegram Assistant.json

Usage

Testing: Execute workflows manually in n8n or via triggers (e.g., webhooks, Telegram).
Customization: Edit nodes in n8n to fit your needs, like changing API keys or adding more tools.
Deployment: For production, host n8n on a server (e.g., Docker) and secure webhooks.
Example: For Calendar Agent, send a chat message like "Add meeting at 3 PM tomorrow" – it will process, save, and add to calendar.

Contributing
Feel free to fork this repo, add improvements, or submit pull requests. If you have issues, open a ticket with details.
License
This project is licensed under the MIT License - see the LICENSE file for details.
