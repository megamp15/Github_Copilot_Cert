# Prompt Engineering Basics

## The 4 Ss Framework

| Principle | Meaning |
|-----------|---------|
| **Single** | Focus on one well-defined task |
| **Specific** | Use explicit, detailed instructions |
| **Short** | Keep prompts concise |
| **Surround** | Provide context via filenames and open files |

## Learning Approaches

| Approach | Description | Best For |
|----------|-------------|----------|
| **Zero-shot** | No examples provided | Common patterns, standard functionality |
| **One-shot** | Single example given | Consistency across codebase |
| **Few-shot** | Multiple examples provided | Complex scenarios, edge cases |

## Advanced Techniques

| Technique | Purpose | Example |
|-----------|---------|---------|
| **Chain Prompting** | Manage long conversations efficiently | Summarize context instead of repeating full history |
| **Role Prompting** | Get expert-level responses | "Act as a cybersecurity expert..." |

**Best Practices**: Be clear/explicit, add contextual comments, provide examples, iterate to refine

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/2-prompt-engineering-foundations-best-practices)

# Prompt Process Flow

**Inbound**: HTTPS → Context gathering (code, files, tabs) → Proxy filter → Toxicity filter → LLM generation

**Outbound**: Post-processing → Validation (security, quality, public code match) → Delivery → Feedback loop

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/3-github-copilot-user-prompt-process-flow)

# Copilot Data Handling

**Code Suggestions**: Prompts NOT retained, discarded after use

**Chat**: 28-day retention for chat outside editor; supports direct questions, code requests, open-ended queries

**Context Windows**: Standard (200-500 lines), Chat (4k tokens)

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/4-github-copilot-data)

# LLMs in Copilot

**What**: AI models trained on vast text data with billions of parameters

**Role**: Context-aware suggestions considering current file + open tabs

**LoRA Fine-Tuning**: GitHub's efficient method - adds trainable parts without changing original model (faster, less resource-heavy)

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/5-github-copilot-large-language-models)
