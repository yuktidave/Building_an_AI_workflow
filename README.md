✨ AI Calendar Scheduling Workflow
Automate your Google Calendar using n8n + OpenAI
<p align="center"> <img src="https://img.shields.io/badge/n8n-Automation-orange?style=for-the-badge" /> <img src="https://img.shields.io/badge/OpenAI-gpt--4o--mini-blue?style=for-the-badge" /> <img src="https://img.shields.io/badge/Google-Calendar-4285F4?style=for-the-badge&logo=googlecalendar&logoColor=white" /> </p> <p align="center"> <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square" /> <img src="https://img.shields.io/badge/Maintained-Yes-blue?style=flat-square" /> </p>
<h1>🚀 Overview</h1>

This project is an AI-powered automation workflow built using n8n, OpenAI, and Google Calendar.
Simply send a natural-language message like:

“Book a meeting tomorrow at 10 AM.”

…and the workflow automatically creates a properly-timed event in your Google Calendar.

This project helped me learn:

🔗 Workflow automation

🤖 AI Agents & system messages

🧩 JSON expressions

📅 Google Calendar API integrations

🛠 Troubleshooting AI tool pipelines

🧠 How It Works
1️⃣ Chat Trigger

The workflow starts when a new message is received.

2️⃣ AI Agent (The Brain 🧠)

The AI Agent uses OpenAI (gpt-4o-mini) to:

Understand your message

Extract date & time

Generate a meeting title

Decide whether to call the Calendar tool

It uses a dynamic system message to always know today’s date:

Today's date is {{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}

3️⃣ JSON Expressions

Instead of static times, the workflow uses:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}


This ensures the AI decides the final event timing, not n8n default values.

4️⃣ Google Calendar Tool

The tool creates the real event in your actual calendar.
If the time is free → event is added.
If not → AI can be extended to suggest alternatives.

🛠️ Tech Stack
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

🧪 Testing & Debugging

During development:

The event was created at wrong times

The Calendar node used current time instead of AI time

System message had fixed dates → wrong scheduling

These were fixed by:

Switching to $fromAI() JSON expressions

Making the system message dynamic

Reviewing AI Agent logs carefully

The final workflow now schedules correct events every time. 🎉

📂 Workflow Diagram (Simplified)
flowchart LR
    A[Chat Trigger] --> B[AI Agent]
    B -->|Parses Time| D[From AI Variables]
    D --> C[Google Calendar Tool]
    C --> E(Event Created)

📁 Files Included

My workflow.json — Importable n8n workflow

AI workflow.pdf — Full project explanation

README.md — This file

🧑‍💻 Setup Instructions
1. Import Workflow

Upload the provided JSON file into n8n.

2. Connect Credentials

Google Calendar

OpenAI (n8n free credits supported)

3. Start Workflow

Run the workflow and send messages like:

schedule a call tomorrow at 4pm

4. Watch Your Calendar Update Automagically ✨
🎯 Future Improvements

📆 Conflict detection (check existing events)

🔁 Support for recurring meetings

🤝 Multi-person scheduling

🧠 Add memory for user preferences

👩‍🎓 Author

Yukti Dave
AI automation enthusiast, learning to build smart workflows using n8n & OpenAI.

⭐ Support

If you like this project, please ⭐ star the repo — it motivates me to build more AI workflows!
