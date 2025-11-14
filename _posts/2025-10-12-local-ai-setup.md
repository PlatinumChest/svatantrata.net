---
layout: post
title: "Setup of Local AI with Internet Access"
---

This week I decided that I wanted to setup a local AI on my desktop which has a NVIDIA 3090ti, 32GB DDR4 and an Intel i9-13900k running Fedora Workstation. My plan is to run this on my website which is now reachable at chatbot.svatantrata.net using a cloudflare tunnel. 
In addition to that I will be giving the AI models internet access using SearXNG so that I don't need an API from another browser. 
This was my plan in ordered steps:

- Step 1: Create a Podman network for my pods. Podman uses Docker commands but runs more efficiently when using Fedora Workstation.
- Step 2: Install Ollama and OpenWebUI onto my desktop. This is to have the models running.
- Step 3: Pull a 7B model to my computer. On my desktop this should be near instant reference and I can pinpoint any issues.
- Step 4: Fix GPU passthrough problems. The model ran on CPU and RAM at first making it very slow so I had to fix the GPU issue.
- Step 5: Install SearXNG. Preparing the web browser for the AI.
- Step 6: Allow JSON format on SearXNG. The AI requires this to do "web searches."
- Step 7: Connect and test internet access. Making sure everything works.
- Step 8: Create the tunnel and token. Using the cloudflare zero trust dashboard I needed to make the tunnel for my site and get the token.
- Step 9: Connect tunnel and test. Connected the tunnel to my network and tested it on a network apart from my and it functioned.
- Step 10: Add peers. For the moment I added one of my friends to the list since he wants to use my locally run models.

For the moment I installed 3 AI Assistants with the following names:

- General AI: Llama 3 8B
- Powerful General AI: GPT-OSS 20B
- Powerful Coding AI: Llama 34B

These models ran very well and fast and I was impressed the 34B Coding Assistant could fit into my 24GB of VRAM on my GPU to not sacrifice speeds. 
Quite a bit of troubleshooting was required here but in the end everything worked as planned.
