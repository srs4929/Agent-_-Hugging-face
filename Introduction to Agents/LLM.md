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


  
