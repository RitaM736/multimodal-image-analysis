# Multimodal Image Analysis with Llama 4

My first hands-on AI engineering project using **Meta Llama 4 Maverick** through **IBM watsonx.ai**.

This project demonstrates how a multimodal Large Language Model can analyze images and answer questions about their content.

## Project Overview

The application sends an image together with a natural-language question to the Llama 4 Maverick multimodal model.

The model can then analyze the image and generate a response based on the user's question.

### Examples of tasks

* 🖼️ Image description
* 👤 Object and clothing identification
* 🌦️ Scene and weather analysis
* 📝 Text recognition from images

## Technologies Used

* **Python**
* **IBM watsonx.ai**
* **Meta Llama 4 Maverick**
* **Requests**
* **Base64 Encoding**
* **Multimodal LLM**

## How It Works

The project follows these main steps:

1. Load images from URLs.
2. Download the images using Python `requests`.
3. Encode the images into Base64.
4. Create a multimodal message containing both text and an image.
5. Send the message to Llama 4 Maverick through IBM watsonx.ai.
6. Receive the model's response.
7. Extract and display the generated answer.

### Multimodal Message

The model receives both the user's question and the image:

```python
messages = [
    {
        "role": "user",
        "content": [
            {
                "type": "text",
                "text": assistant_prompt + user_query
            },
            {
                "type": "image_url",
                "image_url": {
                    "url": "data:image/png;base64," + encoded_image
                }
            }
        ]
    }
]
```

## Example Queries

The project tests the model with different types of questions:

```text
"Describe this image"

"What is the person wearing?"

"What weather condition is shown in this image?"

"What is the serving size listed on this label?"
```

These examples demonstrate how the same multimodal model can be used for different image-understanding tasks.

## Project Structure

```text
multimodal-image-analysis/
│
├── image_analysis.py
├── requirements.txt
├── README.md
└── .gitignore
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/multimodal-image-analysis.git
cd multimodal-image-analysis
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## API Configuration

The project uses an IBM watsonx.ai API key.

For security, the API key should **not** be stored directly in the source code.

Set it as an environment variable:

```bash
export IBM_API_KEY="your_api_key"
```

Then access it from Python:

```python
import os

api_key = os.getenv("IBM_API_KEY")
```

**Never commit your API key or other credentials to GitHub.**

## What I Learned

This project helped me understand the fundamentals of working with multimodal AI models, including:

* How multimodal LLMs process images and text
* How to interact with an LLM through an AI SDK
* How to encode image data using Base64
* How to structure multimodal chat messages
* How prompts influence model responses
* How to extract responses from an LLM API
* How to work with Python packages and APIs

## Future Improvements

Some possible next steps for this project are:

* Add support for user-uploaded images
* Build a web interface
* Create a FastAPI backend
* Add conversation history
* Add RAG capabilities
* Integrate external tools
* Develop an AI agent capable of performing multi-step tasks

## Project Status

**Completed — First hands-on multimodal AI engineering project.**
