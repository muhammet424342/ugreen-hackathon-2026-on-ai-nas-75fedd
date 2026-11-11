# AI-NAS-Organizer

**A lightweight AI skill that organizes NAS files by extracting metadata, generating summaries, and tagging content using free-tier models**

## Problem
Users with UGREEN AI NAS store large volumes of photos, videos, and documents but struggle to find, categorize, and manage them efficiently. Manual organization is time-consuming, and existing tools lack context-aware summarization or intelligent tagging.

## Solution
AI-NAS-Organizer is a simple AI skill that runs on UGREEN AI NAS. It scans authorized files, extracts metadata (e.g., date, location, content type), generates short summaries using a free LLM (e.g., Llama 3.2), and applies intelligent tags based on content. The skill uses the NAS file system and document capabilities to automate organization without requiring user input.

## How It Fits This Listing
| Requirement | Feature Mapping |
|-----------|-----------------|
| Build an AI Skill using NAS files and data | Uses authorized files and documents from UGREEN AI NAS |
| Automate Workflow | Organizes content, extracts info, generates summaries |
| Use NAS CLI capabilities | Leverages file listing, read, and metadata extraction |
| Use AI models for content understanding | Uses free-tier LLMs via API for summarization and tagging |
| Submit PDF proposal and ZIP package | Complete submission package built for Devpost |

## Architecture
- **Frontend**: Single-page web app (React/Vite) for testing and demo
- **Backend**: Cloudflare Worker (serverless) to handle API calls to NAS and LLM
- **LLM**: Free-tier model (e.g., Llama 3.2 via Ollama or Hugging Face Inference API)
- **Storage**: Local KV for caching metadata and tags
- **Workflow**:  
  1. User triggers skill via NAS CLI or web interface  
  2. Skill lists authorized files and reads metadata  
  3. For each file, extracts text (if document) or analyzes media via OCR/audio transcription  
  4. Sends content to LLM for summary and tag generation  
  5. Stores results in NAS or local KV  
  6. Returns organized file list with tags and summaries

## Try It
- **Demo Web App**: [[MUHAMMET: dogru link]]([MUHAMMET: dogru link]) (mock UI, no real NAS access)
- **Skill Package**: [Download ZIP](https://github.com/muhammet424342/ai-nas-organizer/archive/refs/heads/main.zip)

## What Is Live vs TO BUILD
- **Live**:  
  - Web app frontend (mock UI)  
  - Cloudflare Worker stub with file list mock  
  - LLM integration placeholder  
- **TO BUILD**:  
  - Full skill package (SKILL.md, ZIP) compliant with Uliya standard  
  - Real NAS CLI integration (via UGREEN API or CLI tools)  
  - File processing pipeline (OCR, transcription, metadata extraction)  
  - End-to-end test on NAS (requires UGREEN AI NAS device)  

## Roadmap
1. Finalize SKILL.md with required fields (name, description, inputs, workflow)  
2. Implement NAS file access via CLI and API  
3. Add document/text extraction (PDF, TXT, DOCX)  
4. Integrate LLM for summarization and tagging  
5. Build test cases for photos, videos, and documents  
6. Package for submission

## Honest Limitations
- No real NAS access in prototype; testing requires UGREEN AI NAS device  
- Free-tier LLMs have rate limits and latency  
- OCR and transcription accuracy depends on file quality  
- No user authentication or persistence (prototype only)  
- Depends on UGREEN AI NAS CLI and API (not yet public)  

---
