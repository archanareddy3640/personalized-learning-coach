# Prompting Strategy — Kickoff (Nov 17)

## Purpose
Define prompting goals, persona/tone, guardrails and simple evaluation criteria for the Personalized Learning Coach agents.

## Prompting goals (what prompts must achieve)
1. **Accuracy:** Answers must be grounded in provided context and cite sources when used.
2. **Clarity:** Explanations should be simple, stepwise, and matched to learner level (beginner/intermediate/advanced).
3. **Conciseness:** Keep responses focused — avoid unnecessary tangents.
4. **Adaptivity:** Prompt should condition the model to adapt tone and difficulty based on `skill_profile`.
5. **Safety & Honesty:** If the model cannot answer from context, explicitly respond with "I don't know; here are suggested next steps."

## Tone / Persona
- Friendly, encouraging, patient.
- Use short sentences, actionable language, and positive reinforcement.
- Avoid slang; be respectful and culturally neutral.

## Guardrails
- "Use only provided context." (hard requirement)
- "Do not invent facts." (if unsure, say 'I don't know')
- Limit answer length for practice problems (max 120 words per explanation).
- Always include a "next step" recommendation.

## Prompting patterns to use
- **System prompt**: set role + constraints + response format (JSON when machine-readable).
- **Few-shot**: 2–3 examples for complex tasks (tutor explanations, grading).
- **Chain-of-thought avoidance**: avoid asking model to reveal internal reasoning — keep answers, not the chain.
- **Tool contract**: when a tool is required (GRADER_TOOL), specify exact call format.

## Quick versioning
- Add `PROMPT_VERSION: "v0.1"` at top of every prompt file during early iterations.

## Today’s deliverables
- prompts/prompting_strategy.md (this file)
- prompts/assessment_prompt.md (system prompt draft)
- prompts/tutor_prompt.md (system prompt draft)
- prompts/prompt_eval_criteria.md (evaluation rubric)

## Notes for Archana
Archana should expand each system prompt into:
1. Full system instruction (150–300 words)
2. 2 few-shot examples
3. Tool contract snippet if the agent will call a tool
4. A short test-case (input → expected output)

