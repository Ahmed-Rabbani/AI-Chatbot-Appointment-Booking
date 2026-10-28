# AI Chatbot & Appointment Booking System

An AI-powered website chatbot built with **n8n**, **Google Gemini**, and **Google Calendar**. It lets website visitors chat with an AI assistant, ask questions, check calendar availability, and book appointments through a conversational interface.

> **Project status:** Demo link is not available yet. Setup details may need to be adapted to the exact frontend and n8n workflow included in this repository.

## Features

- **AI-powered chat:** Visitors can interact with the chatbot and ask questions.
- **Appointment availability:** Check availability using the connected Google Calendar integration.
- **Appointment booking:** Support appointment booking through the chatbot workflow.
- **Website integration:** Send messages from the frontend to an n8n webhook and display the returned response.
- **Workflow-based automation:** Manage the chatbot logic using an n8n workflow.
- **Gemini integration:** Use Google Gemini as the AI model for the agent.

## How It Works

1. A visitor sends a message through the website chat interface.
2. The frontend sends the message to the configured n8n webhook.
3. The n8n workflow passes the request to the AI Agent powered by Google Gemini.
4. When the request involves scheduling, the agent uses the connected Google Calendar tool according to its configuration.
5. The workflow returns a response to the frontend.
6. The chat interface displays the response to the visitor.

## Workflow Overview

```text
Website Chat Interface
        |
        v
    n8n Webhook
        |
        v
 AI Agent (Gemini)
        |
        +---- Google Calendar Tool
        |       |
        |       +-- Check availability
        |       +-- Book appointments
        |
        v
 Respond to Webhook
        |
        v
Display response in website chat
```

The exact node names and connections may vary depending on the exported workflow included in this repository.

## Technology Stack

- **n8n** — Workflow automation and orchestration
- **Google Gemini** — AI model
- **Google Calendar** — Calendar availability and appointment operations
- **HTML, CSS, and JavaScript** — Website frontend, if these are the technologies used by the included frontend
- **Webhook** — Communication between the website and n8n

## Repository Structure

The following is a suggested structure. Adjust the paths to match the actual files committed to the repository.

```text
ai-chatbot-appointment-booking/
├── README.md
├── LICENSE
├── .gitignore
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── n8n/
│   └── chatbot-workflow.json
└── assets/
    └── preview.png
```

## Prerequisites

Before setting up the project, prepare:

- An n8n instance
- A Google Gemini API key and a Gemini model available to your account
- A Google account and Google Calendar access
- The frontend files included in this repository
- A way to configure the frontend with your n8n webhook URL

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/Ahmed-Rabban/ai-chatbot-appointment-booking.git
cd ai-chatbot-appointment-booking
```

If your repository uses a different name or URL, replace the example URL above with your repository's actual clone URL.

### 2. Set up the n8n workflow

1. Open your n8n instance.
2. Import the exported workflow JSON file from the `n8n/` directory, if included.
3. Open the AI Agent configuration and select/configure Google Gemini.
4. Add your Gemini credentials using n8n's credential manager.
5. Configure the Google Calendar integration and authorize the Google account that should manage appointments.
6. Review the AI Agent instructions and calendar tool settings.
7. Check the webhook and response configuration.
8. Test the workflow before activating it.

The exact credential fields and node settings depend on the n8n nodes and versions used in the workflow.

### 3. Configure the frontend

1. Open the frontend files.
2. Locate the setting or code responsible for sending chat messages to n8n.
3. Set it to your webhook URL.
4. Ensure the frontend request format matches the fields expected by the webhook.
5. Ensure the frontend handles the response format returned by the workflow.
6. Run the frontend using your chosen local web server or hosting method.

Do not expose Gemini API keys, Google credentials, or other private secrets in frontend JavaScript.

### 4. Test the chatbot

Test the following scenarios before using the chatbot with real visitors:

- Ask a general question.
- Ask about appointment availability.
- Request an appointment at an available time.
- Request a time that is unavailable.
- Submit incomplete appointment details.
- Check how the workflow responds if the calendar or AI service fails.

Confirm that an appointment was actually created in Google Calendar before treating a booking as successful.

## Configuration Notes

You will need to configure these values or integrations in your own environment:

- n8n webhook URL
- Google Gemini credentials and selected model
- Google Calendar credentials and target calendar
- AI Agent instructions
- Calendar availability and booking rules
- Frontend request and response handling

Exact environment-variable names are not specified here because they depend on the implementation in the repository.

## Security

- Store API keys and OAuth credentials in n8n's credential manager or an appropriate secrets manager.
- Never commit API keys, OAuth tokens, passwords, or private configuration files.
- Do not put private credentials in frontend code.
- Protect webhook endpoints with appropriate authentication or access controls where supported.
- Validate incoming requests and handle errors safely.
- Collect and retain only the personal information required for appointment scheduling.
- Test calendar permissions and booking behavior before production use.

## Troubleshooting

**The chatbot does not respond**
- Confirm the n8n workflow is active when using its production webhook.
- Check the webhook URL and request format.
- Review the n8n execution log for errors.

**Gemini requests fail**
- Verify the credential configuration and selected model.
- Check that the API key is valid and that the account has access to the selected model.
- Review the n8n execution details for the error.

**Calendar operations fail**
- Confirm Google Calendar authorization and permissions.
- Check that the correct calendar is selected.
- Review availability and booking settings in the workflow.

**The frontend shows an empty or unexpected response**
- Compare the response returned by n8n with the response format expected by the frontend.
- Check browser developer tools and the n8n execution log.

## Demo

A public demo link is not available yet.

## License

This project is intended to use the **MIT License**. Include a `LICENSE` file containing the MIT License text and the appropriate copyright holder before distributing the repository under that license.

## Author

**Ahmed Rabbani**  
n8n Automation Developer

- **GitHub:** [Ahmed-Rabban](https://github.com/Ahmed-Rabban)
- **LinkedIn:** [Ahmed Rabbani](https://www.linkedin.com/in/ahmed-rabbaniofficial)
- **YouTube:** [Ahmed Automates](https://www.youtube.com/@Ahmed-Automates)

---

If you find this project useful, feel free to explore the workflow and adapt it to your own use case, subject to the project's license and the terms of the services you connect.
