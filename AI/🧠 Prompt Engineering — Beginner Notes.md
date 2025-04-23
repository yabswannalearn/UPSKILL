
## 📄 Overview

This whitepaper explains how to write _prompts_ for Large Language Models (LLMs) to get better results. It walks you through different _techniques_, _settings_, and _best practices_ for writing clear, effective instructions that LLMs can understand and follow.

---

## ⚙️ What Is Prompt Engineering?

**Prompt Engineering** is the process of crafting a good question or instruction to get useful responses from AI models like ChatGPT or Gemini. Think of it like giving directions to a very smart assistant — the clearer and more specific you are, the better the help you’ll get.

### Why It Matters:

- LLMs predict words one at a time based on patterns they learned from the internet.
    
- Bad prompts = vague, off-topic, or wrong answers.
    
- Good prompts = clear, useful, task-specific answers.
    

---

## 🔧 Key LLM Settings

These settings help control the style and behavior of your AI's responses.

### **1. Output Length**

#tokens = number of words/pieces of words in response

- More tokens = longer answers, higher cost
    
- Less tokens = faster but shorter responses
    

### **2. Temperature**

Temperature∈[0,1+]Temperature ∈ [0, 1+] Temperature∈[0,1+]

- **0** = very strict, always picks the most likely word (good for facts)
    
- **Higher** = more creative or random (good for stories or brainstorming)
    

### **3. Top-K Sampling**

- Chooses from the **top K most likely words**.
    
- **K=1** = picks just the best guess
    
- Higher K = more variety
    

### **4. Top-P Sampling (Nucleus Sampling)**

- Chooses from words whose total probability = **P**
    
- **P=0.9** = only most likely answers
    
- **P=1** = include everything
    

> 💡 Use a combo like `temperature=0.2, top-P=0.95, top-K=30` for balance.

---

## 🧪 Prompting Techniques

### **1. Zero-Shot Prompting**

- Just ask your question without examples.
    

text

CopyEdit

`Classify the review as POSITIVE, NEUTRAL, or NEGATIVE: "Her" is a disturbing study... a masterpiece.`

### **2. One-Shot and Few-Shot Prompting**

- Give **1** or **a few examples** to show the AI what to do.
    

text

CopyEdit

`EXAMPLE: I want a small pizza with cheese. JSON: { "size": "small", "ingredients": ["cheese"] }  TASK: I want a large pizza with ham.`

### **3. System, Role, and Contextual Prompts**

- **System** = tells the AI what its job is.
    
- **Role** = makes it act like a specific character (e.g., teacher, lawyer).
    
- **Contextual** = gives background to help it answer better.
    

---

## 🧠 Advanced Prompting Styles

### **Step-Back Prompting**

- Ask a broader or related question first.
    
- Helps the model "think" before it answers.
    

### **Chain of Thought (CoT)**

- Force the model to **show its steps**.
    

text

CopyEdit

`Q: I was 3, my partner was 3x my age. I'm 20 now. How old is my partner? A: Step 1... Step 2... Final Answer: 26`

### **Self-Consistency**

- Ask the model the same question several times and **pick the most common answer**.
    

---

## 🧼 Best Practices

- **Be specific** in your prompt.
    
- **Use examples** when possible.
    
- **Write clearly**, avoid confusing language.
    
- **Experiment** with different formats.
    
- **Track what works** and reuse effective prompts.
    

---

## ✅ Key Takeaways

1. **Prompt engineering = giving the AI good instructions.**
    
2. Use **temperature, top-K, top-P** to control randomness and creativity.
    
3. Try **zero-shot, few-shot, role-based**, and **chain of thought** techniques.
    
4. **Self-consistency** helps boost accuracy on tough questions.
    
5. Clear, structured prompts = better, safer results.