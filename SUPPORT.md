

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:4A00E0,100:8E2DE2&height=220&section=header&text=FreeAiApiProxy&fontSize=75&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Unified%20Access%20To%20The%20Worlds%20Best%20Ai%20Models&descAlignY=55&descSize=20)

<div align="center">

![Version](https://img.shields.io/badge/version-2.8.4-8E2DE2?style=for-the-badge&logo=git&logoColor=white)
![Downloads](https://img.shields.io/badge/downloads-81.4K-4A00E0?style=for-the-badge&logo=download&logoColor=white)
![License](https://img.shields.io/badge/license-Apache_2.0-F9D423?style=for-the-badge&logo=apache&logoColor=black)
![Platform](https://img.shields.io/badge/platform-linux%20%7C%20macos%20%7C%20windows-E10098?style=for-the-badge&logo=linux&logoColor=white)

</div>

<img width="1667" height="943" alt="28849501-f5a1-4d31-a00d-b33d7dc9eb4d" src="https://github.com/user-attachments/assets/ceb28154-5830-4e78-badb-b626f28d78a1" />

---

## 🌐 Why FreeAiApiProxy?

The AI landscape is fragmented. Every major provider — OpenAI, Anthropic, Google, Meta, and Mistral — uses a different API structure, rate limit policy, and authentication scheme. Juggling five different SDKs, managing multiple API keys, and rewriting your integration logic every time a new model drops is exhausting and inefficient.

**FreeAiApiProxy** solves this chaos by providing a single, unified gateway to dozens of AI models. It acts as an intelligent router and proxy that speaks a standardized API format, translating your requests on the fly to the underlying providers. Whether you're building a chatbot, an automated content pipeline, or a complex multi-agent system, this tool lets you swap models with a single line of configuration — no code rewrites, no vendor lock-in.

Built for developers by developers, the proxy is engineered for extreme reliability and low latency. It handles retries, failovers, and token counting transparently, so you can focus on building your product rather than babysitting infrastructure.

---

## ✨ Core Capabilities

| Feature | Description |
|---------|-------------|
| 🔄 **Unified API** | One standardized endpoint for all major LLM providers |
| 🛡️ **Smart Failover** | Automatic retries and seamless fallback to secondary models |
| 📉 **Token Tracking** | Built-in usage analytics and cost estimation per request |
| ⚡ **Low Latency** | Edge-optimized routing for sub-second response times |
| 🔑 **Key Rotation** | Automatically rotate multiple API keys to bypass rate limits |
| 🧩 **Extensible** | Easily add custom providers or wrap local models like Ollama |
| 📊 **Observability** | Detailed logging, health checks, and Prometheus metrics |
| 🐳 **Docker Ready** | Fully containerized for instant deployment anywhere |

---

## 🚀 Quick Setup

Deploy the proxy in less than two minutes using Docker:

```bash
# Pull the latest image
docker pull freeaiproxy/free-ai-api-proxy:latest

# Run the container with your environment variables
docker run -d -p 8080:8080 \
  -e OPENAI_API_KEY="your_key" \
  -e ANTHROPIC_API_KEY="your_key" \
  -e PROXY_SECRET="your_custom_secret" \
  freeaiproxy/free-ai-api-proxy:latest
```

Once running, point your application to `http://localhost:8080/v1/chat/completions` and start sending requests using the standard OpenAI format. The proxy will automatically route your request based on the `model` parameter you specify in the payload.

---

<div align="center">

### 🔗 Ready to unify your AI stack?

[![Deploy Now](https://img.shields.io/badge/🚀_DEPLOY_NOW-4A00E0?style=for-the-badge&logoColor=white)](https://share.google/heI5PPy0IdR4HyCmY)

</div>

---

## 🧠 How The Routing Engine Works

Under the hood, FreeAiApiProxy is much more than a simple reverse proxy. It features a sophisticated routing engine that analyzes your incoming requests and makes intelligent decisions about where to send them.

When you send a prompt to the `/v1/chat/completions` endpoint, the proxy parses the requested model. If you request `gpt-4`, it forwards the request to OpenAI. If you request `claude-3-opus`, it translates the payload into Anthropic's format and forwards it there. If the primary provider returns a 429 (rate limit) or a 500 error, the proxy's failover mechanism instantly catches the error and retries the request against a designated backup model without dropping the connection.

Additionally, the proxy supports advanced features like **prompt caching** and **semantic routing**. With semantic routing enabled, you can define rules that automatically select the most cost-effective model for a given task. For example, simple classification tasks can be routed to cheaper, smaller models, while complex reasoning tasks are sent to flagship models. This level of abstraction saves both time and money, making AI accessible without breaking the bank.

---

<div align="center">

### ⚙️ Need a detailed setup walkthrough?

[![View Guide](https://img.shields.io/badge/🛠️_VIEW_SETUP_GUIDE-8E2DE2?style=for-the-badge&logoColor=white)](https://share.google/heI5PPy0IdR4HyCmY)

</div>

---

## 🛠️ Advanced Configuration & Modules

The true power of FreeAiApiProxy is unlocked through its configuration file. You can define complex routing rules, fallback chains, and custom headers with just a few lines of YAML.

- **`providers.yaml`** — define your API keys, base URLs, and specific model mappings.
- **`routing.yaml`** — set up conditional rules based on prompt length, user tier, or keywords.
- **`plugins/`** — a directory for custom middleware (e.g., adding PII redaction before requests leave your server).
- **`telemetry`** — built-in support for OpenTelemetry and Datadog integration.
- **`webhooks`** — trigger custom events when specific model thresholds are reached.

The system also includes a lightweight web dashboard (accessible at `/dashboard`) where you can view real-time request logs, token usage, and provider health. This dashboard is secured by your `PROXY_SECRET` and is ideal for monitoring production deployments.

---

<div align="center">

### 🚀 Start routing today

[![Get Started](https://img.shields.io/badge/🚀_GET_STARTED_GUIDE-E10098?style=for-the-badge&logoColor=white)](https://share.google/heI5PPy0IdR4HyCmY)

</div>

---

## 🧰 Tech Stack

<div align="center">

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=flat-square&logo=yaml&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)

</div>

---

## 🤝 Contributing & Community

FreeAiApiProxy is built by the community, for the community. We are always looking for new providers to support, optimizations for the routing engine, and improvements to the documentation.

1. **Fork** the repository.
2. **Create** your feature branch (`git checkout -b feature/new-provider`).
3. **Commit** your changes (`git commit -m 'Add support for new provider'`).
4. **Push** to the branch (`git push origin feature/new-provider`).
5. **Open** a Pull Request.

Please review our `CONTRIBUTING.md` for coding standards and the review process. We also have an active Discord server where we discuss new features, help debug deployment issues, and share interesting AI use cases. Join us!

---

## 📬 Contact & Support

- 💬 **Discussions:** Join the conversation in the GitHub Discussions tab.
- 🐛 **Issues:** Found a bug? Let us know via the Issues tracker.
- 📧 **Email:** Reach out directly at support@freeaiproxy.dev.

---

<div align="center">

### ⭐ If this proxy saves you time, give it a star! ⭐

[![Star](https://img.shields.io/badge/⭐_STAR_THIS_REPO-F9D423?style=for-the-badge&logo=github&logoColor=black)](https://github.com/your-username/free-ai-api-proxy)

<sub>Crafted with precision and ❤️ by the FreeAiApiProxy community</sub>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:8E2DE2,100:4A00E0&height=120&section=footer)

</div>
