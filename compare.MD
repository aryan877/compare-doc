# Qwen Coder 3 (Cerebras) vs GPT-5: Quick Comparison Guide

## Overview

This guide compares **Qwen Coder 3 480B on Cerebras** (accessed via OpenRouter) with **GPT-5** (accessed directly via OpenAI) for coding tasks.

---

## Qwen Coder 3 480B on Cerebras (via OpenRouter)

### Pricing
- **Input tokens**: $2.00 per million tokens
- **Output tokens**: $2.00 per million tokens
- **Flat rate**: Same pricing for both input and output

### Performance
- **Throughput**: Up to 2,000 tokens/second
- **Speed advantage**: ~20-30x faster than GPU-based models
- **Context window**: 131K tokens
- **Model**: 480B parameters (MoE architecture)

### Setup Requirements
**You only need:**
1. OpenRouter API key (get from https://openrouter.ai/)
2. Set model to: `qwen/qwen3-coder-480b`
3. Optionally specify provider routing to use Cerebras specifically

**No direct Cerebras API key needed** - OpenRouter handles the routing to Cerebras infrastructure.

### Use Cases
- Code generation with extremely fast response times
- Large codebase analysis (131K context)
- Real-time coding assistance
- Budget-friendly for high output scenarios

---

## GPT-5 (via OpenAI)

### Pricing
- **Input tokens**: $1.25 per million tokens
- **Output tokens**: $10.00 per million tokens
- **Note**: 8x price difference between input and output

### Performance
- **Throughput**: Standard GPU speeds (slower than Cerebras)
- **Context window**: 400K tokens input (128K max output)
- **Model**: Latest GPT-5 (released Aug 2025)
- **Capabilities**: Text, vision, advanced reasoning

### Setup Requirements
**You need:**
1. Direct OpenAI API key (get from https://platform.openai.com/)
2. OpenAI account with billing enabled
3. Access to GPT-5 API (may require waitlist/approval)
4. Set model to: `gpt-5-2025-08-07`

### Use Cases
- Complex reasoning and agentic tasks
- Multi-modal applications (text + vision)
- Very large context needs (up to 400K)
- Tasks requiring latest AI capabilities

---

## Cost Comparison Examples

### Example 1: Simple Code Generation
**Input**: 1,000 tokens | **Output**: 500 tokens

- **Qwen Coder 3**: $0.002 + $0.001 = **$0.003**
- **GPT-5**: $0.00125 + $0.005 = **$0.00625**

### Example 2: Large Code Generation
**Input**: 10,000 tokens | **Output**: 5,000 tokens

- **Qwen Coder 3**: $0.02 + $0.01 = **$0.03**
- **GPT-5**: $0.0125 + $0.05 = **$0.0625**

### Example 3: Code Review (High Input, Low Output)
**Input**: 50,000 tokens | **Output**: 1,000 tokens

- **Qwen Coder 3**: $0.10 + $0.002 = **$0.102**
- **GPT-5**: $0.0625 + $0.01 = **$0.0725**

**Winner for input-heavy tasks**: GPT-5 (cheaper input)

### Example 4: Code Generation (Low Input, High Output)
**Input**: 5,000 tokens | **Output**: 20,000 tokens

- **Qwen Coder 3**: $0.01 + $0.04 = **$0.05**
- **GPT-5**: $0.00625 + $0.20 = **$0.20625**

**Winner for output-heavy tasks**: Qwen Coder 3 (flat rate)

---

## Quick Decision Matrix

| Factor | Choose Qwen Coder 3 (Cerebras) | Choose GPT-5 |
|--------|-------------------------------|--------------|
| **Speed Priority** | ✓ (2,000 tokens/s) | |
| **High Output Volume** | ✓ (flat $2/M rate) | |
| **Input-Heavy Tasks** | | ✓ (cheaper input $1.25/M) |
| **Budget Constraint** | ✓ (predictable costs) | Depends on I/O ratio |
| **Largest Context** | | ✓ (400K vs 131K) |
| **Multi-modal** | | ✓ (vision support) |
| **Coding Tasks** | ✓ (specialized for code) | ✓ (general purpose) |
| **Setup Simplicity** | ✓ (one API key via OpenRouter) | More setup required |

---

## Speed Comparison

**Response time for 1,000 token output:**
- **Qwen Coder 3 on Cerebras**: ~0.5 seconds
- **GPT-5**: ~10-20 seconds (typical GPU speed)

**Winner**: Qwen Coder 3 is 20-40x faster in throughput

---

## Recommendations

### Choose Qwen Coder 3 (Cerebras) if:
- Speed is critical for your workflow
- You generate a lot of code (high output tokens)
- You want predictable, flat-rate pricing
- You need fast iteration cycles
- Your context fits within 131K tokens
- You prefer simpler API setup (just OpenRouter)

### Choose GPT-5 if:
- You need vision/multi-modal capabilities
- You're doing mostly code review/analysis (high input, low output)
- You need very large context (>131K tokens)
- You need the absolute latest AI reasoning capabilities
- You're doing complex agentic workflows

---

## API Setup Comparison

### Qwen Coder 3 via OpenRouter
```bash
# 1. Get OpenRouter API key from https://openrouter.ai/
# 2. Use in your code:

export OPENROUTER_API_KEY="your-key-here"

# OpenAI-compatible endpoint:
# https://openrouter.ai/api/v1/chat/completions
# Model: qwen/qwen3-coder-480b
```

### GPT-5 via OpenAI
```bash
# 1. Sign up at https://platform.openai.com/
# 2. Add payment method
# 3. Generate API key
# 4. Use in your code:

export OPENAI_API_KEY="your-key-here"

# Endpoint:
# https://api.openai.com/v1/chat/completions
# Model: gpt-5-2025-08-07
```

---

## Bottom Line

**For pure coding speed and cost-effective generation**: **Qwen Coder 3 on Cerebras wins** with 2,000 tokens/s and flat $2/M pricing.

**For versatility, largest context, and cutting-edge AI**: **GPT-5 wins** but costs more for high output scenarios.

**Best of both worlds**: Use OpenRouter for Qwen Coder 3 (Cerebras) for fast coding tasks, and GPT-5 for complex reasoning/multi-modal needs.
