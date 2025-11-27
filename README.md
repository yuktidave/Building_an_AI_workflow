🌅 AI Calendar Scheduling Workflow
Automate your Google Calendar using n8n + OpenAI
🎬 DEMO PREVIEW
<img src="https://i.ibb.co/D8kbHdq/demo-gif.gif" width="80%"/>
🟣 OVERVIEW

This is a fully automated AI workflow built using:

⚙️ n8n

🤖 OpenAI

📅 Google Calendar

Send a message like:

“Book a meeting tomorrow at 10 AM.”

✔ The AI understands
✔ Extracts the timing
✔ Creates the event in your calendar

💜 WHAT I LEARNED
🔗 Workflow automation
🧠 AI Agents & system messages
🧩 JSON expressions
📅 Google Calendar API integration
🛠 Debugging & analysing tool logs
🌈 HOW IT WORKS
🔵 1. CHAT TRIGGER

This is what starts the workflow when you send a message.

🟢 2. AI AGENT — THE BRAIN 🧠

The AI Agent (gpt-4o-mini):

✔ Understands your message

✔ Extracts date & time

✔ Generates a meeting title

✔ Decides when to call the Calendar tool

🔧 Dynamic System Message
Today's date is {{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}


This ensures the AI always knows the current date.

🟣 3. JSON EXPRESSIONS

Instead of static values:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}


These dynamically pull the exact timing the AI extracts.

🔴 4. GOOGLE CALENDAR TOOL

This is the final step where the event gets created.

🛠 TECH STACK
Tool	Use
⚙️ n8n	Workflow automation
🤖 OpenAI	AI reasoning
📅 Google Calendar	Event creation
🧩 JSON expressions	Dynamic values
🧪 TESTING & FIXES
❌ Initial Problems

Wrong time used

Calendar tool using “current time”

System message not dynamic

✔ Fixes

Added $fromAI()

Updated system message to dynamic expression

Checked AI agent logs

🎉 Result

The workflow now creates events accurately every single time.

🧬 WORKFLOW DIAGRAM
flowchart LR
    A[Chat Trigger] --> B[AI Agent]
    B -->|Extracts Date/Time| C[JSON Expressions]
    C --> D[Google Calendar]
    D --> E[📅 Event Created]

⚡ SETUP
1️⃣ Import the workflow .json
2️⃣ Add Google Calendar + OpenAI credentials
3️⃣ Activate workflow
4️⃣ Send a message → event created ✨
🌱 FUTURE IMPROVEMENTS

📆 Conflict checking

🔁 Recurring events

🤝 Multi-user scheduling

🧠 AI memory

👩‍💻 AUTHOR

Yukti Dave
AI workflow engineer in progress ✨

⭐ If you liked this project, please star the repository!
