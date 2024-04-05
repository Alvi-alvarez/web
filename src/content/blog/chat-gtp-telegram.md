---
title: 'Chat GTP Telegram'
description: 'He creado un bot para utilizar ChatGPT en Telegram, y lo he alojado en AWS'
pubDate: 'Apr 04 2023'
heroImage: 'chatgpt-telegram.webp'
---

**Update: 4/5/20204**

Un año después, es posible que una instancia de ChatGPT ya no sea tan atractiva como parecía antes. En este momento, optaría por Mistral o Llama 7B, alojados localmente o en algún servicio en la nube como AWS, Google Cloud, entre otros.

---

He creado un bot para utilizar ChatGPT en Telegram, y lo he alojado en AWS.

**->** [Repositorio](https://github.com/Alvi-alvarez/ChatGPT-Telegram-Bot-with-AWS-Lambda)

# ChatGPT Telegram Bot with AWS Lambda

ChatGPT on Telegram by utilizing the services of AWS Lambda, S3, and API Gateway.

# Features

- [X] API support
- [X] Memory

# Initial Setup

1. Create an [OpenAI account](https://openai.com/api/) and [get an API Key](https://platform.openai.com/account/api-keys).
2. Create an [AWS account](https://aws.amazon.com/es/).
3. Setup your Telegram bot. You can follow [this instructions](https://core.telegram.org/bots/tutorial#obtain-your-bot-token) to get your token.
4. Create your Lambda service, choose Python 3.9
5. Create a env and install requirements.txt
5. put all content of lib/site-packages in a zip file with lambda_funtion.py
6. Create a S3 bucket
7. Create a Create a REST API and deploy
8. Connect Telegram to your API Gateway
    ```
    $ curl --data "url=<INVOKE_URL>" "https://api.telegram.org/bot<ACCESS_TOKEN>/setWebhook"
    ```
    - Replace `<ACCESS_TOKEN>` with your Telegram HTTP API access token obtained in the first step
    - Replace `<INVOKE_URL>` with your endpoint
    You should get back a response similar to this:
    ```
    $ {"ok":true,"result":true,"description":"Webhook was set"}
    ```
9. setup the environment variables:
    - BUCKET_TOKEN: bucket name
    - OPENIA_KEY: OpenAI key
    - PERSINALITY: the system message for the AI
    - TELEGRAM_TOKEN: Telegram bot token
    - USER_ID: your telegram user ID
10. upload the zip file to your Lambda service

I skipped a thousand steps, you have to give permissions to lambda to be able to write files and some other things that I missed :sweat:.
soon I will add what is missing

## refs
- https://github.com/codin-eric/lambda-telegram
- https://www.youtube.com/watch?v=Ic7trVdsrv4
- https://platform.openai.com/docs/guides/chat
- https://github.com/franalgaba/chatgpt-telegram-bot-serverless