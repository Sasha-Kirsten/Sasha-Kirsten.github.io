### Hi there 👋

This project builds a **Lecture2Note AI Agent** that turns long-form videos (e.g., lecture recordings, screen recordings, tutorials) into **structured study notes / knowledge artifacts**.

## What it does

It processes a video end-to-end by:

- Downloading it from **S3**
- Extracting audio and **transcribing** it
- Sampling frames and removing duplicates (**keyframe selection**)
- *(Planned)* Extracting diagrams and on-screen text (**OCR**)
- *(Planned)* Scraping referenced URLs to enrich context
- Synthesizing everything into a **high-quality Markdown study guide** using an LLM (e.g., **Bedrock Claude**)

The pipeline is designed to be **restartable**, storing intermediate outputs in **S3** and tracking progress in a persistent `output.json` state file.

## What problem this solves

Lecture videos contain valuable information across multiple modalities:

- **Speech** (explanations, definitions, examples)
- **Slides / visuals** (diagrams, code, charts)
- **On-screen references** (URLs, paper titles, docs)

This project extracts and merges these signals into a single structured output so you can:

- Revise faster
- Search content more easily
- Build a reusable **knowledge base** from videos