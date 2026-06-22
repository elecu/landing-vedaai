# Veda AI — Sanskrit-to-Spanish Translation Pipeline

This repository hosts **Veda AI**, a project that publishes AI-assisted Spanish translations of classical Sanskrit texts (starting with the Bhagavatam and Brahma Samhita).

The published output is a browsable, readable edition of each translated text. The translations themselves are produced by a multi-stage NLP pipeline.

## What the pipeline does

1. **Base machine translation** — a transformer model (mBART, with a Marian model as fallback) translates the source verses.
2. **Glossary enforcement** — a custom terminology database ensures Sanskrit proper nouns and technical terms are translated consistently across the whole corpus rather than verse by verse.
3. **Post-editing model** — a fine-tuned model corrects vocabulary and stylistic drift introduced by the base translator.
4. **Style classification** — a separate classifier checks tone/register consistency across the text.
5. **Lexical cleanup and contextual repair** — automated passes detect and fix invented or out-of-context words, with checkpoints saved at each stage for traceability.
6. **LLM review pass** — translated text is chunked and sent through a large language model (Gemini) for a final quality and fidelity review against the source.
7. **Export** — the reviewed text is rendered into a static edition for publication on the site.

## Why this is relevant

The project demonstrates an end-to-end applied NLP/data workflow: data preparation, model selection and chaining, terminology/data quality control, automated QA checks, and a reproducible pipeline producing a versioned, checkpointed dataset — skills that map directly onto data analysis and applied AI work (data cleaning, pipeline design, quality validation, and working with LLM APIs).
