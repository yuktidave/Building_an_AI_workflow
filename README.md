# Building an AI Workflow — n8n + OpenAI + Google Calendar

<small>A clean, attractive README for the AI workflow project — quick to scan, with a large title and compact supporting text.</small>


(Replace assets/header.png with your real header image — a soft rounded photo like the one in your project PDF looks great.) 

AI workflow

✨ What this project does

A lightweight n8n-based AI workflow that accepts chat messages and schedules events in Google Calendar using an AI agent (OpenAI). It demonstrates integrating triggers, an AI model, and a Calendar tool to automate scheduling. 

AI workflow

🚀 Features (small notes)

Trigger: chat message → starts the workflow.

AI Agent: interprets user intent and extracts start_time / end_time.

Google Calendar tool: creates events only when calendar is free.

Troubleshooting: uses JSON expressions and dynamic system messages to pass correct dates/times. 

AI workflow

📁 Project files

AI workflow.pdf — project writeup with screenshots and lessons learned (see pages for system message / JSON expression examples). 

AI workflow

My workflow.json — exported n8n workflow (nodes, connections, system message and calendar node config). Use to import directly into n8n. 

My workflow

🧩 Quick setup (small and simple)

Clone this repo.

Add a header image to assets/header.png (optional).

Import My workflow.json into n8n (Workflows → Import). 

My workflow

Add credentials:

OpenAI / n8n free credits (or your API key).

Google Calendar OAuth2 for the account you want to book events in.

Activate the workflow and test by sending a chat message:
Book a meeting tomorrow at 10 AM for 30 minutes.

🛠️ Notes on important pieces (compact)

System message: use an expression that injects the current date in the correct timezone (example in JSON). This prevents wrong-date scheduling. 

My workflow

Calendar times: make start and end fields read from the AI response using JSON references like {{$fromAI('start_time')}}. 

AI workflow

Debugging: inspect agent logs and the Calendar node inputs when times are wrong — logs show what the AI passed to the tool. 

AI workflow

💡 Demo & visuals

Add a short demo GIF assets/demo.gif showing: chat → AI response → calendar event created.

Consider a faint colored banner or badge row at the top (shields.io badges) to make the README pop.

⚠️ Troubleshooting (tiny checklist)

If events are created at the wrong time:

Ensure the system message is dynamic (not fixed) and uses the proper timezone. 

My workflow

Confirm the agent returns start_time/end_time in ISO format and the Calendar node uses {{$fromAI('...')}}. 

AI workflow

🧾 License & Contact

License: MIT — feel free to reuse and improve.
Author: Yukti Dave — found more about this project in AI workflow.pdf. 
