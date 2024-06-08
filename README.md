**GenAI-Powered Search "using your own Data" Demo**

This repo contains artifacts & Python programs that can be use to ask a question regarding the data that was ingested and index into Elasticsearch Cloud and query them using a Retrieval Augmented Generation (RAG) demo app.

Pre-requisite

ElasticSearch Setup
1. 

Quickstart 
1. Clone this repo
2. Enable python virtual environment

   ```source .venv/bin/activate```

3. Ensure dependencies are installed:

```pip3 install -r requirements.txt```

4. Make a copy of config.ini, rename it to something memorable, and fill out the required settings (note - you can choose Azure or Local LLM):

```
[chat]
OrganisationName = Orgname #something that will be displayed on your web app
OrganisationCode = orgname-index #index name in ES

[elastic]
ElasticCloudId = Elastic cloud ID to send output to
ElasticPassword = Elasticsearch password to use (optional if using api key)

[gpt.openai]
ApiKey = ChatGPT Key
Model = gpt-4o
Temperature = 0
```

5. To start the application, run the following command and substitute in your custom config.toml.

```streamlit run genai-intel-demo.py```
