# AgenticAI

This repository contains course materials for **"Agentic AI — from business needs to working agents"**. It includes comprehensive templates, sample agents, and n8n workflow examples to help teams design, implement, and iterate on agentic AI solutions.

## Contents

### [agents/](agents/)
Pre-built n8n workflow agents organized by course lecture and demonstration topics:

**Lecture 1 - Fundamentals:**
- Email Triage Agent
- HR Policy Lookup Agent
- Procurement Review Agent

**Lecture 2 - Advanced Patterns:**
- Agent Evaluation Workflow
- ReAct Pattern - Customer Support Agent
- Plan-and-Execute Agent
- Collaborative Research and Fact-Checking Report Generator
- Multi-Agent System
- Tool Design Workshop

**Lecture 3 - Production Readiness:**
- State Machine - Policy Q&A
- Guardrails - Email Processor
- Retry Circuit Breaker
- Human Approval Gate
- Email Manager

**Demonstrations:**
- CV Screening
- Human in the Loop
- LinkedIn AI Content Automation
- Memory
- RAG (Retrieval-Augmented Generation)

### [templates/](templates/)
Reusable document templates and worksheets to support agent development:
- Agent Canvas Template (with worked examples)
- Agent Specification Template (with worked examples)
- Peer Review Form
- Prompt Evolution Worksheet
- Test Design Template
- Ticket and Reflection documents

## Goals

This course and repository aim to:
- Explain when and why to use agentic architectures in product and business contexts
- Provide hands-on templates and runnable examples to accelerate prototyping
- Demonstrate integration patterns with n8n automation platform
- Establish best practices for safety, observability, and iteration in production systems

## Getting Started

1. **Environment Setup**: Open this workspace in the provided dev container (Ubuntu 24.04.2 LTS) or your local n8n instance.

2. **Explore Templates**: Review the document templates in the [templates/](templates/) directory to understand agent design methodologies.

3. **Import Sample Agents**: 
   - Navigate to the [agents/](agents/) directory
   - Import the JSON workflow files into your n8n instance
   - Start with Lecture 1 agents for foundational patterns

4. **Customize and Adapt**: Modify the example agents to connect with your specific data sources, tools, and business requirements.

## Prerequisites

- n8n workflow automation platform (self-hosted or cloud)
- Basic understanding of AI/LLM concepts
- Access to LLM API (OpenAI, Anthropic, or similar)

## Contributing

Contributions are welcome! To contribute:
- Add new templates or sample agents under the appropriate directory ([agents/](agents/) or [templates/](templates/))
- Keep examples well-documented, small in scope, and reproducible
- Follow existing naming conventions and organizational structure
- Test all workflows before submitting

## License

Please refer to the project or course license documentation before reusing or redistributing materials.
