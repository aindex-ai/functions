# 🌀 aindex - functions

Reusable AI functions

### functions

[get_current_weather](https://github.com/aindex-ai/functions/blob/main/functions/get_current_weather.json)

## Get Started

### install aindex
`pip install aindex`

### retrieve the function by name
```python
import aindex as a

# a.function_name_here
a.sum
```

### use functions on OpenAI api

Use aindex to retrieve the function by name:
a.function_name_here

```python
import requests
import json

# Use aindex to retrieve the function by name
import aindex as a

# Your OpenAI API key
OPENAI_API_KEY = 'your_api_key'

headers = {
    'Content-Type': 'application/json',
    'Authorization': f'Bearer {OPENAI_API_KEY}'
}

data = {
  "model": "gpt-3.5-turbo-0613",
  "messages": [
    {"role": "user", "content": "What is the weather like in Boston?"}
  ],
  "functions": [
    a.get_current_weather
  ]
}

response = requests.post(
    'https://api.openai.com/v1/chat/completions', 
    headers=headers, 
    data=json.dumps(data)
)

print(response.json())
```
