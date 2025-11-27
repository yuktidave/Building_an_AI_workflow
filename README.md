✨ AI Calendar Scheduling Workflow
Automate your Google Calendar using n8n + OpenAI
<p align="center"> <img src="https://img.shields.io/badge/n8n-Automation-orange?style=for-the-badge" /> <img src="https://img.shields.io/badge/OpenAI-gpt--4o--mini-blue?style=for-the-badge" /> <img src="https://img.shields.io/badge/Google-Calendar-4285F4?style=for-the-badge&logo=googlecalendar&logoColor=white" /> </p> <p align="center"> <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square" /> <img src="https://img.shields.io/badge/Maintained-Yes-blue?style=flat-square" /> </p>
<h1>🚀 Overview</h1>

This project is an AI-powered automation workflow built using n8n, OpenAI, and Google Calendar.
Simply send a natural-language message like:

“Book a meeting tomorrow at 10 AM.”

…and the workflow automatically creates a properly-timed event in your Google Calendar.

This project helped me learn:

1. 🔗 Workflow automation

2. 🤖 AI Agents & system messages

3. 🧩 JSON expressions

4. 📅 Google Calendar API integrations

5. 🛠 Troubleshooting AI tool pipelines

<h2>🧠 How It Works</h2>
<h3>1️⃣ Chat Trigger</h3>

The workflow starts when a new message is received.

<h3>2️⃣ AI Agent (The Brain 🧠)</h3>

The AI Agent uses OpenAI (gpt-4o-mini) to:

Understand your message

Extract date & time

Generate a meeting title

Decide whether to call the Calendar tool

It uses a dynamic system message to always know today’s date:

Today's date is {{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}

<h3>3️⃣ JSON Expressions</h3>

Instead of static times, the workflow uses:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}


This ensures the AI decides the final event timing, not n8n default values.

<h3>4️⃣ Google Calendar Tool</h3>

The tool creates the real event in your actual calendar.
If the time is free → event is added.
If not → AI can be extended to suggest alternatives.

<h2>🛠️ Tech Stack</h2>
Tool	Purpose
n8n	Workflow automation
OpenAI (gpt-4o-mini)	Natural language understanding
Google Calendar API	Event creation
JSON Expressions	Dynamic parameter mapping
AI Agent	Decision-making + tool calling
🌟 Features

✨ AI understands natural-language date/time

🧷 Auto-creates events in Google Calendar

🕒 Accurate timezone handling (Asia/Kolkata)

🔍 Debuggable AI agent logs

⚡ Uses free OpenAI credits from n8n

❌ No hard-coding of dates or times

<h2>🧪 Testing & Debugging</h2>

During development:

The event was created at wrong times

The Calendar node used current time instead of AI time

System message had fixed dates → wrong scheduling

These were fixed by:

Switching to $fromAI() JSON expressions

Making the system message dynamic

Reviewing AI Agent logs carefully

The final workflow now schedules correct events every time. 🎉

<h2>📂 Workflow Diagram (Simplified)</h2>
flowchart LR
    A[Chat Trigger] --> B[AI Agent]
    B -->|Parses Time| D[From AI Variables]
    D --> C[Google Calendar Tool]
    C --> E(Event Created)

<h2>📁 Files Included</h2>

My workflow.json — Importable n8n workflow

AI workflow.pdf — Full project explanation

README.md — This file

<h2>🧑‍💻 Setup Instructions</h2>
1. Import Workflow

Upload the provided JSON file into n8n.

2. Connect Credentials

Google Calendar

OpenAI (n8n free credits supported)

3. Start Workflow

Run the workflow and send messages like:

schedule a call tomorrow at 4pm

4. Watch Your Calendar Update Automagically ✨


👩‍🎓 Author

Yukti Dave

⭐ Support

If you like this project, please ⭐ star the repo — it motivates me to build more AI workflows!
