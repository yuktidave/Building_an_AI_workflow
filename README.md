<img src="https://i.ibb.co/3yW0d8Q/gradient-header.png" width="100%" />
🎉 AI Calendar Scheduling Workflow
Automate your Google Calendar using n8n + OpenAI
<p align="center"> <img src="https://img.shields.io/badge/BUILT%20WITH-n8n-FE6E00?style=for-the-badge&logo=n8n&logoColor=white" /> <img src="https://img.shields.io/badge/OpenAI-gpt--4o--mini-412991?style=for-the-badge&logo=openai&logoColor=white" /> <img src="https://img.shields.io/badge/Google%20Calendar-Automation-4285F4?style=for-the-badge&logo=googlecalendar&logoColor=white" /> </p>
🌈 Demo
<p align="center"> <img src="https://i.ibb.co/D8kbHdq/demo-gif.gif" width="80%" /> </p>
🟣 Overview

This project is a fully automated AI workflow built using:

⚙️ n8n

🤖 OpenAI

📅 Google Calendar

Send a message like:

“Book a meeting tomorrow at 10 AM.”

…and the workflow magically creates a properly timed event in Google Calendar.

💜 What I Learned

🔗 Workflow automation

🧠 AI Agents & system messages

🧩 JSON expressions

📅 Google Calendar API integration

🛠 Debugging & analysing tool logs

💎 How It Works
🟦 1️⃣ Chat Trigger

A message starts the workflow instantly.

🟩 2️⃣ AI Agent — The Brain 🧠

The AI Agent (gpt-4o-mini):

✔ Understands your message
✔ Extracts date & time
✔ Generates the meeting title
✔ Decides when to call the Calendar tool

🟪 Dynamic System Message
Today's date is {{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}


This ensures the AI always knows the correct current date.

🟧 3️⃣ JSON Expressions

Instead of static values:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}


These pull the exact timing the AI decides.

🟥 4️⃣ Google Calendar Tool

The event is created inside your calendar with complete accuracy.

🌟 Tech Stack
Tool	Purpose
🧩 n8n	No-code workflow engine
🤖 OpenAI gpt-4o-mini	AI reasoning + extraction
📅 Google Calendar API	Event creation
🧮 JSON expressions	Dynamic fields
🧠 AI Agent	Decision orchestration
📊 Workflow Diagram
flowchart LR
    A[Chat Trigger] --> B[AI Agent]
    B -->|Extract Times| C[JSON Expressions]
    C --> D[Google Calendar Tool]
    D --> E[Event Created Successfully 🎉]

🧪 Testing & Debugging
❌ Problems Found

Wrong time being used

System message showing static date

Calendar using “now” instead of AI-parsed time

✔ Fixes Applied

Used $fromAI() expression

Turned system message into a dynamic expression

Verified logs via AI Agent node

🎉 Final Result

Your workflow perfectly schedules events with AI-chosen timings.

📦 Setup Instructions
1️⃣ Import the Workflow

Upload the .json file into n8n.

2️⃣ Add Credentials

Google Calendar

OpenAI (n8n free credits supported)

3️⃣ Run the Workflow

Send a message like:

schedule a call tomorrow at 4pm

4️⃣ Enjoy ✨

Your calendar event appears automatically!

🌱 Future Upgrades

📆 Calendar conflict detection

🔁 Recurring events

🧠 Memory of user preferences

🤝 Multi-participant scheduling

✨ Screenshots
<p align="center"> <img src="https://i.ibb.co/t2ChdQQ/sample-ui.png" width="80%" /> </p>
👩‍💻 Author

Yukti Dave
AI Workflow Enthusiast
n8n | OpenAI | Automations | Calendar APIs

⭐ If you found this project helpful, please star this repo!

It motivates me to build more beautiful AI workflows ✨💜
