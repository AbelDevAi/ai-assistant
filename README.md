This repository contains the core workflow for a simple AI assistant built with n8n.

## MAX Workflow

This workflow acts as the central brain, orchestrating different tools and services to **accept and respond to user requests via Telegram with both text and voice**, perform internet searches, manage a Google Calendar, and more, all while remembering past conversations.

* n8n
* OpenAI
* Telegram API
* Air Table
* SerpAPI
* PineCone vectorStore
* Google sheets
* Google Calendar
* Gmail
* (Add any other main services you remember, like Airtable, Google Sheets, SerpAPI, etc.)

  ## Telegram Workflow (Telegram.json)

This workflow is responsible for handling communication with users via Telegram. It listens for new messages sent to your Telegram bot, forwards them to the "MAX" workflow for processing, and sends the AI assistant's responses back to the user on Telegram (either as text or voice).


  ## Google Calendar tool Workflow

This workflow provides a set of tools to manage Google Calendar events, including creating, reading, updating, deleting, and modifying reminders. It's designed to be used by the "MAX" workflow.

## Installation

To use these workflows, you will need to:

1.  Install n8n.
2.  Import the `MAX.json` and `Gestor_Google_Calendar.json` files into your n8n instance.
3.  Configure the necessary credentials for each of the services listed under "Technologies Used" in the n8n credentials settings.

4. ## Basic Usage

To interact with the AI assistant, send a message to your Telegram bot. The "MAX" workflow will process your request and respond accordingly, potentially using the various tools integrated. For example, you could ask it to:

* "What's the weather like in Lugo?" (using SerpAPI)
* "Add an event to my calendar for tomorrow at 10 AM called 'Meeting with John'." (using Gestor Google Calendar)
* "Remind me in 30 minutes." (using Gestor Google Calendar)

## Important Considerations / Configuration Notes

* **Google Sheets Integration:** The "MAX" workflow includes a node for interacting with Google Sheets. Please note that this node is currently configured to connect to a specific Google Sheet used for internal data logging. **To use this functionality, you will need to:**
    * Have a Google account with Google Sheets enabled.
    * Create your own Google Sheet where you want the data to be logged.
    * **Crucially, you will need to reconfigure the "Google Sheets" node in the "MAX" workflow with your own Google Sheets credentials and specify the correct Spreadsheet ID and Sheet Name.** Instructions on how to set up Google Sheets credentials in n8n can be found in the official n8n documentation.

* **Other Service Credentials:** Similarly, ensure you have configured your own API keys and credentials for all the other services used in the workflows (Telegram, OpenAI, Airtable, SerpAPI, Google Calendar, Gmail, Pinecone). The workflows will not function correctly without these valid credentials.
