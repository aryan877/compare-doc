# Qwen Coder 3 vs GPT-5: Test Generation Site

**Use Case**: Short question input → LeetCode-style output (code, tests, explanations)

---

## The Numbers

| Model | Input Price | Output Price | Speed |
|-------|-------------|--------------|-------|
| **Qwen Coder 3** (Cerebras) | $2/M | $2/M | 2,000 tok/s |
| **GPT-5** (OpenAI) | $1.25/M | $10/M | ~100 tok/s |

---

## Your Use Case: 500 input → 10,000 output tokens

**Qwen Coder 3**:
- Cost: $0.021 per generation
- Time: ~5 seconds

**GPT-5**:
- Cost: $0.10 per generation (5x more expensive)
- Time: ~100 seconds (20x slower)

**Winner**: Qwen Coder 3 by a landslide

---

## Why Qwen Wins for Test Generation

1. **Output-heavy workload** → Flat $2 rate beats GPT-5's $10 output rate
2. **Speed matters** → 2,000 tok/s = instant results
3. **Simple setup** → One OpenRouter API key, done
4. **Code specialist** → Built for coding tasks

---

## Setup

**Qwen Coder 3 (OpenRouter)**:
```bash
export OPENROUTER_API_KEY="sk-or-..."
# Model: qwen/qwen3-coder-480b
# Endpoint: https://openrouter.ai/api/v1/chat/completions
```

**GPT-5 (OpenAI)** - only if you need it:
```bash
export OPENAI_API_KEY="sk-..."
# Model: gpt-5-2025-08-07
# Endpoint: https://api.openai.com/v1/chat/completions
```

---

## Bottom Line

For generating LeetCode-style problems with lots of code:
- **Use Qwen Coder 3** → 5x cheaper, 20x faster
- **Skip GPT-5** → Only makes sense if you need vision/multimodal or 400K context

