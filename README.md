**GenAI-Powered Search "using your own Data" Demo**

This repo contains artifacts & Python programs that can be use to ask a question regarding the data that was ingested and index into Elasticsearch Cloud and query them using a Retrieval Augmented Generation (RAG) demo app.

Pre-requisite

ElasticSearch Setup

1. Visit the Elastic Cloud Trial registration page at https://cloud.elastic.co/registration/ and register a new trial.
   ```
      Name: your org 
      Cloud Provider: [any]
      Region: [any Australian region]
      Hardware profile: CPU Optimized OR CPU Optimized ARM
      Version: latest
   ```
2. Verify your deployment and make sure you have the following deployment

  ```
   - 3 Availability Zones
   - 2 Elasticsearch data nodes
   - 1 Elasticsearch tiebreaker node - 1 Enterprise Search node
   - 1 Integration Server node
   - 1 ML node
  ```

3. Now it is time to ingest the data from your selected website.
    
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
