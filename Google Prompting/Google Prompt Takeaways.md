TASK 
- Persona - make the AI act like a professional or give it an specific audience
- Format - how the output would appear eg. bulleted lists, paragraph, sentences or table
CONTEXT
- Necessary details that would AI need to generate what you need from it.
- being more specific
REFERENCES
- give what you given in the past time
EVALUATE
- look if the input prompt got the output prompt that you desire
ITRETATE
- tweak the prompt to get the best output

Thoughtfully
Create
Really
Excellent
Inputs



REFERENCES
few shot prompting - 3+ references
single shot prompting - 1 reference
zero shot prompting - 0 reference
2-5 reference is the goldilocks zone in references

## **Prompting 101: Getting the AI to Do What You Want**

- **The Goal:** To create clear, detailed prompts that get accurate and useful outputs from AI.
    
- **Key Components:**
    
    - **Task:**
        - What do you want the AI to do? (e.g., write, create, summarize)
        - Be specific! Avoid vague requests.
        - Add a "persona" (e.g., "act as a science expert").
        - Specify the "format" (e.g., bullet points, table, paragraph).
    - **Context:**
        - Provide background information. The more, the better.
        - Explain your goals and reasons for the task.
        - Use delimiters (like """ or XML tags) to separate parts of the prompt.
    - **References:**
        - Give examples of what you want the AI to create.
        - Use text, images, or audio as references.
        - Provide 2-5 examples.
    - **Evaluation:**
        - Check the AI's output for accuracy, relevance, and bias.
        - Don't just blindly trust the results.
    - **Iteration:**
        - If the output is not right, tweak the prompt.
        - Keep refining your prompts until you get the desired results.
- **Why This Matters:**
    
    - AI models vary, so clear prompts are crucial.
    - Accurate outputs save time and improve results.
    - Using this framework is applicable to all gen AI models.
- **In Simple Terms:**
    
    - Tell the AI exactly what to do, give it background info, show it examples, check its work, and keep improving your instructions.
    - Think of it as having a very specific conversation with a very smart, but sometimes literal, assistant.


Always be Iterating

Practice image prompting: 
https://artsandculture.google.com/experiment/say-what-you-see/jwG3m7wQShZngw?hl=en


tone alternatives
- Academic, or “scholarly and in-depth, like a professor”
    
- Persuasive, or “compelling and convincing”
    
- Sarcastic, or “dryly funny, like a wry comedian”
    
- Inspirational, or “motivating and uplifting”
    
- Simple, or “like you’re a kindergarten teacher explaining this to their students”

Advance summarization technique
Chain of density

`Key Settings and What They Do:

- **Temperature:**
    - Controls how "creative" or "predictable" the AI is.
    - **Low Temperature (e.g., 0.1):**
        - More predictable, factual, and accurate.
        - Best for summaries, timelines, and tasks needing precision.
    - **High Temperature (e.g., 1.5):**
        - More creative, surprising, and varied.
        - Best for brainstorming, creative writing, and exploring new ideas.
        - Increases the chance of hallucinations.
- **Top-k:**
    - Sets the number of possible options (tokens) the AI considers.
    - **Low Top-k:**
        - Narrows the choices, reducing hallucinations.
        - Useful for when you need focused specific results.
    - **High Top-k:**
        - Expands the choices, leading to more diverse outputs.
        - Useful for brainstorming and creative exploration.
        - Setting top-k to 1 or temperature to 0 makes the result deterministic (always the same).
- **Top-p:**
    - Filters options based on their combined probability.
    - **Low Top-p (less than 1.0):**
        - Focuses on the most likely responses.
        - Useful for tasks needing precision.
    - **High Top-p (closer to 1.0):**
        - Allows more varied responses.
        - Useful for comparing options and brainstorming.
        - Default is 1.0, which has no effect.

**Quick Tips:**

- **For accuracy:** Use low temperature and low top-p.
- **For creativity:** Use high temperature and high top-k or top-p.
- **Always check the output:** High randomness can lead to errors (hallucinations).
- Experiment with the settings to find what works best for your needs.
- Default settings will return when a new chat thread is started.`



use google ai studio to build prompts for future use of AI

prompt chaining:

chain of thought - explain your thought process

tree of thought - solving abstract problems

### **Prompt Chaining: Breaking Down Big Tasks with AI**

Some projects are too big to handle all at once. With **prompt chaining**, you break a task into smaller steps, using AI-generated outputs to build on previous prompts. This keeps things manageable and helps prevent AI mistakes.

### **How It Works**

1. **Start with a broad prompt** – e.g., designing an onboarding course.
2. **Refine the output step by step** – expand sections, create quizzes, or generate images.
3. **Re-enter context when needed** – some AI models don’t remember past prompts.

### **Advanced Techniques**

🔹 **Chain-of-Thought Prompting** – Ask AI to explain its reasoning step by step (e.g., "Explain your reasoning"). This helps refine responses and pinpoint errors.

🔹 **Tree-of-Thought Prompting** – Generate multiple solutions, evaluate them, and choose the best one. This is useful when exploring different design styles or problem-solving approaches.

### **Key Takeaways**

- **Be specific** – Clear, detailed prompts lead to better outputs.
    
- **Iterate & refine** – Adjust prompts based on results.
    
- **Combine techniques** – Use both chain-of-thought and tree-of-thought when needed.
    
- **Stay involved** – AI helps, but human judgment is crucial.
    

### **Meta-Prompting: A Simple Guide**

**What is Meta-Prompting?**

Meta-prompting is the process of using AI to help design better prompts. It’s like asking AI how to ask better questions.

**Why is it Useful?**

- Helps get more accurate and useful AI responses
- Improves clarity and detail in prompts
- Saves time by refining prompts quickly

**Two Main Strategies:**

1. **Prompt Generation** – Creating a prompt from scratch
    - Example: _“Generate a prompt for writing a job offer letter.”_
2. **Prompt Refinement** – Improving an existing prompt
    - Example: _“How can I make my prompt more engaging?”_

**Bonus Tip:**

If a prompt isn’t working, break it into smaller steps or combine multiple prompts for better results!

Would you like any tweaks to fit your study style better? 😊

AI AGENTS

- make them simulate a professional to conversate with them to practice certain skills like vocabulary and interviews
- make them also give feedbacks on your work so you can enhance it

### **AI Agents Overview**

- AI agents act as expert assistants for various tasks.
- They can help with writing, learning, roleplaying scenarios, and more.

### **How to Create an AI Agent**

1. **Assign a Persona** – Define the role (e.g., fitness trainer, editor, grant writer).
2. **Give Context** – Explain your goal or situation.
3. **Specify Interactions** – Set conversation style and rules.
4. **Use a Stop Phrase** – Define how to end the session.
5. **Request Takeaways** – Ask for summaries or improvement points.

### **Applications of AI Agents**

1. **Skill Practice** – Roleplay negotiations, public speaking, etc.
2. **Feedback & Critique** – Improve writing, proposals, or presentations.
3. **Learning** – AI tutors for languages, coding, etc.
4. **Project Collaboration** – Assist with research, grants, and planning.

**Main Idea:** AI agents personalize AI interactions by acting as experts, providing structured conversations, and enhancing productivity.

### **More AI Agent Ideas**

- **Professor Ethan Mollick’s Newsletter (One Useful Thing)** – Offers practical AI tips, research-based insights, and discussions on AI’s impact.
- **LangChain** – An open-source framework for linking AI agents together with minimal coding.
- **Google Vertex AI Agents** – Allows users to integrate conversational AI into apps, devices, and bots. Supports text and voice inputs.
- **Gems (in Gemini AI)** – Customizable AI personas with specific skills, such as a learning coach, career guide, and coding partner.

### **Main Takeaway**

AI agents aren’t just for fun—they can boost productivity, learning, and creativity. Experimenting with them could unlock new ways to achieve your goals.

prompt versioning

modify prompts for further use