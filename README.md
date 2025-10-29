# Reddit Dialogue Sample Dataset

25,000-sample subset of a larger dataset of Reddit dialogues regarding Human-AI chats.

# Overview

The dataset captures short text excerpts (extracted_dialogue) from Reddit posts across multiple subreddits. 
Each sample is annotated with attributes related to harassment, hate, self-harm, sexual/violent content, emotions, and moral foundations.

The data is stored in a Parquet file format for efficient loading and processing with Python or other data tools.

# Sampling Procedure

A random subset of 25,000 rows was drawn from the full dataset using a seed=81
| Column                   | Type          | Description                                                                                   |
| ------------------------ | ------------- | --------------------------------------------------------------------------------------------- |
| `extracted_dialogue`     | string        | Extracted snippet associated with the post (e.g., quoted or parsed dialogue text if present). |
| `subreddit`              | string        | **Post** subreddit name (posts only; comments are not collected in this sample).              |
| `id`                     | string        | Reddit post ID.     |
| `party`                  | string | null | Categorical tag if present in the upstream source; not guaranteed/populated for all rows.     |
| `text`                   | string        | Full post text/body (when available).                                                         |
| `turn`                   | int | null    | Turn index if the post includes structured/parsed dialogue; may be null otherwise.            |
| `harassment`             | float [0,1]   | **OpenAI Moderation score** for harassment.                                                   |
| `harassment_threatening` | float [0,1]   | **OpenAI Moderation score** for threatening harassment.                                       |
| `hate`                   | float [0,1]   | **OpenAI Moderation score** for hate.                                                         |
| `hate_threatening`       | float [0,1]   | **OpenAI Moderation score** for threatening hate.                                             |
| `self-harm`              | float [0,1]   | **OpenAI Moderation score** for self-harm content.                                            |
| `self-harm_instructions` | float [0,1]   | **OpenAI Moderation score** for self-harm instructions.                                       |
| `self-harm_intent`       | float [0,1]   | **OpenAI Moderation score** for self-harm intent.                                             |
| `sexual`                 | float [0,1]   | **OpenAI Moderation score** for sexual content.                                               |
| `sexual_minors`          | float [0,1]   | **OpenAI Moderation score** for sexual content involving minors.                              |
| `violence`               | float [0,1]   | **OpenAI Moderation score** for violence.                                                     |
| `violence_graphic`       | float [0,1]   | **OpenAI Moderation score** for graphic violence.                                             |
| `illicit`                | float [0,1]   | **OpenAI Moderation score** for illicit behavior.                                             |
| `illicit_violent`        | float [0,1]   | **OpenAI Moderation score** for violent illicit behavior.                                     |
| `anger`                  | float [0,1]   | **DEMUX emotion** score: anger.                                                               |
| `disgust`                | float [0,1]   | **DEMUX emotion** score: disgust.                                                             |
| `fear`                   | float [0,1]   | **DEMUX emotion** score: fear.                                                                |
| `sadness`                | float [0,1]   | **DEMUX emotion** score: sadness.                                                             |
| `anticipation`           | float [0,1]   | **DEMUX emotion** score: anticipation.                                                        |
| `surprise`               | float [0,1]   | **DEMUX emotion** score: surprise.                                                            |
| `optimism`               | float [0,1]   | **DEMUX emotion** score: optimism.                                                            |
| `joy`                    | float [0,1]   | **DEMUX emotion** score: joy.                                                                 |
| `love`                   | float [0,1]   | **DEMUX emotion** score: love.                                                                |
| `trust`                  | float [0,1]   | **DEMUX emotion** score: trust.                                                               |
| `pessimism`              | float [0,1]   | **DEMUX emotion** score: pessimism.                                                           |
| `Purity`                 | float         | Moral/virtue signal (scoring source per your pipeline; numeric).                              |
| `Thin Morality`          | float         | Thin-morality signal (numeric).                                                               |
| `Authority`              | float         | Moral/virtue signal (numeric).                                                                |
| `Equality`               | float         | Moral/virtue signal (numeric).                                                                |
| `Loyalty`                | float         | Moral/virtue signal (numeric).                                                                |
| `Care`                   | float         | Moral/virtue signal (numeric).                                                                |
| `Proportionality`        | float         | Moral/virtue signal (numeric).                                                                |
| `text_id`                | string        | Stable unique identifier for the text/post row.                                               |
