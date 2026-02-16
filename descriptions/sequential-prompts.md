**Title:** Run a sequence of prompts through one AI agent session with shared memory

---

Test workflow that sends multiple prompts one-by-one to the same AI agent while preserving memory context between steps.

## How it works

1. Starts manually
2. Defines an array of prompts
3. Splits prompts into individual items
4. Loops through items with **Split In Batches**
5. Sends each prompt to **AI Agent**
6. Uses **Window Buffer Memory** with a fixed session key so prior responses remain in context
7. Aggregates all outputs at the end

## Setup

1. Add your model credential to **OpenAI Chat Model**
2. Run manually and inspect the aggregated output

## Customization

- **Prompt list:** edit `prompts` in **Define Prompts**
- **Memory behavior:** change `sessionKey` or memory window settings
- **Model/provider:** swap **OpenAI Chat Model** with your preferred compatible model node
