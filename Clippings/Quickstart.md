---
title: "Quickstart"
source: "https://docs.browser-use.com/quickstart"
author:
  - "[[Browser Use]]"
published:
created: 2025-06-23
description: "Start using Browser Use with this quickstart guide"
tags:
  - "clippings"
---
## Prepare the environment

Browser Use requires Python 3.11 or higher.

First, we recommend using [uv](https://docs.astral.sh/uv/) to setup the Python environment.

```
uv venv --python 3.11
```

and activate it with:

```
# For Mac/Linux:

source .venv/bin/activate

# For Windows:

.venv\Scripts\activate
```

Install the dependencies:

```
uv pip install browser-use
```

Then install playwright:

```
uv run playwright install
```

## Create an agent

Then you can use the agent as follows:

agent.py

```
from langchain_openai import ChatOpenAI

from browser_use import Agent

from dotenv import load_dotenv

load_dotenv()

import asyncio

llm = ChatOpenAI(model="gpt-4o")

async def main():

    agent = Agent(

        task="Compare the price of gpt-4o and DeepSeek-V3",

        llm=llm,

    )

    result = await agent.run()

    print(result)

asyncio.run(main())
```

## Set up your LLM API keys

`ChatOpenAI` and other Langchain chat models require API keys. You should store these in your `.env` file. For example, for OpenAI and Anthropic, you can set the API keys in your `.env` file, such as:

.env

```
OPENAI_API_KEY=

ANTHROPIC_API_KEY=
```

For other LLM models you can refer to the [Langchain documentation](https://python.langchain.com/docs/integrations/chat/) to find how to set them up with their specific API keys.

Quickstart - Browser Use