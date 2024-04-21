---
title: "LLM Farm User Manual"
datePublished: Sat Jan 27 2024 15:17:26 GMT+0000 (Coordinated Universal Time)
cuid: clv8wgp8a000e09jyaw0c9jdq
slug: llm-farm-user-manual
canonical: https://quni.io/2024/01/27/llm-farm-user-manual/
tags: uncategorized

---

### Overview

[LLM Farm](https://apps.apple.com/us/app/llm-farm/id6461209867) is an advanced iOS application that allows users to interact with various large language models. It offers a suite of customization options for fine-tuning language generation according to specific needs.

### Getting Started

1.  **Launch the App**: Open the LLM Farm app on your iOS device.
2.  **Edit Chat**: Tap on ‘Edit Chat’ to configure your language model settings.

### Model Configuration

Select the language model that best suits your task from an extensive list, including options like GPT-2, LLAMA, and others.

#### Model Selection

*   Navigate to the “Inference” field to choose your desired model architecture.
*   Choose from pre-existing models like `gpt2`, `llama`, `replit`, and more.

### Prediction Options

Configure how the model generates predictions.

#### Context Settings

*   **Context Size**: Determine how many previous tokens the model should consider (e.g., 1024 tokens).
*   **N\_Batch**: Set the batch size for prompt processing to manage multiple requests simultaneously.

#### Sampling Methods

Choose how the model will sample predictions.

*   **Greedy**: Selects the most likely next word.
*   **Temperature**: Introduces randomness into the selection process based on a set temperature value.
*   **Mirosat**: A custom sampling method based on target entropy.

#### Penalties

Adjust penalties to control repetition and enhance output quality.

*   **Repeat Penalty**: Penalize repeated sequences to ensure varied responses.
*   **Frequency Penalty**: Discourage frequent use of the same word to maintain diversity.
*   **Presence Penalty**: Avoid reusing words that have already been mentioned.

### Advanced Settings

Delve deeper into customization with advanced settings.

#### numberOfThreads

*   **Description**: Specifies the number of threads the model uses for parallel processing.
*   **Acceptable Values**: Any positive integer or 0 for the maximum available.
*   **Impact Example**: Increasing the number might speed up processing but could lead to higher memory usage.

#### context

*   **Description**: Determines the number of tokens from the previous text the model uses to generate the next word.
*   **Acceptable Values**: Typically, a power of 2, such as 512, 1024, or 2048.
*   **Impact Example**: A larger context size allows the model to consider more of the previous conversation, potentially improving coherence over longer interactions.

#### n\_batch

*   **Description**: The batch size for prompt processing, indicating how many prompts will be processed simultaneously.
*   **Acceptable Values**: Any positive integer, commonly a power of 2 like 16, 32, 64, etc.
*   **Impact Example**: A higher batch size can process more prompts at once but requires more computational resources.

### Sampling Options

#### temp (Temperature)

*   **Description**: Controls the randomness in the prediction distribution.
*   **Acceptable Values**: A decimal typically between 0.1 and 1.0. Values above 1.0 increase randomness, while values below 1.0 make predictions more deterministic.
*   **Impact Example**: Setting `temp` to 0.5 might result in more predictable text, whereas a value of 1.5 could generate more creative and diverse outputs.

#### top\_k

*   **Description**: Limits the next word predictions to the top k most likely words.
*   **Acceptable Values**: Any non-negative integer. Setting to 0 disables this feature.
*   **Impact Example**: Setting `top_k` to 20 restricts the model to consider only the top 20 most probable next words, which can help maintain coherence.

#### top\_p

*   **Description**: Nucleus sampling parameter that chooses from the smallest set of words whose cumulative probability exceeds the threshold p.
*   **Acceptable Values**: A decimal typically between 0 and 1.
*   **Impact Example**: A `top_p` value of 0.9 might generate text with good variability while still being relevant to the prompt.

#### tfs\_z (Tail Free Sampling)

*   **Description**: Adjusts the ‘sharpness’ of the probability distribution tail, controlling how much attention is given to less likely words.
*   **Acceptable Values**: Typically a positive decimal. Higher values make the tail ‘heavier’, giving more chance to less likely words.
*   **Impact Example**: Increasing `tfs_z` may result in more diverse language generation, possibly at the cost of coherence.

#### typical\_p

*   **Description**: Ensures that each selected word is not too unlikely, given a threshold p.
*   **Acceptable Values**: A decimal, usually close to 1.
*   **Impact Example**: Setting `typical_p` to a high value like 0.95 ensures most generated words are within a typical range for the context.

### Penalty Settings

#### repeat\_penalty

*   **Description**: Applies a penalty for repeating the same word or phrase to discourage redundancy.
*   **Acceptable Values**: A decimal typically greater than 1.0.
*   **Impact Example**: A `repeat_penalty` of 1.2 might reduce the repetition of previous words in the output.

#### repeat\_last\_n

*   **Description**: Defines the number of last tokens to check for repetition.
*   **Acceptable Values**: Any positive integer.
*   **Impact Example**: With `repeat_last_n` set to 50, the model will look at the last 50 tokens to avoid repetition, which could help in producing more varied content.

#### frequency\_penalty

*   **Description**: Decreases the likelihood of repeatedly using the same word in generation.
*   **Acceptable Values**: A decimal typically between 0 and 1.
*   **Impact Example**: If `frequency_penalty` is set to 0.5, the model is less likely to repeat words it has already used, encouraging more diverse vocabulary.

#### presence\_penalty

*   **Description**: Discourages the model from using words that have already appeared.
*   **Acceptable Values**: A decimal typically between 0 and 1.
*   **Impact Example**: With a `presence_penalty` of 0.1, there is a slight discouragement from reusing words, promoting lexical diversity without significant impact on content relevance.

### Advanced Sampling

#### mirosat

*   **Description**: Custom sampling based on target entropy (if the field is set to 1, it’s enabled).
*   **Acceptable Values**: Typically 0 (disabled) or 1 (enabled).
*   **Impact Example**: Enabling `mirosat` might adjust the word selection process to maintain a certain level of entropy, possibly leading to more unpredictable and varied text output.

#### mirosat\_tau

*   **Description**: The target entropy value when `mirosat` sampling is enabled.
*   **Acceptable Values**: Positive decimals, where higher values aim for higher entropy in the selection process.
*   **Impact Example**: A higher `mirosat_tau`, like 5.0, encourages the model to produce more diverse and less deterministic outputs, which could be beneficial for creative writing tasks.

### Examples of Settings Impact

*   **Lower** `temperature` **for factual queries**: When asking the model to provide information, a lower temperature (e.g., 0.7) can help produce more precise and relevant answers.
*   **Higher `temperature` for creative tasks**: For creative writing or brainstorming, a higher temperature (e.g., 1.2) can lead to more innovative and varied ideas.
*   **Moderate `top_k` for balanced output**: A mid-range `top_k` (e.g., 40) can offer a balance between creativity and relevance, useful for tasks like article writing.
*   **Tailored `top_p` for nuanced control**: Adjusting `top_p` (e.g., 0.9) allows for dynamic control over the diversity of the text, suitable for scenarios where the model needs to adapt to a wide range of topics.
*   **Penalty adjustments for content quality**: Fine-tuning `repeat_penalty`, `frequency_penalty`, and `presence_penalty` can drastically improve the readability and uniqueness of the content, especially in longer text generations.
*   **Metal**: Toggle to enable Metal for GPU-accelerated model inference (if available).
*   **MMAP**: Enable memory mapping for efficient memory usage.

#### Saving and Templates

*   **Save as new template**: Save your current configuration as a new template for future use.

### Executing a Chat

1.  **Enter Prompt**: Type your prompt in the designated area.
2.  **Send**: Tap ‘Send’ to receive the model’s response based on the configured settings.

### Additional Features

*   **Clear Chat History**: Erase the conversation to start fresh.
*   **Special Tokens**: Use ‘BOS’ (Beginning of Sentence) and ‘EOS’ (End of Sentence) tokens to mark the start and end of your input.