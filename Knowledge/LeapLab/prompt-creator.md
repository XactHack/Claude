# LeapLab Prompt Creator — AI Prompt Mastery Reference

From foundational frameworks to expert-level techniques, in one resource.

## Part 1 — What Is Prompt Engineering?

Prompt engineering is the skill of designing inputs that guide AI toward accurate, relevant, and high-quality responses. Instead of asking random questions, you structure instructions intentionally. Done correctly, it transforms an AI model into a focused assistant rather than a generic responder.

**Core practices**: structuring clear instructions, adding relevant context, defining format and expectations, reducing ambiguity. It's not about complex coding — it's about structured communication. Strong prompts reduce confusion and increase precision.

## Part 2 — Why AI Needs Sharp Prompts

Generative AI models don't genuinely understand human language — they predict it based on probability and proximity:

1. Text is broken down into tokens.
2. Tokens are converted into multi-dimensional vectors (numbers).
3. Vectors are placed into an embedding space where similar ideas cluster.
4. The AI generates output by predicting the most likely next token based on probability and proximity — not stored facts or memory.

Since the AI is a guessing machine: a vague prompt produces vague guesses. A sharp, targeted prompt helps it compute your intent, yielding results 5–10x better. The solution: learn "Machine English" — the structured language AI actually responds to.

## Part 3 — The AIM Framework (Foundation)

AIM transforms any vague request into a structured input the model can understand, compute, and reason with.

| Letter | Component | Purpose & Example |
|---|---|---|
| A | Actor (Persona) | Instructs the model on the specific role/expertise to adopt. e.g. "You are the world's most sought-after résumé editor who has reviewed thousands of résumés that led to interviews at top tech companies." |
| I | Input (Context & Data) | Provides necessary context, files, or data. e.g. "I am attaching my resume and the job description for a Senior Product Manager role at a fintech company." |
| M | Mission (Task) | Defines the precise task/goal, including the overarching objective. e.g. "Review it and give me a bullet list of 10 specific ideas on how to improve clarity, measurable impact, and alignment with the role." |

**Quick reminder**: A = Who is the AI being? I = What context/data/files does it need? M = What exactly must it deliver, and what's the end goal? Using all three consistently yields results 5–10x better than unstructured prompts.

## Part 4 — Prompt Priming

Priming prepares the AI before asking it to complete a task, framing the response before generation begins.

- Without priming: "Write a sales email."
- With priming: "You are an experienced digital marketing consultant specializing in high-converting email campaigns for SaaS startups. Write a persuasive sales email…"

Priming sets the role, establishes expertise, defines context, and improves output quality. It's the practical application of AIM's Actor component — often the single highest-leverage action before any prompt.

## Part 5 — The MAP Framework (Building Context)

Once AIM is mastered, MAP takes prompting further. Context is the map that helps the AI navigate its mathematical space — telling it where to look and what matters.

| Letter | Component | Purpose & Example |
|---|---|---|
| M | Memory | Conversation history carried over from previous sessions. Repaste threads or ask the model to summarize continuity. |
| A | Assets | Files, data, or resources attached/pasted into the prompt — ground the model in your specific reality. |
| A | Actions | Tools the model can call to do work — searching the web, scanning a drive, writing/running code. |
| P | Prompt | The instruction itself. The sharper the AIM prompt, the more powerfully it combines with Memory, Assets, and Actions. |

Mastering AIM + MAP places you in the top 10% of AI users.

## Part 6 — 30 Prompt Starters

**Role & Expertise**
- "Act as an expert in…"
- "You are a world-class [role] with 20+ years of experience in…"
- "Imagine you are a [specific expert] advising a [audience]…"
- "Take on the perspective of a [role] who specializes in…"

**Explanation & Learning**
- "Explain this concept to a beginner who knows nothing about…"
- "Break down [topic] into its five most important components…"
- "Teach me [subject] as if I have a background in [different field]…"
- "Compare and contrast [X] and [Y], focusing on practical differences…"

**Creation & Generation**
- "Create a step-by-step guide for…"
- "Generate 10 ideas for… ranked by potential impact"
- "Draft a [document type] that achieves [specific goal]…"
- "Write a [format] that starts with [hook] and ends with [call to action]…"

**Analysis & Critique**
- "Review the following and identify the three biggest weaknesses…"
- "Analyse [input] from the perspective of [specific lens or framework]…"
- "List every assumption embedded in the following statement…"
- "Find the strongest argument against my position on…"

**Strategy & Planning**
- "Build a 30-day plan to achieve [goal], broken into weekly milestones…"
- "What would [specific expert or company] do differently in this situation?…"
- "Give me a decision framework for choosing between [option A] and [option B]…"
- "Identify the three biggest risks in [plan] and how to mitigate each…"

**Refinement & Iteration**
- "Rewrite the following to be more [concise / persuasive / clear]…"
- "Take this rough idea and sharpen it into a compelling one-paragraph pitch…"
- "What questions should I be asking about [topic] that I am not asking?…"
- "Propose two sharper versions of this prompt and explain the difference…"

**Verification & Fact-Checking**
- "List every assumption you made in your last response and rank by confidence…"
- "Cite two independent sources for each major claim, with title and URL…"
- "Find one credible source that disagrees with this conclusion…"
- "Recompute every figure in your response and show your working…"

**Marketing & Content**
- "Generate fresh content ideas for [audience] around the theme of…"
- "Draft a structured blog post outline with hook, three key sections, and CTA…"

## Part 7 — Debug Your Thinking: Iteration Cheat Codes

When AI output is weak, the problem is almost always the prompt, not the model. Prompting is iterating, not typing.

- **Cheat Code 1 — Chain of Thought**: "Before answering, think through this step by step, show your reasoning, and only then give me your final answer."
- **Cheat Code 2 — Verifier Pattern**: "Before you begin, ask me three clarifying questions one at a time. Use what you learn to produce a sharper response."
- **Cheat Code 3 — Refinement Pattern**: "Propose two sharper versions of the question I just asked. Explain the difference, then ask me which one to run."

## Part 8 — Steer to Experts

Direct the model toward the sharper edges of its knowledge by citing specific experts, companies, or research.

- Generic: "Explain how to make a team more innovative."
- Expert-steered: "Explain how to make a team more innovative using ideas from Pixar's Brain Trust, Satya Nadella's leadership strategy, and Harvard's research on psychological safety."

**Two-step expert discovery** (if you don't know the relevant experts):
1. "List the top 5 experts and most cited research papers on [topic]."
2. Feed those names back: "Using the frameworks of [Expert A] and [Expert B], explain how to [accomplish goal]."

## Part 9 — Verify What You Get

AI models sound confident even when wrong. Verification separates noise from knowledge — the **5 Verification Techniques**:

1. **Assumptions**: ask the AI to list every assumption it made and rank by confidence level.
2. **Sources**: demand two independent sources for each major claim, including title, URL, and a one-line quote.
3. **Counter Evidence**: push the AI to find one credible source that disagrees with its answer.
4. **Auditing**: ask the AI to recompute every figure and show its math or code.
5. **Cross-Model Verification**: run the same prompt in ChatGPT, Gemini, and Claude, then ask one model to critique another's claims.

## Part 10 — Developing Taste: The OCEAN Framework

The final level of AI mastery: moving beyond generic output to responses that sound uniquely like you. Treat the AI as a sparring partner — argue with it, push back, demand better.

| Letter | Component | Purpose & Example |
|---|---|---|
| O | Original | Push for non-obvious ideas. Ask for three angles no one else has thought about, label one as risky, and recommend one. |
| C | Concrete | Ensure there are names, examples, and numbers. Ask for real examples to back every claim. |
| E | Evident | Make the reasoning visible. Ask the AI to show its logic in three bullets and provide evidence before the final answer. |
| A | Assertive | Demand a stance. Ask the AI to pick a side, state a thesis, defend it, and address the best counterpoint. |
| N | Narrative | Guide the AI to structure output as a compelling story: hook, problem, insight, proof, actions. |

## Part 11 — The 30-Day AI Mastery Roadmap

**Week 1: Foundations**
- Step 1 — Learn Machine English: master AIM so structured prompts come without thinking. Goal: 5–10x better outputs.
- Step 2 — Pick Your Instrument: choose one AI model (ChatGPT for maturity, Gemini for Google ecosystem, Claude for business/projects) and go deep.

**Week 2: Advanced Usage**
- Step 3 — Context (MAP): add Memory, Assets, and Actions to prompts. AIM + MAP = top 10% of AI users.
- Step 4 — Debug Your Thinking: when output is weak, fix the prompt using Chain of Thought, Verifier, and Refinement patterns.

**Weeks 3–4: Expert Refinement**
- Step 5 — Steer to Experts: cite specific experts, companies, and research to avoid generic answers.
- Step 6 — Verify What You Get: apply the 5 verification techniques.
- Step 7 — Develop Taste: apply OCEAN to produce original, concrete, evident, assertive, narrative-driven outputs.

As you apply this roadmap, you're not just training the model — you're training yourself.

## Part 12 — Quick-Reference Cheat Sheet

**The Complete Prompt Checklist:**
- [ ] ACTOR defined? (Role, expertise level, perspective)
- [ ] INPUT provided? (Context, files, relevant background data)
- [ ] MISSION stated? (Specific task + overarching goal)
- [ ] PRIMING done? (Role established before the task begins)
- [ ] CONTEXT added? (Memory, Assets, Actions from MAP)
- [ ] EXPERT-STEERED? (Specific sources, frameworks, or names cited)
- [ ] OUTPUT FORMAT defined? (List, table, essay, code, steps...)
- [ ] VERIFICATION requested? (Sources, assumptions, cross-check)
- [ ] OCEAN applied? (Original, Concrete, Evident, Assertive, Narrative)

**Top reasons prompts fail:**
1. No Actor defined — the model defaults to a generic assistant persona.
2. Vague Mission — the model guesses at your goal and guesses wrong.
3. No context or data — the model fills gaps with plausible-sounding fiction.
4. No iteration — the first output is rarely the best; prompting requires refinement.
5. Not verifying outputs — confident-sounding AI responses can still be incorrect.

## Related Notes
- [Content Strategy](./content-strategy.md) — apply AIM/MAP when drafting SLAY-framework posts with AI.
- Note: this is general-purpose prompt-engineering guidance, not LeapLab-specific — also broadly useful for any AI work in this OS (e.g. `Knowledge/Frameworks/`).
