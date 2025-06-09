# Modular Multi-Agent System: Homework Triage ExampleThis is a Pyt

hon-based multi-agent system that uses a **triage agent** to determine the appropriate specialist agent (Math or History) to respond to user queries, with a **guardrail system** to filter out non-homework-related questions.This example is based on the You

Tube tutorial:📺 [How to Build a Modular Multi-Agent System in Pytho
n](https://www.youtube.com/watch?v=jZe2Jd9p54Y)---## 🧠 Overview

This project demonstrates how to build a modular multi-agent framework
with:- **Guardrails**: Validate user intent (e.g., is this homework?

)- **Specialist Agents**: Math and History tutors- **Triage Agent**:

Routes input to the correct tutor agent---## 🗂️ Project Struct

ure```text.├── main.py # This file├── agents/

# (Assumed to contain Agent, Runner, InputGuardrail, etc.)

`

