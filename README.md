# Engineer AI Assistant — Telegram Multi-Agent System

An AI-powered engineering assistant built with **n8n, Telegram, OpenAI, and specialized AI Agent tools**. The system helps users explore engineering problems, perform calculations, understand technical concepts, and analyze possible solutions through a conversational Telegram interface.

The system is designed to support engineering work without making final engineering decisions on behalf of the user.

---

## Project Overview

Engineering questions often require different capabilities, including numerical calculations, technical analysis, and theoretical explanations.

This project uses a multi-agent architecture to organize these tasks into specialized AI tools coordinated by a central AI agent.

Users interact with the system through Telegram. The central agent interprets each request, delegates suitable tasks to specialized agents when needed, and returns a consolidated response.

---

## Project Objectives

* Build a conversational engineering assistant accessible through Telegram.
* Implement a centralized AI agent that coordinates specialized AI tools.
* Support engineering calculations and unit conversions.
* Explain engineering concepts, theories, and technical principles.
* Analyze engineering problems and interpret results.
* Maintain conversational context using Simple Memory.
* Keep final engineering judgment and decision-making with the human user.

---

## System Architecture

The workflow follows this general structure:

```text
Telegram Trigger
       |
       v
Main AI Agent
       |
       +---- Simple Memory
       |
       +---- Engineering Calculation Agent
       |              |
       |              +---- Calculator
       |
       +---- Engineering Analysis Agent
       |
       +---- Engineering Knowledge Agent
       |
       v
Telegram Send Message
```

The Main AI Agent acts as the central coordinator. The specialized agents provide task-specific support, and the central agent formulates the final response for the user.

---

## Specialized AI Agents

### 1. Engineering Calculation Agent

Responsible for quantitative engineering tasks, including:

* Applying mathematical and engineering equations.
* Performing numerical calculations using the Calculator tool.
* Handling unit conversions.
* Showing calculation steps.
* Identifying missing parameters and stating assumptions.
* Presenting results with appropriate units.

### 2. Engineering Analysis Agent

Responsible for technical reasoning and engineering problem analysis, including:

* Explaining cause-and-effect relationships.
* Interpreting calculation results.
* Identifying relevant technical factors.
* Comparing possible approaches.
* Exploring potential causes of engineering problems.
* Discussing possible solution approaches and their limitations.

### 3. Engineering Knowledge Agent

Responsible for engineering knowledge and educational explanations, including:

* Explaining engineering concepts and theories.
* Defining technical terminology.
* Describing engineering principles and methods.
* Explaining formulas and their variables.
* Providing examples and discussing practical applications.
* Clarifying relevant assumptions and limitations.

---

## Main AI Agent

The Main AI Agent coordinates the system.

Its responsibilities include:

* Understanding the user's request.
* Determining the type of assistance required.
* Selecting suitable specialized AI tools.
* Delegating tasks when appropriate.
* Combining and organizing returned results.
* Maintaining conversational continuity through Simple Memory.
* Returning a clear response through Telegram.

Simple questions may be answered directly. More specialized requests can be delegated to one or more AI Agent tools.

---

## Example Use Cases

### Engineering Calculations

A user provides engineering parameters and requests a calculation.

The system can identify the required formula, use the Calculator tool, show the calculation steps, and return the result with appropriate units.

### Engineering Analysis

A user asks why a technical phenomenon occurs or how a particular variable affects an engineering system.

The Engineering Analysis Agent explains the relevant relationships and discusses possible influencing factors.

### Engineering Knowledge

A user requests an explanation of a concept such as stress, strain, Reynolds number, voltage drop, or feedback control.

The Engineering Knowledge Agent provides a structured technical explanation appropriate to the question.

### Combined Requests

A user may ask for both a theoretical explanation and a numerical calculation.

The Main AI Agent can coordinate the relevant tools and combine their outputs into one response.

---

## Engineering Disciplines

The system is intended to support questions across a broad range of engineering fields, including:

* Civil and Structural Engineering
* Surveying and Geotechnical Engineering
* Electrical and Electronics Engineering
* Mechanical Engineering
* Chemical Engineering
* Industrial Engineering
* Architecture and Building Systems
* Computer Engineering
* Environmental Engineering
* Materials Engineering
* Mechatronics and Robotics
* Energy Engineering

The reliability of an answer depends on the information provided, the task, and the capabilities of the underlying AI model and tools.

---

## Human-in-the-Loop Principle

The system provides technical assistance rather than final professional engineering judgment.

It can calculate, explain, analyze, compare alternatives, and identify possible solutions. It does not approve or certify designs, provide final construction approval, or replace a qualified engineer's judgment.

For safety-critical applications, results must be independently verified by an appropriately qualified professional.

---

## Technologies Used

* **n8n** — Workflow automation and AI agent orchestration
* **Telegram Bot API** — User interaction and message delivery
* **OpenAI Chat Model** — Language understanding, reasoning, and response generation
* **AI Agent Tools** — Specialized task delegation
* **Calculator** — Numerical calculations
* **Simple Memory** — Conversational context

---

## Repository Structure

```text
engineer-ai-assistant/
├── README.md
├── workflow/
│   └── engineer-ai-assistant.json
└── screenshots/
    ├── workflow.png
    ├── telegram-demo.png
    ├── main-agent.png
    ├── engineering-tools.png
    └── calculation-demo.png
```

---

## Workflow Screenshot

![Complete n8n Workflow](screenshots/workflow.png)

## Telegram Demonstration

![Telegram Assistant Demonstration](screenshots/telegram-demo.png)

## Main AI Agent Configuration

![Main AI Agent Configuration](screenshots/main-agent.png)

## Specialized Engineering Tools

![Engineering Agent Tools](screenshots/engineering-tools.png)

## Calculation Example

![Engineering Calculation Example](screenshots/calculation-demo.png)

---

## Setup and Usage

1. Export the workflow from n8n as a JSON file.
2. Import the JSON file into an n8n instance.
3. Configure the required credentials for Telegram and the OpenAI model.
4. Verify the connections between the Main AI Agent, Simple Memory, specialized AI Agent tools, and Calculator.
5. Configure the Telegram response node to return the Main AI Agent's output to the originating chat.
6. Test the workflow with conceptual questions, calculation requests, and engineering analysis tasks.

**Note:** Exported workflow files do not guarantee that credentials or external service configurations will be available in another n8n instance. Credentials must be configured separately, and the workflow should be tested after import.

---

## Security

* Do not commit API keys, access tokens, passwords, or private credentials.
* Configure credentials securely inside n8n.
* Review exported workflow JSON files before publishing them.
* Avoid including private user information in screenshots or test data.

---

## Limitations

* AI-generated answers may contain errors and require verification.
* Numerical accuracy depends on the correctness of formulas, input values, units, and tool usage.
* The system does not automatically verify compliance with every engineering code or local regulation.
* Persistent memory behavior depends on the selected n8n memory implementation and configuration.
* The system is an assistant for technical exploration, not a certified engineering design or approval system.

---

## Future Improvements

Potential extensions include:

* Image and document input for engineering problems.
* Engineering document retrieval using a Retrieval-Augmented Generation (RAG) system.
* Support for technical PDFs and reference materials.
* More specialized engineering agents.
* Improved numerical validation and calculation testing.
* Structured conversation logging and session management.
* Engineering reference citations and source verification.

---

## Project Purpose

This project demonstrates the practical application of **AI agents, tool orchestration, conversational memory, numerical tools, and workflow automation** in an engineering assistance system.

It was developed as a portfolio project to explore how a centralized AI agent can coordinate specialized tools to support engineering calculations, analysis, and technical learning while preserving human responsibility for final engineering decisions.
