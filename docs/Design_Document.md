# AI Minute — AI Content Automation System

## Design Document

**Version:** 1.0  
**Project Type:** AI Automation System  
**Platform:** Instagram Carousel Content Generation  
**Automation Engine:** n8n  

---

# 1. Project Overview

## 1.1 Introduction

AI Minute is an AI-powered content automation system designed to discover trending AI topics, generate educational Instagram carousel posts, create branded designs automatically, and schedule publishing with human approval.

The system combines AI research agents, Large Language Models (LLMs), workflow automation, and social media integrations to automate the complete content creation pipeline.

---

## 1.2 Problem Statement

Creating high-quality educational AI content requires multiple manual steps:

- Searching for recent AI trends
- Understanding complex AI concepts
- Selecting suitable topics for the audience
- Writing educational explanations
- Designing carousel posts
- Creating captions
- Scheduling publications

This process is time-consuming and requires continuous research.

The goal is to automate this workflow while maintaining content quality and human control.

---

# 2. Project Goals

The system aims to:

- Automatically discover trending AI topics.
- Identify educational topics suitable for AI learners.
- Avoid repeating previously published content.
- Generate simple and engaging educational carousel content.
- Automate Instagram post creation.
- Reduce manual content preparation time.
- Maintain human approval before publishing.

---

# 3. Scope

## 3.1 MVP Scope

The first version will support:

✅ AI topic research  
✅ Trend analysis  
✅ Content generation  
✅ Instagram carousel creation  
✅ Caption generation  
✅ Telegram approval workflow  
✅ Canva template automation  
✅ Instagram scheduling and publishing  

---

## 3.2 Out of Scope

The MVP will not include:

- Video generation
- TikTok publishing
- LinkedIn publishing
- Automated comment responses
- Advanced analytics dashboard

These features can be considered future improvements.

---

# 4. High-Level System Design

## 4.1 System Architecture Overview

The system consists of several AI-powered modules:

```text
                 AI Minute Automation System


                       Daily Trigger

                            |
                            ↓

                  AI Research Agent

                            |
                            ↓

              Trend Analysis Agent

                            |
                            ↓

          Topic Planning & Validation

                            |
                            ↓

             Content Generation Agent

                            |
                            ↓

             Caption Generation Agent

                            |
                            ↓

              Telegram Approval

                            |
                            ↓

                Canva Automation

                            |
                            ↓

              Design Approval

                            |
                            ↓

             Publishing Queue

                            |
                            ↓

              Instagram Publishing
```

---

# 5. System Components

## 5.1 AI Research Agent

### Responsibility

Discover new and trending AI topics from multiple sources.

---

### Data Sources

The agent uses a hybrid research approach:

### Trusted Sources

Examples:

- OpenAI Blog
- Google AI Blog
- Anthropic Blog
- Hugging Face Blog
- arXiv AI Research

### Web Search

Using search APIs to discover:

- Trending discussions
- New AI tools
- Emerging concepts
- Community interest

---

### Output Example

```json
{
  "topic": "AI Agents",
  "source": "Multiple AI communities",
  "trend_reason": "Increasing adoption in automation",
  "category": "AI Automation"
}
```

---

# 5.2 Trend Analysis & Topic Selection Agent

## Responsibility

Evaluate discovered topics and select the best topic for AI Minute.

The agent considers:

- Current popularity
- Educational value
- Audience relevance
- Difficulty level
- Previous published topics
- Content sequence

---

## Topic Sequence Management

The system maintains a structured learning journey.

Example:

```text
Generative AI Basics

        ↓

Large Language Models

        ↓

AI Agents

        ↓

RAG Systems

        ↓

AI Automation
```

This prevents random content generation.

---

# 5.3 Content History & Memory System

## Purpose

Prevent duplicate or highly similar topics.

---

## Storage

Airtable will be used as the content database.

---

## Content History Table

| Field | Description |
|---|---|
| Topic | Published topic |
| Category | AI concept category |
| Summary | Short explanation |
| Keywords | Related concepts |
| Publication Date | Date published |
| Status | Generated / Published |

---

## Duplicate Detection Process

```text
New Topic

    ↓

Compare with Airtable History

    ↓

Similarity Check

    ↓

Duplicate?

  Yes        No

Reject    Continue
```

---

# 5.4 Content Generation Agent

## Responsibility

Generate Instagram carousel content.

---

## Carousel Structure

The output contains 5 slides:

### Slide 1 — Hook

Purpose:
Capture attention.

Example:

> AI Agents are changing how we automate work. But what are they?

---

### Slide 2 — Definition

Answers:

"What is this concept?"

---

### Slide 3 — Importance

Answers:

"Why is it important?"

---

### Slide 4 — Usage

Answers:

"How can people use it?"

---

### Slide 5 — Examples

Answers:

"What are real-world examples?"

---

## Content Requirements

Generated content must be:

- Simple
- Educational
- Beginner-friendly
- Short
- Engaging

---

# 5.5 Caption Generation Agent

The system generates Instagram captions.

## Caption Structure

```text
Hook

↓

Explanation

↓

Call To Action (CTA)
```

Example:

> Follow AI Minute for simple AI explanations.

---

# 6. Human Approval Workflow

Human approval is required before publishing.

---

## First Approval

Telegram sends:

- Topic
- Carousel content
- Caption

User actions:

✅ Approve  
❌ Reject  

---

## Rejection Flow

```text
Reject

   ↓

Generate New Version

   ↓

Send Telegram Again
```

---

# 7. Canva Automation

## Purpose

Convert generated content into branded Instagram carousel designs.

---

## Process

```text
Approved Content

        ↓

Canva API

        ↓

AI Minute Template

        ↓

Replace Placeholders

        ↓

Generate Images
```

---

## Template Mapping

| Slide | Placeholder |
|---|---|
| Slide 1 | Hook |
| Slide 2 | Definition |
| Slide 3 | Importance |
| Slide 4 | Usage |
| Slide 5 | Examples |

---

# 8. Design Approval

After Canva generation:

The final carousel is sent through Telegram.

User approves:

✅ Ready for publishing  
❌ Reject design  

---

# 9. Publishing Queue System

## Purpose

Manage scheduled Instagram publishing.

---

## MVP Implementation

Use:

**n8n Queue Mode**

Reasons:

- Native integration with automation workflow
- Simple deployment
- Suitable for MVP scale

---

## Future Improvement

For large-scale production:

- Redis Queue
- Dedicated workers

---

# 10. Instagram Publishing

Workflow:

```text
Publishing Queue

        ↓

Scheduler

        ↓

Instagram API

        ↓

Published Carousel
```

---

# 11. Technical Stack

| Component | Technology |
|---|---|
| Automation | n8n |
| AI Models | GPT / Gemini |
| Research | Web Search API + RSS |
| Database | Airtable |
| Communication | Telegram Bot API |
| Design | Canva API |
| Publishing | Instagram Graph API |

---

# 12. Sequence Diagram

```text
User

 ↓

AI Research Agent

 ↓

Search APIs + AI Sources

 ↓

Trend Analysis Agent

 ↓

Airtable History Check

 ↓

Content Generator

 ↓

Caption Generator

 ↓

Telegram Bot

 ↓

User Approval

 ↓

Canva API

 ↓

Generate Carousel

 ↓

Telegram Bot

 ↓

Design Approval

 ↓

Publishing Queue

 ↓

n8n Scheduler

 ↓

Instagram API

 ↓

Published Post
```

---

# 13. Error Handling

The system should handle:

## Research Failure

Fallback to available sources.

---

## AI Generation Failure

Retry generation.

---

## API Failure

Implement:

- Retry mechanism
- Error notifications

---

## Publishing Failure

Keep the post in queue until successful publishing.

---

# 14. Future Enhancements

Possible improvements:

- Multi-platform publishing
- Analytics-based topic selection
- Performance feedback loop
- AI-generated videos
- Vector database for advanced semantic memory
- Personalized content strategy

---

# 15. Success Metrics

The project success can be measured by:

- Reduction in manual content creation time
- Number of generated posts
- Approval success rate
- Publishing reliability
- Content quality
- Topic diversity
