# What is a Large Language Model?

An LLM is a type of AI model that excels at understanding and generating human language. They are trained on vast amounts of text data, allowing them to learn patterns, structure, and even nuance in language. These models typically consist of many millions of parameters.
# Types of Transformers

There are 3 types of transformers:

## Encoders  
An encoder-based Transformer takes text (or other data) as input and outputs a dense representation (or embedding) of that text.

- **Example:** BERT from Google  
- **Use Cases:** Text classification, semantic search, Named Entity Recognition  
- **Typical Size:** Millions of parameters  

## Decoders  
A decoder-based Transformer focuses on generating new tokens to complete a sequence, one token at a time.

- **Example:** Llama from Meta  
- **Use Cases:** Text generation, chatbots, code generation  
- **Typical Size:** Billions (in the US sense, i.e., 10^9) of parameters  

## Seq2Seq (Encoder–Decoder)  
A sequence-to-sequence Transformer combines an encoder and a decoder. The encoder first processes the input sequence into a context representation, then the decoder generates an output sequence.

- **Example:** T5, BART  
- **Use Cases:** Translation, Summarization, Paraphrasing  
- **Typical Size:** Millions of parameters
# How Large Language Models Work

The main idea behind an LLM is simple: it tries to predict the next token based on the previous tokens. A **token** is a unit of text, similar to a word but often smaller for efficiency.

For example, instead of using whole words, LLMs break words into smaller pieces called tokens. The word **“interesting”** might be split into two tokens: **“interest”** and **“ing”**.
# Special Tokens and Next Token Prediction in Large Language Models (LLMs)

LLMs use **special tokens** to manage their text generation. These tokens help the model know when to start or stop generating text.

The most important special token is the **End of Sequence (EOS)** token, which tells the model, "Stop here."

Different models use different EOS tokens. For example:

| Model     | Provider                 | EOS Token         | Purpose               |
|-----------|--------------------------|-------------------|-----------------------|
| GPT-4     | OpenAI                   | `<|endoftext|>`   | End of message text   |
| Llama 3   | Meta                     | `<|eot_id|>`      | End of sequence       |
| SmolLM2   | Hugging Face             | `<|im_end|>`      | End of instruction    |
| Gemma     | Google                   | `<end_of_turn>`   | End of conversation   |



---

## How LLMs Predict Text

LLMs generate text **one token at a time**. After predicting one token, it becomes part of the input to predict the next token. This continues until the model predicts the EOS token.

### Example:

Imagine writing a sentence:

**Input:** "The capital of France is"

The model predicts the next token, e.g., "Paris". Then "Paris" is added to the input, and the model predicts the next token, and so on, until it predicts the EOS token.

---

## Attention: Understanding What Matters

When predicting the next word, not every previous word is equally important. For example, in the sentence:

**"The capital of France is..."**

Words like "capital" and "France" carry the most meaning for predicting the next word.

The **attention mechanism** in Transformers helps the model focus on the most important words when generating the next token.

---

## Summary

- Special tokens like EOS help control when the model stops generating text.  
- LLMs generate text token-by-token, using previous tokens as context.  
- Attention helps the model focus on important parts of the input.  

These concepts allow LLMs to generate coherent and meaningful text.

# Prompting and Training Large Language Models (LLMs)

## Why Prompting Matters

An LLM’s job is to predict the next token by looking at all the tokens in the input and deciding which are most important. This means **how you phrase your input — the prompt — matters a lot**.

A well-designed prompt helps guide the model to give the answer you want.

**Example:**  
If you ask,  
*“What is the capital of France?”*  
you’re more likely to get a clear answer than if you say,  
*“France capital?”*

---

## How Are LLMs Trained?

LLMs learn by reading huge amounts of text and trying to guess the next word in sentences. This is called **self-supervised learning** because they learn from the data itself without needing human labels.

Through this, the model understands language structure and patterns, which lets it handle new sentences it has never seen before.

After this general training, LLMs can be **fine-tuned** for specific tasks like chatting, classifying text, or writing code.

---

This process enables LLMs to generate human-like text and perform many language-related tasks.
# How Are LLMs Used in AI Agents?

Large Language Models (LLMs) are the **core “brain”** of AI Agents. They help agents:

- Understand user instructions  
- Keep track of conversation context  
- Make plans  
- Decide which tools to use  

In short, LLMs enable AI Agents to understand and generate human-like language, making interactions smooth and intelligent.


**The LLM is the brain of the Agent.**



# How Chat with AI Works

- When you chat with AI (like ChatGPT), you send **messages** back and forth.
- Inside the AI, all these messages get joined into one long text before the AI thinks and replies.
- Special **markers** are added to show where each message starts and ends, so the AI knows who said what.

## Types of Messages

- **System Message:** Tells the AI how to behave (like being helpful or polite).
- **User Message:** What you say.
- **Assistant Message:** What the AI replies.

## What is a Chat Template?

- A chat template is a set of rules that puts messages into the right format for the AI to understand.
- It adds the special markers and organizes the conversation properly.

## Why It Matters

- This helps the AI follow instructions and keep track of the conversation, making it feel like a real chat.

## How It Works in Simple Steps

1. You write messages.
2. Messages get formatted with special markers (chat template).
3. The AI reads the formatted conversation and replies.

## Example

Suppose you chat like this:

- You: "Hi, can you help me?"
- AI: "Sure! What do you need?"
- You: "I want to know the weather."

Before the AI processes it, it turns into something like this:

```plaintext
<|system|>You are a helpful assistant.<|end|>
<|user|>Hi, can you help me?<|end|>
<|assistant|>Sure! What do you need?<|end|>
<|user|>I want to know the weather.<|end|>
````

# 🛠️ What Are Tools?



One crucial aspect of AI Agents is their ability to **take actions**. This happens through the use of **Tools**.

In this section, we’ll learn:

- What Tools are
- How to design them effectively
- How to integrate them into your Agent via the System Message

By giving your Agent the right Tools—and clearly describing how those Tools work—you can dramatically increase what your AI can accomplish. Let’s dive in!

---

## 🤖 What are AI Tools?

A **Tool** is a function given to the LLM. This function should fulfill a **clear objective**.

### 🔧 Common Tools in AI Agents

| Tool            | Description                                             |
|------------------|---------------------------------------------------------|
| Web Search       | Fetch up-to-date info from the internet                 |
| Image Generation | Create images from text descriptions                    |
| Retrieval        | Retrieve info from an external source                   |
| API Interface    | Interact with external APIs (e.g. GitHub, YouTube)      |



---

## 🧠 Why Use Tools?

LLMs are powerful, but:

- They’re limited to **pretrained knowledge**
- They can **hallucinate** when asked about current events or real-time data
- They **struggle** with precise tasks like arithmetic

> 🔍 **Example**: To get today’s weather, you need a tool. Otherwise, the LLM may guess randomly.

---

## 🧪 Tool Structure

A Tool should include:

- ✅ **Name**: What it's called
- 📝 **Description**: What it does
- 🔡 **Arguments**: Input types and names
- 📤 **Outputs**: Output type(s)
- ⚙️ **Callable**: The actual function

---

## ⚙️ How Tools Work

1. **LLMs can only read/write text** — they cannot actually *call* a function.
2. The Agent (you) parses the LLM output and executes any tool calls on its behalf.
3. The results are fed back to the LLM as additional input.

> 💡 To the user, it looks like the LLM did everything itself!

---

## 🧾 Defining Tools via System Prompts

To give a Tool to an LLM, describe it clearly in the **system prompt**:





  
