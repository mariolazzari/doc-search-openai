# Build a Document Search Assistant with Node and OpenAI's Assistants API

## Introduction

### Setup

```sh
pnpm i
pnpm start
```

## Building an assistant

### First file

[Assistants API](https://platform.openai.com/docs/api-reference/assistants)

```js
// Script to create the assistant
const openai = require("./config");

let assistantId = "";

// create assistant
async function createAssistant() {
  try {
    const response = await openai.beta.assistants.create({
      name: "Document Search",
      model: "gpt-4o",
      instructions:
        "You are a document search assistant. Answer user queries with relevant information from the documents, or politely explain if none is found.",
    });

    assistantId = response.id;
    console.log("Assistant created with ID: ", assistantId);
  } catch (error) {
    console.error("Error creating assistant:", error.message);
  }
}
```
