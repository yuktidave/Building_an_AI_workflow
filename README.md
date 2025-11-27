AI Calendar Scheduling Workflow (n8n + OpenAI + Google Calendar)

A fully automated workflow that uses AI to read natural-language messages and schedule events in Google Calendar — built using n8n, OpenAI, and Google Calendar API.

📌 About This Project

This project demonstrates how to build an AI-powered workflow using n8n, where a user can send a simple chat message like:

“Book a meeting tomorrow at 10 AM.”

…and the workflow automatically schedules the correct event in Google Calendar using AI intelligence.
This project was created to explore AI automation, tool integrations, and workflow engineering.
AI workflow

 and the workflow JSON you exported 

My workflow

.)

🚀 Features

Natural-language message input via n8n chat trigger

OpenAI-powered Chat Model (gpt-4o-mini)

Automatic time extraction (start/end time)

Google Calendar event creation

Real-time timezone awareness (Asia/Kolkata)

Fully no-code setup using n8n

🧠 How It Works
1. Chat Trigger Starts the Workflow

A user sends any message (“schedule a call for tomorrow at 3 PM”).
This triggers the workflow. (Page 4 of your PDF shows this clearly.) 

AI workflow

2. AI Agent Interprets the Message

The n8n AI Agent uses:

A system message

OpenAI's Chat Model

The system message includes the current date and time using:

{{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}


(Seen inside your workflow JSON systemMessage field.) 

My workflow

3. AI Extracts Required Fields

The AI parses:

start_time

end_time

summary

These values are passed through:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}



AI workflow

4. Google Calendar API Creates the Event

The Google Calendar node adds the event to your actual calendar.


AI workflow

🛠️ Tech Stack

n8n – AI workflow automation

OpenAI (gpt-4o-mini) – language understanding

Google Calendar API – event creation

JSON expressions – dynamic data mapping

🧩 Workflow Structure (Simplified)

When Chat Message Received

AI Agent

System message

Date handling

OpenAI Chat Model

Google Calendar Tool (Create Event)


My workflow

🧪 Testing & Troubleshooting

During testing, you identified issues with:

Wrong start/end time values

The tool using “current time” instead of AI-parsed times

Incorrect dates due to fixed system messages


AI workflow


These issues were fixed by:

Switching to {{ $fromAI(...) }} JSON expressions

Making the system message dynamic, not fixed

Ensuring proper timezone handling

🎉 Final Result

The final workflow successfully:

Interprets any natural-language date

Creates the correct event in Google Calendar

Adapts to daily date changes automatically


AI workflow

📂 Project Files

AI workflow PDF report – detailed explanation of the project (design, testing, challenges)


AI workflow

Workflow JSON – importable n8n workflow


My workflow

📝 How to Use

Import the provided .json workflow into n8n.

Connect:

Google Calendar credentials

OpenAI API (n8n free credits are supported)

Set your timezone (already configured as Asia/Kolkata).

Start the workflow.

Send a message like:

Book a meeting for tomorrow at 4 PM.


The event will appear in your Google Calendar.

⭐ Future Improvements

Add conflict detection (check existing calendar availability)

Support recurring events

Add memory for ongoing scheduling preferences

Multi-calendar support

👩‍💻 Author

Yukti Dave
A NextWork student learning automation and AI workflows.
