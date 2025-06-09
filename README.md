# Homework Triage Agent System

A multi-agent system that intelligently routes homework questions to specialized tutoring agents while filtering out non-homework queries using guardrails.

## Overview

This project demonstrates how to build a triage system using AI agents that:
- **Filters** incoming queries to ensure they're homework-related
- **Routes** homework questions to appropriate specialist agents
- **Provides** specialized tutoring for math and history subjects

## Tutorial Source

This code is based on the tutorial: [AI Agents Tutorial](https://www.youtube.com/watch?v=jZe2Jd9p54Y)

## System Architecture

The system consists of four main agents:

### 1. Guardrail Agent
- **Purpose**: Validates if user input is homework-related
- **Output**: Boolean determination with reasoning
- **Prevents**: Non-homework queries from reaching tutoring agents

### 2. Triage Agent
- **Purpose**: Central coordinator that routes validated homework questions
- **Features**: Input guardrails and handoff capabilities
- **Routes to**: Math Tutor or History Tutor based on question type

### 3. Math Tutor Agent
- **Specialty**: Mathematics problems and concepts
- **Approach**: Step-by-step explanations with examples
- **Handoff target**: Receives math-related homework questions

### 4. History Tutor Agent
- **Specialty**: Historical questions and events
- **Approach**: Contextual explanations of events and significance
- **Handoff target**: Receives history-related homework questions

## Key Components

### Guardrail Function
```python
async def homework_guardrail(ctx, agent, input_data):
    # Validates homework vs non-homework queries
    # Returns GuardrailFunctionOutput with tripwire status
```

### Output Models
- `HomeworkOutput`: Pydantic model for structured guardrail responses
- `GuardrailFunctionOutput`: Controls agent flow based on validation

## How It Works

1. **Input Validation**: User query hits the triage agent
2. **Guardrail Check**: Homework guardrail validates the query
3. **Tripwire Logic**: Non-homework queries are blocked
4. **Agent Routing**: Valid homework questions are routed to appropriate tutors
5. **Specialized Response**: Tutor agents provide subject-specific assistance

## Example Usage

The script includes two test cases:

```python
# Valid homework question - routes to History Tutor
"who was the first president of the united states?"

# Non-homework question - blocked by guardrail
"what is life"
```

## Prerequisites

```bash
pip install agents pydantic
```

## Running the Code

```bash
python main.py
```

## Expected Behavior

- **Homework questions**: Successfully routed to appropriate tutor agents
- **Non-homework questions**: Blocked by guardrail system
- **Output**: Structured responses from specialist agents or guardrail blocks

## Key Learning Points

- **Agent Orchestration**: How to coordinate multiple AI agents
- **Input Validation**: Using guardrails to filter inappropriate inputs
- **Dynamic Routing**: Intelligent handoffs between specialized agents
- **Structured Outputs**: Using Pydantic models for consistent responses

## Customization

You can extend this system by:
- Adding more subject-specific tutor agents
- Modifying guardrail logic for different validation criteria
- Enhancing triage logic for better routing decisions
- Adding more sophisticated output formatting