# sn-chatGPT

Custom application on the ServiceNow platform integrated with ChatGPT. Specified model used can be updated in the application properties but defaults to gpt-3.5-turbo.

Purpose:
Play around with ChatGPT APIs.

Features:
Submit a prompt and receive a response from ChatGPT independently or in the context of a conversation.

Pre-Reqs:
1. The 'Flow Designer Action Step - Payload Builder' plugin is installed in the target instance. It is used in the flows.
2. Create an API Key credential record (api_key_credentials) with an API key from OpenAPI related to a paid account.
*If not done the API will fail
3. Create a connection record (http_connection) to reference the API Key credential record and the exisiting Connection Alias record (sys_id = a6a1ca7b87e625101fd74336cebb3514). The Connection URL should be set to: https://api.openai.com/v1/
4. Update system properties (ChatGPT > ChatGPT App Properties)

Validation:
1. Go to ChatGPT > Prompts > Create Prompt
2. Type in a prompt and save
3. Click 'Ready for Processing'
4. Validate the State moves to 'Complete' with a response. If the state is 'Error' troubleshoot by looking at the generated task with the API error.
