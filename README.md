# vibe-neuron
Flask-based AI neuron for Bittensor — serves AI voice agent and tool queries
Voice Agent Neuron for Bittensor
Description

This repository contains a Python neuron designed for Bittensor. It runs a Flask server that responds to AI queries about tools, resources, and voice agents. The neuron can be used locally or in a subnet.

It is lightweight, easy to extend, and does not require the private Vibe library.

Features

Serve AI tool recommendations via HTTP requests.

Query AI voice agents programmatically.

Fully local development; works on macOS, Linux, or Windows.

Flask-based for easy integration with other projects.

Requirements

Python 3.9+

Flask

Requests (for querying the neuron)

Install dependencies:

pip install flask requests

Quick Start

Clone the repository:

git clone git@github.com:<your-username>/<repo-name>.git
cd <repo-name>


Run the neuron:

python voice_agent_neuron.py


Query the neuron via HTTP:

import requests

resp = requests.post(
    "http://127.0.0.1:5000/query",  # adjust port if needed
    json={"prompt": "give me top AI voice agents"}
)
print(resp.json())

Example Response
{
  "timestamp": "2025-09-26T22:37:59.192944",
  "tools": [
    {"name": "ElevenLabs", "url": "https://elevenlabs.io/", "description": "Text-to-speech with lifelike voices"},
    {"name": "Murf.ai", "url": "https://murf.ai/", "description": "AI voice generator for presentations"}
  ]
}

How to Extend

Add more AI tools or voice agents to self.tools.

Implement more endpoints in Flask for additional functionality.

Integrate with Bittensor subnet by replacing local Flask logic with neuron forwarding functions.

License

MIT License
