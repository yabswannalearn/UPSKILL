## 📄 Overview

This guide explains how to create **AI agents** — smart systems powered by large language models (LLMs) that can **do tasks for you** (not just answer questions). It teaches the basics of when and how to build agents, how they work, and how to keep them safe and reliable.

---

## 🤔 What Is an Agent?

### Agent vs. Chatbot:

|**Agent**|**Chatbot**|
|---|---|
|Acts independently|Responds to single requests|
|Can handle multi-step tasks|Usually one question at a time|
|Uses tools (APIs, search, databases)|Just gives answers|
|Can decide what to do next|Follows strict rules|

> **Analogy:** A chatbot is like a calculator. An agent is like a virtual assistant that can book your flights, check the weather, and send reminders.

---

## 🧪 When Should You Use Agents?

Use agents for **complex workflows** that:

1. **Need judgment calls** (like refund approvals)
    
2. **Have messy rules** (like security reviews)
    
3. **Use unstructured info** (like reading PDFs or emails)
    

> **Don’t use agents** if a simple rule-based app will do the job.

---

## ⚙️ The 3 Main Parts of an Agent

### 1. **Model**

- The brain of the agent (usually an LLM like GPT or Claude)
    

### 2. **Tools**

- APIs, functions, or systems it uses to take action  
    (e.g., sending emails, searching, updating databases)
    

### 3. **Instructions**

- The rules that tell the agent what to do and how to act
    

> 🧠 Think of it like:  
> “Smart AI brain + toolbox + user manual = Agent”

---

## 🔨 Designing an Agent

### 🧩 Start Simple:

- Use a powerful model for all tasks first
    
- Then test which tasks can switch to faster, cheaper models
    

### 🧰 Define Tools:

|**Tool Type**|**What It Does**|**Examples**|
|---|---|---|
|Data|Gets info|Search, read docs|
|Action|Does stuff|Send message, update CRM|
|Orchestration|Runs other agents|“Manager” agent|

---

## ✏️ Writing Clear Instructions

- Use real examples from support docs or company playbooks
    
- Break big tasks into small steps
    
- Be **very specific**: tell the agent exactly what to say or do
    
- Plan for **edge cases** like missing info or weird inputs
    

---

## 🔁 Orchestration Patterns

### 1. **Single-Agent System**

- One smart agent with tools handles everything in a loop
    
- Simple and easier to manage
    

### 2. **Multi-Agent System**

- Agents hand off tasks to each other like a relay race
    

#### Two types of multi-agent setups:

|**Pattern**|**How It Works**|**Example**|
|---|---|---|
|**Manager**|One “boss” agent calls other agents as tools|Translator agent calls French/Spanish sub-agents|
|**Decentralized**|Agents talk to each other and pass tasks|Support agent sends delivery question to order agent|

---

## 🛡️ Guardrails: Keeping Things Safe

> Like bumpers in bowling — they prevent agents from going off track.

Types of guardrails:

- **Relevance filter**: blocks off-topic questions
    
- **Safety filter**: blocks hacks and unsafe prompts
    
- **PII filter**: stops leaking personal info
    
- **Moderation**: catches toxic or offensive stuff
    
- **Tool risk levels**: high-risk tools pause or escalate
    

> 🧱 Use layers of protection for better safety (rules + AI checks)

---

## ✅ Key Takeaways

1. **Agents = smart, decision-making AI systems** that can do real work.
    
2. Use them for **complex tasks** where simple automation fails.
    
3. Good agents need a **model, tools, and clear instructions**.
    
4. Start simple, then **split into multiple agents** if needed.
    
5. **Use guardrails** to keep them safe, ethical, and on-task.