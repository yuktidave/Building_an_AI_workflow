🌟 AI Calendar Scheduling Workflow

Automated workflow built using n8n, OpenAI, and Google Calendar to instantly schedule events based on natural-language messages.

📊 Project Highlights

AI-Powered Scheduling
AI interprets user messages to extract date, time, and meeting details.

Google Calendar Integration
Automatically creates events in your personal calendar with accurate timing.

Dynamic Date Handling
System message passes today’s date dynamically using Asia/Kolkata timezone.

JSON Expression Mapping
Ensures AI-parsed start_time and end_time are correctly passed to the Calendar tool.

Trigger-Based Automation
Workflow starts when a new chat message is received.

AI Agent Logic
Understands intent → extracts date/time → decides when to call the Calendar tool.

📁 Files in This Repository
├── My workflow.json          # Importable n8n workflow
├── AI workflow.pdf           # Full project explanation
└── README.md                 # Project documentation

🧠 How the Workflow Works
1. Chat Trigger

Starts the workflow whenever a user sends a message.

2. AI Agent

Uses gpt-4o-mini to:

Understand the natural-language command

Extract date and time

Generate meeting titles

Decide whether to call Google Calendar

Dynamic System Message
Today's date is {{DateTime.now().setZone('Asia/Kolkata').toFormat('dd LLL yyyy HH:mm:ss')}}

3. JSON Expressions

Used to pass AI-generated values:

={{ $fromAI('start_time') }}
={{ $fromAI('end_time') }}

4. Google Calendar Tool

Creates the actual calendar event with AI-provided timing.

📙 Dataset / Tools Used

n8n – Workflow orchestration

OpenAI Chat Model – Understanding human commands

Google Calendar API – Event creation

JSON expressions – Dynamic data mapping

AI Agent – Decision making + tool calling

🧪 Testing & Troubleshooting

Initial issues:

Wrong time added

System message using fixed date

Calendar defaulting to current time

Fixes implemented:

Added $fromAI() mapping

Converted system message into a dynamic expression

Analyzed Agent logs for parameter flow

Final result:

Workflow now schedules accurate events every time.

🛠 Skills & Concepts Learned

AI workflow automation

Setting up AI Agents in n8n

Dynamic system prompts

JSON expressions

Google Calendar API integration

Debugging agent logs & node setups

Understanding workflows vs. agents

🚀 Setup Instructions

Import My workflow.json into n8n

Connect:

Google Calendar credentials

OpenAI API (free n8n credits supported)

Activate the workflow

Send a message like:

Book a meeting tomorrow at 4 PM


Event appears in your Google Calendar ✨

🌱 Future Enhancements

Calendar availability conflict detection

Recurring event support

Preference-based scheduling (AI memory)

Multi-user event creation

👩‍💻 Author

Yukti Dave
AI automation learner — building intelligent workflows using n8n & OpenAI
