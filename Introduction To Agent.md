## 🧠 The Agent Workflow

**Think → Act → Observe**

1. **Think** – Analyze the current state and determine the next action.  
2. **Act** – Execute the chosen action using available tools or logic.  
3. **Observe** – Evaluate the result of the action and update internal memory or context.
## 🤖 What is an Agent?

An **Agent** is an AI model capable of **reasoning**, **planning**, and **interacting** with its environment.

We call it an *Agent* because it has **agency** — the ability to take actions and influence its environment.

## 🧩 Agent Anatomy: Brain and Body

Think of the **Agent** as having two main parts:

### 🧠 The Brain (AI Model)
This is where all the thinking happens. The AI model handles **reasoning** and **planning**. It decides which **Actions** to take based on the situation.

### 🛠 The Body (Capabilities and Tools)
This part represents everything the Agent is equipped to do — its tools, functions, or integrations.

# Understanding AI Agents

## What type of AI Models do we use for Agents?

The most common AI model found in Agents is an **LLM (Large Language Model)**, which takes **text as input** and outputs **text** as well.

Well-known examples include:

- GPT-4 from OpenAI
- LLaMA from Meta
- Gemini from Google

These models have been trained on a vast amount of text data and are capable of generalizing well.


> *Note:* It's also possible to use other types of models as an Agent's core model.  
> For example, a **Vision Language Model (VLM)** understands both text and images as input.  
> In this guide, we'll focus primarily on LLMs and discuss other models later.

---

## How does an AI take action on its environment?

While LLMs are amazing at generating text, they cannot perform actions by themselves. 

For example, if you ask chat applications like **HuggingChat** or **ChatGPT** to generate an image, they can do so — but how?

**The secret is Tools:**  
Developers integrate additional functionality, called **Tools**, which the LLM can call upon to perform specific tasks, such as generating images.

*Example:*  
> The model used an **Image Generation Tool** to create the Eiffel Brocolis image.


---

## What type of tasks can an Agent do?

An Agent can perform **any task** implemented via Tools to complete Actions.

### Example:

Suppose you create an Agent as your personal assistant (like Siri) on your computer.  
You ask it to:  
> *“Send an email to my Manager asking to delay today’s meeting.”*





## Example 1: Personal Virtual Assistants
Virtual assistants like Siri, Alexa, or Google Assistant, work as agents when they interact on behalf of users using their digital environments.

They take user queries, analyze context, retrieve information from databases, and provide responses or initiate actions (like setting reminders, sending messages, or controlling smart devices).

## Example 2: Customer Service Chatbots
Many companies deploy chatbots as agents that interact with customers in natural language.

These agents can answer questions, guide users through troubleshooting steps, open issues in internal databases, or even complete transactions.

Their predefined objectives might include improving user satisfaction, reducing wait times, or increasing sales conversion rates. By interacting directly with customers, learning from the dialogues, and adapting their responses over time, they demonstrate the core principles of an agent in action.

## Example 3: AI Non-Playable Character in a video game
AI agents powered by LLMs can make Non-Playable Characters (NPCs) more dynamic and unpredictable.

Instead of following rigid behavior trees, they can respond contextually, adapt to player interactions, and generate more nuanced dialogue. This flexibility helps create more lifelike, engaging characters that evolve alongside the player’s actions.

## Summary
To summarize, an Agent is a system that uses an AI Model (typically an LLM) as its core reasoning engine, to:

Understand natural language: Interpret and respond to human instructions in a meaningful way.

Reason and plan: Analyze information, make decisions, and devise strategies to solve problems.

Interact with its environment: Gather information, take actions, and observe the results of those actions.



