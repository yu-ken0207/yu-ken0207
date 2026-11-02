# Hi, I'm Ken (yu-ken0207) 👋

**English** | [繁體中文](README.zh-TW.md)

I mostly build AI agents: AI that gets real work done through tools, asks a person before changing any data, and is measured with test cases to see how well it does. I also build MCP servers, local model serving, and mobile apps.

## What I work on

- AI agents: AI that calls tools to get work done (checked before acting, confirmed by a person, undoable if wrong), several AIs discussing together, MCP servers with authentication and audit logs
- Evaluation: scenario scripts for testing agents; comparing how accurately different models call tools
- Local LLMs: Ollama, LM Studio, and OpenAI-compatible servers; keeping small models working within limited context (for example, condensing long chats into a summary)
- Vision and robotics: vision-language models that judge inspection images, robot navigation with ROS 2 / Nav2 in simulation, YOLO object detection
- Fine-tuning and serving: LoRA fine-tuning of Llama, 4-bit quantization, serving as an API with FastAPI
- Apps and backends: Expo / React Native (iPhone), Go (cross-platform desktop), Python

## Work projects (not open source)

**Inspection robot agent in simulation** (my main project)

- An LLM agent directs a mobile robot on patrol through a simulated site using MCP tools for navigation, taking pictures, and reporting incidents.
- A vision-language model judges what the camera sees. Inspection procedures (SOPs) are written as agent skills: give it a new SOP and the robot follows the new procedure, with no code changes.
- Evaluated with scenarios: a fallen person, a car crash with smoke, or boxes falling in a storage area, staged on different simulated sites, to see whether the robot notices and handles them according to the SOP.

## Open-source projects

| Project | Highlights |
|---|---|
| [local-chat](https://github.com/yu-ken0207/local-chat) | iPhone app ("Local AI") for chatting with the AI on your own computer. The AI can add calendar events and reminders: it checks first, shows a card for you to confirm, and can undo afterwards ([design](https://github.com/yu-ken0207/local-chat/blob/main/docs/design-phone-actions.md)). 25 everyday requests measure how accurately 5 local models call tools ([results](https://github.com/yu-ken0207/local-chat/blob/main/eval/tools/README.md)). Several AIs in one chat decide among themselves who speaks next ([design](https://github.com/yu-ken0207/local-chat/blob/main/docs/design-multi-agent.md)). Long chats are condensed into a summary automatically. 664 tests, [v1.0.0](https://github.com/yu-ken0207/local-chat/releases/tag/v1.0.0) |
| [local-ai-helper](https://github.com/yu-ken0207/local-ai-helper) | Desktop program in Go (Windows / Linux): phones pair by scanning a QR code and then use the AI on the computer; chats and tool calls are converted between Ollama and OpenAI-compatible servers automatically. Security: tokens are stored only as hashes, the admin page is open to the local machine only, and DNS rebinding attacks are blocked |
| [fastmcp-calculator-example](https://github.com/yu-ken0207/fastmcp-calculator-example) | Securing an MCP server: API key or bearer token auth, Host / Origin / client IP allowlists (works behind a reverse proxy), and an audit log entry with a trace ID for every tool call |
| [HuggingFaceTransformers_llama](https://github.com/yu-ken0207/HuggingFaceTransformers_llama) | Llama 3.1 served with FastAPI for robot task planning; callers can define their own tools in each request as JSON schemas |
| [LlamaLoRAFinetuner](https://github.com/yu-ken0207/LlamaLoRAFinetuner) | LoRA fine-tuning of Llama 3.1 (4-bit, Unsloth): three small models trained on household tasks from ALFWorld to break down tasks and plan steps |
| [VideoFinder](https://github.com/yu-ken0207/VideoFinder) | Type what to look for, and a local vision model checks the video second by second to find when it first appears |

## Tools I use

Python, TypeScript, Go, React Native / Expo, PyTorch, Hugging Face Transformers, Unsloth, Ollama, MCP (FastMCP), FastAPI, ROS 2, Docker
