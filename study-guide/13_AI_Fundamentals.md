# 📁 FOLDER 13 — AI FUNDAMENTALS 🟡 MEDIUM PRIORITY

---

## 🧠 CONCEPT OVERVIEW

AI Fundamentals covers: LLMs, prompt engineering, AI agents, tools, memory, and safety loops.

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. Generative AI vs LLM ⭐

**Generative AI:** AI that creates new content — text, images, code, audio.

**LLM (Large Language Model):** A type of generative AI trained on massive text data. Predicts the next token to generate coherent responses. Examples: GPT, Gemini, Claude.

**How does an LLM generate text?**
1. Input is tokenized (split into tokens)
2. Model predicts the probability of the next token
3. Tokens are sampled and appended
4. Process repeats until end-of-output

---

### Q2. What is a Token? What is Context? ⭐

**Token:** The smallest unit of text the model processes. Roughly 1 token ≈ ¾ of an English word.
- "Hello world" ≈ 2 tokens
- Code and long words take more tokens

**Context (Context Window):** The maximum amount of text (tokens) the model can "see" at once — both the input and output combined.
- If input exceeds context window → earlier content is lost

---

### Q3. Prompt Engineering ⭐

**Definition:** The art of crafting inputs (prompts) to get better outputs from an LLM.

**What makes a good prompt?**
- Clear instructions
- Specific constraints (format, length, audience)
- Context/background information
- Examples of desired output

---

### Q4. Zero-Shot vs Few-Shot Prompting ⭐

| Type | Definition | When to use |
|------|-----------|-------------|
| **Zero-shot** | No examples given | Simple tasks the model already knows |
| **Few-shot** | 2–5 examples provided | Specialized format or complex tasks |
| **Role prompting** | Tell model to act as an expert | Get domain-specific responses |
| **Structured prompting** | Define format (JSON, steps, etc.) | When you need consistent output format |

**Why constraints in prompts?**
- Reduce hallucination
- Ensure format consistency
- Focus model on relevant information

---

### Q5. What is Hallucination? How to reduce? ⭐

**Hallucination:** When an LLM generates **plausible-sounding but factually incorrect** information. It doesn't "know" it's wrong.

**Why it happens:**
- Model optimizes for plausible next tokens, not factual accuracy
- Knowledge cutoff — model may not know recent events
- Gaps in training data

**How to reduce:**
- Use Retrieval-Augmented Generation (RAG) — ground responses in real documents
- Tell the model to say "I don't know" when uncertain
- Provide context/documents in the prompt
- Use lower temperature for factual tasks
- Verify outputs with tools

---

### Q6. What is Temperature? ⭐

**Temperature:** Controls randomness of output.
- **Low temperature (0–0.3):** Deterministic, conservative, factual. Same prompt → same answer.
- **High temperature (0.8–1.5):** More creative, diverse, unpredictable.

**When to use:**
- Factual Q&A, code generation → low temperature
- Creative writing, brainstorming → high temperature

**🧠 Remember:** Temperature = how "spicy" the model is. High temp = creative/random. Low temp = safe/predictable.

---

### Q7. What is an AI Agent? ⭐

**AI Agent:** An AI system that can **perceive, reason, and take actions** autonomously to achieve a goal — not just respond to a single prompt.

**AI Chatbot vs AI Agent:**
| Chatbot | AI Agent |
|---------|---------|
| Responds to one message | Pursues a goal over multiple steps |
| Single-turn or basic multi-turn | Plans and acts autonomously |
| No tool use | Uses tools (search, code, APIs) |
| No memory | Can have memory |

---

### Q8. Tools in AI Agents ⭐

**Tool:** A function or external service the agent can call to get information or perform actions.
- Examples: web search, calculator, code interpreter, database query, API call

**Why does an agent need tools?**
- LLMs have a knowledge cutoff (need live data)
- LLMs can't perform computation reliably (need calculator)
- LLMs can't take real-world actions directly

---

### Q9. Tool-Calling Loop ⭐

The loop an agent follows:
1. **Think** — determine what to do
2. **Act** — call a tool with input
3. **Observe** — receive tool output
4. **Repeat** until the goal is achieved
5. **Return** final answer

---

### Q10. AI Skills and Hooks ⭐

**AI Skills:** Specific capabilities or modules an agent can invoke — like browsing the web, reading a file, or generating an image. Each skill is a "tool" with defined inputs/outputs.

**Hooks (in AI-agent workflows):** Callback points where custom logic is injected — e.g., "before tool call", "after response", "on error". Allow monitoring, logging, safety checks.

**Why use hooks?**
- Inspect/modify inputs before they reach a tool
- Log all tool calls for audit
- Inject safety checks (rate limiting, content filtering)
- Trigger side effects (save to DB, send notification)

---

### Q11. What is AI Memory? ⭐

| Type | Definition | Example |
|------|-----------|---------|
| **Short-term** | Within current conversation (context window) | Previous messages |
| **Long-term** | Stored externally, retrieved when needed | User preferences in DB |

---

### Q12. Infinite Loop in AI Agent ⭐ (Q620) MUST KNOW

**Problem:** Agent keeps calling the same tool indefinitely.

**Causes:**
- Tool result doesn't satisfy stop condition
- Goal is ambiguous — agent doesn't know when to stop
- No loop counter

**Safeguards to implement:**
1. **Max iteration limit** — stop after N steps
2. **Tool call deduplication** — if same tool called with same args twice, stop
3. **Timeout** — stop if execution exceeds time limit
4. **Human-in-the-loop** — require human confirmation for sensitive actions
5. **Goal completion check** — explicit stopping condition in agent logic
6. **Monitoring/logging** — detect loops from outside

---

### Q13. How to Evaluate Whether an AI Agent is Useful? ⭐

- **Task success rate** — does it complete tasks correctly?
- **Efficiency** — how many steps/tokens does it use?
- **Hallucination rate** — how often does it produce false info?
- **Human feedback** — user satisfaction scores
- **Comparison baseline** — is it better than without the agent?

---

## 🔑 QUICK MEMORY TRICKS

- **Token** = smallest text unit (~¾ of a word)
- **Context** = everything the model can see at once
- **Hallucination** = confident but wrong
- **Temperature** = creativity dial (low=safe, high=creative)
- **Agent** = LLM + tools + loop + memory
- **Tool-calling loop:** Think → Act → Observe → Repeat
- **Hooks** = safety checkpoints in agent workflow

---

## ⚠️ COMMON MISTAKES

1. Thinking the model "knows" when it hallucinates — it doesn't
2. Using high temperature for factual tasks → unpredictable results
3. Not setting a max iteration limit on agents → infinite loops
4. Confusing context window with long-term memory
5. Thinking CORS-like restrictions apply to agent tool calls — they don't (server-to-server)
