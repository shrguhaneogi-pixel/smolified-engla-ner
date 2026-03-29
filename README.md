#smolified-engla-ner

🎯 The Problem Solved
Extracting Structured Data from Code-Mixed English-Bengali (Banglish) Text
In South Asian digital communication, users frequently mix English and Romanized Bengali (e.g., "Amader team project niye Google headquarters e California te last month giyechilo"). Standard Natural Language Processing (NLP) tools and off-the-shelf Named Entity Recognition (NER) models traditionally fail at parsing this code-mixed text because they are trained primarily on standard, monolingual datasets.

This project solves that gap by providing a highly accurate, domain-specific model capable of cleanly extracting key entities—Person (PER), Organization (ORG), Location (LOC), and Date (DATE)—from conversational Banglish and formatting them into a strict, predictable JSON structure.

🧠 Why a Specialized Model Over a General LLM?
While massive general-purpose LLMs (like GPT-4 or Llama-3) can perform NER via complex prompting, a specialized model (gemma-3-270m fine-tuned specifically on 10k synthetic Banglish records) is vastly superior for this specific pipeline for three main reasons:

Extreme Resource Efficiency & Edge Deployment: General LLMs require massive VRAM, expensive cloud compute, or high-latency API calls. Our specialized model is distilled down to just 270M parameters and uses 4-bit quantization/FP16 mixed precision. This allows it to run locally, incredibly fast, entirely on edge hardware (CPUs/NPUs), or in severely VRAM-constrained environments without relying on external APIs.

Domain Accuracy and Cultural Nuance: General LLMs often struggle with the phonetic variations and informal slang inherent in Romanized regional languages unless provided with heavy few-shot prompting. By explicitly instruction-tuning on a dedicated English-Bengali corpus, this specialized model inherently understands the linguistic nuances of Banglish natively.

Structured Output Reliability: General LLMs are prone to hallucination or adding conversational filler (e.g., "Here is your extracted data..."), which breaks automated data pipelines. This specialized model has been rigorously trained to output only the requested JSON format, ensuring 100% predictable, machine-readable responses every single time.
