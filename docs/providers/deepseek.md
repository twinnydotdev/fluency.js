# Cohere

[Get a Deekseek API key](https://platform.deepseek.com/api_keys)

## Usage

{% code title=".env" %}
```bash
DEEPSEEK_API_KEY=
```
{% endcode %}

```typescript
import { TokenJS } from 'fluency.js'

// Create the Token.js client
const tokenjs = new TokenJS()

async function main() {
  // Create a model response
  const completion = await tokenjs.chat.completions.create({
    // Specify the provider and model
    provider: 'deepseek',
    model: 'deepseek-chat',
    // Define your message
    messages: [
      {
        role: 'user',
        content: 'Hello!',
      },
    ],
  })
  console.log(completion.choices[0])
}
main()
```

<!-- compatibility -->
## Supported Models

| Model             | Chat Completion | Streaming | JSON Output | Image Input | N > 1 | Function Calling |
| ----------------- | --------------- | --------- | ----------- | ----------- | ----- | ---------------- |
| deepseek-chat     | ✅               | ✅         | ➖           | ➖           | ➖     | ➖                |
| deepseek-reasoner | ✅               | ✅         | ➖           | ➖           | ➖     | ➖                |

### Legend
| Symbol             | Description                           |
|--------------------|---------------------------------------|
| :white_check_mark: | Supported by Token.js                 |
| :heavy_minus_sign: | Not supported by the LLM provider, so Token.js cannot support it     |
<!-- end compatibility -->

## Additional Resources

* [Deepseek Documentation](https://api-docs.deepseek.com/)
