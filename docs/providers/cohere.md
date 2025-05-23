# Cohere

[Get a Cohere API key](https://dashboard.cohere.com/api-keys)

## Usage

{% code title=".env" %}
```bash
COHERE_API_KEY=
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
    provider: 'cohere',
    model: 'command-r-plus',
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

| Model                 | Chat Completion | Streaming | JSON Output | Image Input | Function Calling | N > 1 |
| --------------------- | --------------- | --------- | ----------- | ----------- | ---------------- | ----- |
| command-r-plus        | ✅               | ✅         | ➖           | ➖           | ✅                | ➖     |
| command-r             | ✅               | ✅         | ➖           | ➖           | ✅                | ➖     |
| command               | ✅               | ✅         | ➖           | ➖           | ➖                | ➖     |
| command-nightly       | ✅               | ✅         | ➖           | ➖           | ✅                | ➖     |
| command-light         | ✅               | ✅         | ➖           | ➖           | ➖                | ➖     |
| command-light-nightly | ✅               | ✅         | ➖           | ➖           | ➖                | ➖     |

### Legend
| Symbol             | Description                           |
|--------------------|---------------------------------------|
| :white_check_mark: | Supported by Token.js                 |
| :heavy_minus_sign: | Not supported by the LLM provider, so Token.js cannot support it     |
<!-- end compatibility -->

## Additional Resources

* [Cohere Documentation](https://docs.cohere.com)
