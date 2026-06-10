# ResearchMind · AI-Powered Multi-Agent Research System

A sophisticated AI-driven research system that automates the entire research workflow. ResearchMind orchestrates four specialized agents working collaboratively to gather information, synthesize findings, write polished reports, and provide critical feedback — all from a single research topic.

## Overview

ResearchMind transforms research from a manual, time-consuming process into an automated intelligent workflow. Enter a topic, and the system handles the entire pipeline:

1. **Search Agent** — Gathers recent, reliable web information using Tavily search API
2. **Reader Agent** — Scrapes and extracts deep content from top resources
3. **Writer Chain** — Synthesizes findings into a structured, professional research report
4. **Critic Chain** — Critically reviews the report and provides detailed feedback with scoring

The system is built on LangChain for agent orchestration, powered by OpenAI's GPT-4o-mini, and presented through a beautiful Streamlit web interface with real-time pipeline visualization.

## Key Features

- **Multi-Agent Architecture**: Four specialized agents work together in a coordinated pipeline
- **Real-Time Pipeline Visualization**: Watch each agent work with status indicators (waiting, running, done)
- **Professional Report Generation**: Structured reports with introduction, key findings, conclusion, and sources
- **Critical Evaluation**: AI critic provides scoring (X/10) with strengths and areas for improvement
- **Dark Mode UI**: Modern, aesthetically designed interface with custom fonts and gradients
- **Downloadable Reports**: Export generated research reports as Markdown files
- **Web Scraping**: Extracts clean, readable content from multiple sources
- **Recent Information**: Powered by Tavily API for current, up-to-date research
- **Session State Management**: Persistent results within a Streamlit session

## System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    ResearchMind                              │
│                   (Streamlit App)                            │
└─────────────┬───────────────────────────────────────────────┘
              │
              ├─► [STEP 1] Search Agent ──────────┐
              │           (LangChain)              │
              │           Uses: Tavily API         │
              │           Output: URLs + snippets  │
              │                                    │
              └─► [STEP 2] Reader Agent ──────────┤
              │           (LangChain)              │
              │           Uses: BeautifulSoup      │
              │           Output: Cleaned text     │
              │                                    │
              └─► [STEP 3] Writer Chain ──────────┤
              │           (LangChain + OpenAI)     │
              │           Input: Combined research │
              │           Output: Structured report│
              │                                    │
              └─► [STEP 4] Critic Chain ──────────┘
                          (LangChain + OpenAI)
                          Output: Score + feedback

                    │
                    ▼
            ┌───────────────────┐
            │  Results Display  │
            │  - Raw outputs    │
            │  - Final report   │
            │  - Critic review  │
            │  - Download link  │
            └───────────────────┘
```
