# Reddit Dialogue Sample Dataset

This repository contains a 25,000-sample subset of a larger dataset of Reddit dialogues. The sample was generated to facilitate faster experimentation and prototyping for emotion, morality, and toxicity modeling.

# Overview

The dataset captures short text excerpts (extracted_dialogue) from Reddit posts across multiple subreddits. 
Each sample is annotated with attributes related to harassment, hate, self-harm, sexual/violent content, emotions, and moral foundations.

The data is stored in a Parquet file format for efficient loading and processing with Python or other data tools.

# Sampling Procedure

A random subset of 25,000 rows was drawn from the full dataset using a seed=81

| Column                                                                                                             | Description                                                             |
| :----------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------- |
| `extracted_dialogue`                                                                                               | The extracted Reddit comment or dialogue snippet.                       |
| `subreddit`                                                                                                        | Name of the subreddit the post/comment originated from.                 |
| `id`                                                                                                               | Original Reddit post or comment ID.                                     |
| `party`                                                                                                            | Political or ideological leaning (if applicable).                       |
| `text`                                                                                                             | Full text content (if longer than extracted snippet).                   |
| `turn`                                                                                                             | Position of the message in a dialogue thread.                           |
| `harassment`, `harassment_threatening`                                                                             | Binary indicators of harassment or threatening harassment.              |
| `hate`, `hate_threatening`                                                                                         | Binary indicators of hate speech or threatening hate speech.            |
| `self-harm`, `self-harm_instructions`, `self-harm_intent`                                                          | Self-harm–related labels (general, instructional, or intentional).      |
| `sexual`, `sexual_minors`                                                                                          | Flags for sexual or minor-related content.                              |
| `violence`, `violence_graphic`                                                                                     | Flags for violent or graphically violent content.                       |
| `illicit`, `illicit_violent`                                                                                       | Flags for illicit activity or violent illicit acts.                     |
| `anger`, `disgust`, `fear`, `sadness`, `anticipation`, `surprise`, `optimism`, `joy`, `love`, `trust`, `pessimism` | Emotion indicators derived from lexical or model-based emotion tagging. |
| `Purity`, `Thin Morality`, `Authority`, `Equality`, `Loyalty`, `Care`, `Proportionality`                           | Scores for moral foundation categories.                                 |
| `text_id`                                                                                                          | Unique identifier for each text instance.                               |
