# AI Prompt Engineering Guide

**Purpose:** Master prompt engineering to build high-quality AI prototypes

**Time Required:** Ongoing practice throughout Week 10

**Output:** Effective prompts that deliver consistent, high-quality AI outputs

---

## Table of Contents

1. [Prompt Engineering Fundamentals](#prompt-engineering-fundamentals)
2. [Anatomy of a Great Prompt](#anatomy-of-a-great-prompt)
3. [Core Techniques](#core-techniques)
4. [Advanced Patterns](#advanced-patterns)
5. [Common Use Cases](#common-use-cases)
6. [Testing & Iteration](#testing--iteration)
7. [Troubleshooting](#troubleshooting)
8. [Best Practices](#best-practices)

---

## Prompt Engineering Fundamentals

### What is Prompt Engineering?

**The art and science of crafting inputs to LLMs to get desired outputs reliably.**

**It's critical because:**
- Small changes in prompts = big changes in output
- Good prompts = consistent quality
- Bad prompts = unpredictable, low-quality results
- Prompting is faster/cheaper than fine-tuning

**For your portfolio:**
- ✅ Shows you understand AI systems deeply
- ✅ Demonstrates practical AI skills
- ✅ Proves you can ship working AI products

---

### System vs User Prompts

**System Prompt:**
- Sets the AI's role, behavior, and constraints
- Persistent across conversation
- Like "programming" the AI
- User never sees it

**User Prompt:**
- Specific request or question
- Changes with each interaction
- What the user actually types
- User-facing

**Example:**

```
System: "You are a helpful coding assistant who writes clear,
commented code in Python."

User: "Write a function to calculate fibonacci numbers"
```

---

### The Prompt Engineering Mindset

**Think of LLMs as:**
- ❌ Magic black boxes
- ✅ Very smart but literal interns

**They need:**
- Clear instructions
- Context
- Examples
- Constraints
- Format specifications

**They struggle with:**
- Vague requests
- Implicit assumptions
- Complex multi-step reasoning without guidance
- Knowing what you really want

---

## Anatomy of a Great Prompt

### The 6-Part Prompt Template

```
1. [ROLE]          Who is the AI?
2. [CONTEXT]       What's the situation?
3. [TASK]          What should it do?
4. [CONSTRAINTS]   What are the limits?
5. [FORMAT]        How should output look?
6. [EXAMPLES]      Show what good looks like
```

---

### Example Breakdown

**Bad Prompt:**
```
Generate documentation for this code
```

**Good Prompt:**
```
[ROLE]
You are an expert technical writer with 10 years of experience
documenting Python code.

[CONTEXT]
The user has provided a Python function that needs clear
documentation for other developers on their team.

[TASK]
Generate comprehensive documentation that helps developers
understand what the function does, how to use it, and any
edge cases to be aware of.

[CONSTRAINTS]
- Use Google-style docstrings
- Keep summary under 80 characters
- Include type hints
- Explain the "why" not just the "what"

[FORMAT]
Output in this structure:
"""
[One-line summary]

[Detailed description]

Args:
    param1 (type): description
    param2 (type): description

Returns:
    type: description

Raises:
    ExceptionType: when this happens

Example:
    >>> example_usage()
    expected_output
"""

[EXAMPLES]
Here are two examples of excellent documentation:
[Include 2 examples]

Now document this function:
{user_provided_code}
```

**Result:**
- Specific role → better expertise
- Clear context → better understanding
- Explicit task → focused output
- Defined constraints → appropriate scope
- Format specified → consistent structure
- Examples shown → quality benchmark

---

## Core Techniques

### Technique 1: Clear Instructions

**Principle:** Be explicit about what you want

**Bad:**
```
Make this better
```

**Good:**
```
Improve this code by:
1. Adding type hints
2. Adding docstrings
3. Breaking long functions into smaller ones
4. Adding error handling
```

**Impact:** 70% → 95% quality

---

### Technique 2: Provide Context

**Principle:** Give the AI relevant background

**Bad:**
```
Write a function to process data
```

**Good:**
```
Context: You're building a data pipeline for an e-commerce company.
The data is JSON from an API containing product information.

Write a function to validate and clean this data before storing
it in the database.
```

**Impact:** Generic → Tailored

---

### Technique 3: Specify Format

**Principle:** Define exact output structure

**Bad:**
```
Explain this code
```

**Good:**
```
Explain this code in this format:

## Purpose
[What it does in one sentence]

## How It Works
[Step by step breakdown]

## Key Concepts
- [Concept 1]
- [Concept 2]

## Potential Issues
- [Issue 1]
- [Issue 2]
```

**Impact:** Inconsistent → Consistent

---

### Technique 4: Use Examples (Few-Shot)

**Principle:** Show, don't just tell

**Zero-Shot (No Examples):**
```
Classify the sentiment: "This product is okay"
```

**Few-Shot (With Examples):**
```
Classify the sentiment of product reviews.

Examples:
Input: "This is amazing! Best purchase ever!"
Output: Positive (confidence: 0.95)

Input: "Terrible quality, broke after one use"
Output: Negative (confidence: 0.98)

Input: "It's fine, nothing special"
Output: Neutral (confidence: 0.80)

Now classify:
Input: "This product is okay"
Output:
```

**Impact:** 60% accuracy → 85% accuracy

---

### Technique 5: Chain of Thought

**Principle:** Ask AI to show its reasoning

**Without CoT:**
```
Is this code correct? [code]
```

**With CoT:**
```
Analyze this code step by step:

1. What is this code trying to do?
2. Trace through the logic
3. Identify any potential bugs
4. Determine if it's correct

[code]

Think through each step before answering.
```

**Impact:** Better reasoning, fewer errors

---

### Technique 6: Iterative Refinement

**Principle:** Start broad, then refine

**Iteration 1:**
```
Generate documentation for this function
```

**Iteration 2 (based on results):**
```
Generate documentation for this function.
Make it more concise and focus on practical usage examples.
```

**Iteration 3:**
```
Generate documentation for this function.
Keep it under 10 lines.
Include 2 usage examples.
Use simple language (explain like I'm new to Python).
```

**Impact:** Each iteration improves quality

---

## Advanced Patterns

### Pattern 1: Role Playing

**Technique:** Assign specific persona

```
You are a senior software engineer at Google who specializes
in code reviews. You've reviewed 1000+ pull requests.

Review this code as if it's a PR from a junior engineer.
Be constructive but thorough.
```

**When to use:** Need specific expertise or perspective

---

### Pattern 2: Delimiters

**Technique:** Use clear markers to separate sections

```
You will receive CODE and STYLE_GUIDE.
Generate documentation that follows the STYLE_GUIDE.

CODE:
```python
{user_code}
```

STYLE_GUIDE:
```markdown
{style_rules}
```

OUTPUT FORMAT:
```markdown
{format_template}
```
```

**When to use:** Multiple inputs or complex structure

**Benefits:**
- Clearer separation
- Less confusion
- Better parsing

---

### Pattern 3: Structured Output (JSON Mode)

**Technique:** Request specific data structure

```
Extract key information from this code and return as JSON:

{
  "function_name": "string",
  "purpose": "string",
  "parameters": [
    {
      "name": "string",
      "type": "string",
      "description": "string"
    }
  ],
  "returns": {
    "type": "string",
    "description": "string"
  },
  "complexity": "O(...)"
}

CODE:
{user_code}
```

**When to use:** Need consistent, parseable output

**Benefit:** Easy to process programmatically

---

### Pattern 4: Multi-Step Instructions

**Technique:** Break complex tasks into steps

```
Follow these steps to document this code:

Step 1: Analyze the code structure
- Identify main components
- Note dependencies
- Understand data flow

Step 2: Determine the purpose
- What problem does it solve?
- Who is the target user?

Step 3: Identify edge cases
- What could go wrong?
- What are the limitations?

Step 4: Write the documentation
- Use the template provided
- Include findings from steps 1-3

Now, begin with Step 1:
{code}
```

**When to use:** Complex analysis or multi-part tasks

---

### Pattern 5: Self-Verification

**Technique:** Ask AI to check its own work

```
Generate documentation for this code.

Then, review your documentation and check:
- Is it accurate?
- Does it match the code?
- Are there any mistakes?
- Is anything unclear?

If you find issues, regenerate with corrections.

CODE:
{user_code}
```

**When to use:** High-stakes outputs, quality assurance

---

### Pattern 6: Confidence Scoring

**Technique:** Ask AI to rate its confidence

```
Document this code.

At the end, provide a confidence score (0-100) and explain:
- What you're confident about
- What you're uncertain about
- What additional information would help

CODE:
{user_code}
```

**When to use:** Need to know reliability of output

---

## Common Use Cases

### Use Case 1: Code Documentation

**Effective System Prompt:**

```
You are CodeDocAI, an expert technical writer specializing in code documentation.

Your purpose: Generate clear, comprehensive documentation that helps developers
understand and use code effectively.

Guidelines:
1. Start with a concise one-line summary (< 80 chars)
2. Explain the purpose and use case
3. Document all parameters with types
4. Include practical usage examples
5. Note edge cases and gotchas
6. Use the language's standard doc format (JSDoc, docstrings, etc.)

Output format:
"""
[One-line summary]

[Detailed explanation of what it does and why]

Parameters:
- param1 (type): description
- param2 (type): description

Returns:
- type: description

Example:
```language
code_example
```

Notes:
- [Important consideration 1]
- [Important consideration 2]
"""

Constraints:
- Do NOT execute code, only document it
- If code is unclear, ask clarifying questions
- If you detect potential bugs, mention them in Notes

Tone: Professional but approachable, like a helpful colleague
```

**User Prompt Template:**

```
Document this {language} {code_type}:

```{language}
{user_code}
```

Additional context (optional):
{user_context}
```

---

### Use Case 2: Content Generation

**Effective System Prompt:**

```
You are a content generation assistant that creates {type of content}.

Your purpose: Generate high-quality {content type} that is:
- Clear and engaging
- Well-structured
- Appropriate for the target audience
- Free of errors

Process:
1. Understand the user's requirements
2. Plan the structure
3. Generate content section by section
4. Review for quality

Output format:
[Specify exact format]

Constraints:
- Length: {range}
- Tone: {formal/casual/etc}
- Audience: {description}
- Do NOT include: {restrictions}

Examples of excellent output:
[Include 1-2 examples]
```

---

### Use Case 3: Data Extraction

**Effective System Prompt:**

```
You are a data extraction specialist.

Your purpose: Extract structured information from unstructured text.

Process:
1. Read the input carefully
2. Identify relevant information
3. Extract data fields
4. Format as specified
5. Include confidence scores

Output format: JSON
{
  "field1": "value",
  "field2": "value",
  "confidence": 0.95,
  "notes": "any uncertainties"
}

Constraints:
- Only extract information explicitly stated
- Do NOT make assumptions
- If information is missing, use null
- If uncertain, note it in "notes" field
```

---

### Use Case 4: Conversational AI

**Effective System Prompt:**

```
You are {product name}, a {role} assistant.

Your personality:
- {trait 1}
- {trait 2}
- {trait 3}

Your capabilities:
- {capability 1}
- {capability 2}
- {capability 3}

Conversation flow:
1. Greet the user warmly
2. Understand their need
3. Provide helpful information or complete tasks
4. Ask clarifying questions when needed
5. Offer next steps

Response style:
- Keep responses concise (2-3 paragraphs max)
- Use bullet points for lists
- Be conversational but professional
- Show empathy and understanding

Boundaries:
- You cannot {restriction 1}
- You do not {restriction 2}
- If asked to do something outside your capabilities, politely explain
  what you CAN do instead

Error handling:
- If you don't understand, ask for clarification
- If you make a mistake, acknowledge and correct
- If you can't help, suggest alternatives

Remember:
You're a helpful assistant, not a replacement for human expertise.
Guide users to the right solutions.
```

---

### Use Case 5: Code Review

**Effective System Prompt:**

```
You are a senior software engineer conducting a code review.

Review criteria:
1. **Correctness**: Does the code work?
2. **Clarity**: Is it easy to understand?
3. **Best Practices**: Follows language conventions?
4. **Performance**: Any obvious inefficiencies?
5. **Security**: Any vulnerabilities?
6. **Testing**: Are edge cases handled?

Review process:
1. Read the code thoroughly
2. Identify issues by category
3. Provide specific, actionable feedback
4. Suggest improvements with examples
5. Acknowledge what's done well

Output format:
## Summary
[Overall assessment in 2-3 sentences]

## Issues Found
### Critical (must fix)
- [Issue 1]: [Explanation and fix]

### Important (should fix)
- [Issue 2]: [Explanation and fix]

### Nice to Have (consider)
- [Issue 3]: [Explanation and fix]

## What's Good
- [Positive 1]
- [Positive 2]

## Suggestions
[2-3 concrete improvements]

Tone: Constructive and educational, like mentoring a colleague
```

---

## Testing & Iteration

### Test-Driven Prompt Engineering

**1. Define Success Criteria**

```
Good output should:
- Be accurate (100%)
- Follow format (100%)
- Include all required sections (100%)
- Use appropriate tone (subjective but clear)
- Handle edge cases (specific list)
```

**2. Create Test Cases**

```
Test 1: Happy path
Input: [Normal example]
Expected: [Ideal output]

Test 2: Edge case - empty input
Input: ""
Expected: [Error message or default behavior]

Test 3: Edge case - very long input
Input: [10,000 char string]
Expected: [Truncate or split behavior]

Test 4: Edge case - ambiguous request
Input: [Unclear request]
Expected: [Ask clarifying question]

[Create 10-15 test cases]
```

**3. Run Tests**

Test each prompt variation:
- Prompt v1 → 60% pass rate
- Prompt v2 → 75% pass rate
- Prompt v3 → 90% pass rate

**4. Iterate Until Acceptable**

Target: >85% pass rate on all tests

---

### A/B Testing Prompts

**Compare variations:**

**Prompt A:**
```
Generate documentation for this code
```

**Prompt B:**
```
You are an expert technical writer. Generate comprehensive
documentation for this code using Google-style docstrings.
```

**Measure:**
- Quality (human eval 1-5)
- Consistency (variation across runs)
- Completeness (has all sections)
- User acceptance rate

**Choose winner** and iterate

---

### Tracking Prompt Performance

**Metrics to track:**

| Prompt Version | Quality Score | Consistency | Latency | Cost | Pass Rate |
|----------------|---------------|-------------|---------|------|-----------|
| v1.0 | 3.2/5 | 65% | 8s | $0.03 | 60% |
| v1.1 | 4.1/5 | 82% | 12s | $0.04 | 75% |
| v1.2 | 4.7/5 | 91% | 15s | $0.05 | 90% |

**Optimize for:**
- Quality first
- Then consistency
- Then cost
- Then latency

---

## Troubleshooting

### Problem 1: Inconsistent Outputs

**Symptoms:**
- Same input → different outputs
- Quality varies wildly

**Causes:**
- Prompt too vague
- No format specification
- High temperature setting

**Solutions:**
- ✅ Add explicit format requirements
- ✅ Use few-shot examples
- ✅ Lower temperature (0.3-0.5)
- ✅ Add structure constraints

---

### Problem 2: Off-Topic Responses

**Symptoms:**
- AI doesn't follow instructions
- Goes on tangents
- Ignores constraints

**Causes:**
- Instructions buried in prompt
- Competing instructions
- Ambiguous language

**Solutions:**
- ✅ Put key instructions first
- ✅ Use clear delimiters
- ✅ Be more explicit
- ✅ Add "CRITICAL:" prefix to must-follow rules

---

### Problem 3: Too Verbose

**Symptoms:**
- Outputs are too long
- Rambling responses

**Causes:**
- No length constraint
- LLM default is verbose

**Solutions:**
- ✅ Specify max length: "in under 100 words"
- ✅ Request "concise" or "brief"
- ✅ Use structure that limits length
- ✅ Say "be concise" in system prompt

---

### Problem 4: Hallucinations

**Symptoms:**
- AI makes up facts
- Invents functions/APIs that don't exist
- Confident but wrong

**Causes:**
- Lack of grounding
- No verification
- Asking beyond its knowledge

**Solutions:**
- ✅ Use RAG to ground in real data
- ✅ Ask for sources/citations
- ✅ Request "only use information provided"
- ✅ Add: "If unsure, say 'I don't know'"

---

### Problem 5: Ignoring Edge Cases

**Symptoms:**
- Works for normal inputs
- Fails on edge cases

**Causes:**
- No mention of edge cases in prompt
- No examples of handling them

**Solutions:**
- ✅ Explicitly list edge cases to handle
- ✅ Provide examples of edge case handling
- ✅ Add "Consider edge cases like X, Y, Z"

---

### Problem 6: Wrong Tone

**Symptoms:**
- Too formal or too casual
- Doesn't match brand voice

**Causes:**
- Tone not specified
- Conflicting tone instructions

**Solutions:**
- ✅ Explicitly state desired tone
- ✅ Provide examples in that tone
- ✅ Add personality traits
- ✅ Say "DO NOT be {unwanted tone}"

---

## Best Practices

### Do's ✅

**1. Be Specific**
- ❌ "Make it better"
- ✅ "Improve code clarity by adding comments and renaming variables to be more descriptive"

**2. Provide Context**
- ❌ "Explain this"
- ✅ "Explain this code to a junior developer who's new to Python"

**3. Use Examples**
- ❌ Just tell what you want
- ✅ Show 2-3 examples of good output

**4. Specify Format**
- ❌ Let AI choose format
- ✅ Explicitly define output structure

**5. Set Boundaries**
- ❌ Assume AI knows limits
- ✅ Clearly state what NOT to do

**6. Test Thoroughly**
- ❌ Use first prompt that kind of works
- ✅ Test with 10+ diverse inputs

**7. Iterate**
- ❌ Expect perfection first try
- ✅ Refine based on actual results

**8. Document Prompts**
- ❌ Keep prompts only in code
- ✅ Maintain prompt library with notes

---

### Don'ts ❌

**1. Don't Be Vague**
- Vague → unpredictable
- Specific → consistent

**2. Don't Assume Context**
- AI doesn't know your domain
- Provide all necessary info

**3. Don't Skip Examples**
- Examples dramatically improve quality
- Worth the extra prompt tokens

**4. Don't Ignore Failures**
- Each failure is data
- Use it to improve prompts

**5. Don't Over-Complicate**
- Start simple
- Add complexity only if needed

**6. Don't Forget Edge Cases**
- Normal cases are easy
- Edge cases reveal quality

**7. Don't Set and Forget**
- Prompts need maintenance
- Update as you learn

---

## Prompt Engineering Checklist

**Before deploying a prompt:**

- [ ] Role is clearly defined
- [ ] Context is provided
- [ ] Task is specific and actionable
- [ ] Constraints are explicit
- [ ] Output format is specified
- [ ] 2-3 examples are included
- [ ] Edge cases are addressed
- [ ] Tested with 10+ inputs
- [ ] Pass rate is >85%
- [ ] Tone is appropriate
- [ ] Documented for future reference

---

## Resources for Learning More

**Essential Reading:**
- OpenAI: Prompt Engineering Guide
- Anthropic: Prompting Documentation
- Learn Prompting: learnprompting.org

**Practice:**
- PromptBase: See real prompts
- ShareGPT: Community prompts
- Your own experiments!

**Communities:**
- r/PromptEngineering
- OpenAI Discord
- AI PM communities

---

## Your Prompt Library

**Create a library of your best prompts:**

```markdown
# Prompt Library

## Documentation Generator v3.2
**Use case:** Generate code documentation
**Quality:** 4.7/5
**Pass rate:** 92%

**System Prompt:**
[Your best system prompt]

**User Template:**
[Your user prompt template]

**Notes:**
- Works best with Python and JavaScript
- Struggles with very complex nested logic
- Updated 2024-01-15 to improve example quality

---

## Content Summarizer v2.1
...

---

## Code Reviewer v1.5
...
```

**Maintain version history and performance metrics!**

---

**Prompt engineering is a skill. The more you practice, the better you get. Start simple, test thoroughly, iterate constantly! 🎯**
