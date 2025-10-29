# Reddit Dialogue Sample Dataset

25,000-sample subset of a larger dataset of Reddit dialogues regarding Human-AI chats.

# Overview

The dataset captures short text excerpts (extracted_dialogue) from Reddit posts across multiple subreddits. 
Each sample is annotated with attributes related to harassment, hate, self-harm, sexual/violent content, emotions, and moral foundations.

The data is stored in a Parquet file format for efficient loading and processing with Python or other data tools.

# Sampling Procedure

A random subset of 25,000 rows was drawn from the full dataset using a seed=81
| Column                   | Type        | Description                                                                                            |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------------------------ |
| `extracted_dialogue`     | string      | The multi-turn context window around the current turn (e.g., lines like `Chatbot: ...` / `USER: ...`). |
| `subreddit`              | string      | Subreddit the **post** came from (posts only in this sample; no comment objects).                      |
| `id`                     | string      | Base Reddit **post ID** (e.g., `17f17iy`).                                                             |
| `party`                  | string      | **Speaker role** label for the current turn (e.g., `USER`, `Chatbot`).                                 |
| `text`                   | string      | The **current turn utterance** text (e.g., “Now give daddy a kiss”).                                   |
| `turn`                   | int         | Turn index within the extracted dialogue (e.g., `1`, `2`, `4`, `6`).                                   |
| `harassment`             | float [0,1] | OpenAI moderation **score** for harassment.                                                            |
| `harassment_threatening` | float [0,1] | OpenAI moderation **score** for threatening harassment.                                                |
| `hate`                   | float [0,1] | OpenAI moderation **score** for hate.                                                                  |
| `hate_threatening`       | float [0,1] | OpenAI moderation **score** for threatening hate.                                                      |
| `self-harm`              | float [0,1] | OpenAI moderation **score** for self-harm content.                                                     |
| `self-harm_instructions` | float [0,1] | OpenAI moderation **score** for self-harm instructions.                                                |
| `self-harm_intent`       | float [0,1] | OpenAI moderation **score** for self-harm intent.                                                      |
| `sexual`                 | float [0,1] | OpenAI moderation **score** for sexual content.                                                        |
| `sexual_minors`          | float [0,1] | OpenAI moderation **score** for sexual content involving minors.                                       |
| `violence`               | float [0,1] | OpenAI moderation **score** for violence.                                                              |
| `violence_graphic`       | float [0,1] | OpenAI moderation **score** for graphic violence.                                                      |
| `illicit`                | float [0,1] | OpenAI moderation **score** for illicit behavior.                                                      |
| `illicit_violent`        | float [0,1] | OpenAI moderation **score** for violent illicit behavior.                                              |
| `anger`                  | float [0,1] | Emotion score (DEMUX): anger.                                                                          |
| `disgust`                | float [0,1] | Emotion score (DEMUX): disgust.                                                                        |
| `fear`                   | float [0,1] | Emotion score (DEMUX): fear.                                                                           |
| `sadness`                | float [0,1] | Emotion score (DEMUX): sadness.                                                                        |
| `anticipation`           | float [0,1] | Emotion score (DEMUX): anticipation.                                                                   |
| `surprise`               | float [0,1] | Emotion score (DEMUX): surprise.                                                                       |
| `optimism`               | float [0,1] | Emotion score (DEMUX): optimism.                                                                       |
| `joy`                    | float [0,1] | Emotion score (DEMUX): joy.                                                                            |
| `love`                   | float [0,1] | Emotion score (DEMUX): love.                                                                           |
| `trust`                  | float [0,1] | Emotion score (DEMUX): trust.                                                                          |
| `pessimism`              | float [0,1] | Emotion score (DEMUX): pessimism.                                                                      |
| `Purity`                 | float       | Moral-language score (numeric).                                                                        |
| `Thin Morality`          | float       | Thin-morality score (numeric).                                                                         |
| `Authority`              | float       | Moral-language score (numeric).                                                                        |
| `Equality`               | float       | Moral-language score (numeric).                                                                        |
| `Loyalty`                | float       | Moral-language score (numeric).                                                                        |
| `Care`                   | float       | Moral-language score (numeric).                                                                        |
| `Proportionality`        | float       | Moral-language score (numeric).                                                                        |
| `text_id`                | string      | Unique per-turn identifier: `"{id}_{turn}"` (e.g., `17f17iy_4`).                                       |
