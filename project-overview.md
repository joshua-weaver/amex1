# Project Overview: Amex AI Agent

## Objective
Build a local, Claude-first AI tool that automates the monthly process of compiling American Express (Amex) expense reports. The tool will use AI to:
- Retrieve the most recent Amex statement and receipts from Gmail and Outlook.
- Match expenses with appropriate accounting codes from a reference Excel sheet.
- Populate a standardized cover page.
- Assemble a PDF report including the cover page, Amex statement, and supporting receipts.

## Why Claude-First?
Following Anthropic's guidance:
- Use simple, composable workflows over complex agent frameworks.
- Minimize abstractions: orchestration is handled in code, not the model.
- Claude acts as an *augmented LLM*—reasoning through categorization and matching, not controlling the process.

## Key Workflows
- **Email Retrieval**: OAuth-based access to Gmail and Outlook APIs.
- **PDF Parsing**: Extract transaction lines from the statement.
- **Categorization**: Use Claude to map merchant descriptions to accounting codes.
- **Cover Sheet Generation**: Populate an Excel-based template with transaction and summary data.
- **Report Assembly**: Convert Excel to PDF and merge PDFs into final report.

## Technical Requirements
- Local Python environment (Windows)
- APIs:
  - Gmail API
  - Microsoft Graph API (Outlook)
  - Claude API (tool use enabled)
- Libraries: `openpyxl`, `pypdf`, `python-dotenv`, `requests`, `tiktoken`, `pytesseract` (optional OCR)

## Design Principles
- **Workflow-Driven**: Orchestrate process with deterministic code.
- **Claude-Augmented**: Use Claude selectively for categorization and semantic reasoning.
- **Well-Documented Tools**: Tools defined clearly for Claude with descriptions and examples.
- **Human-in-the-Loop Ready**: Logs every reasoning step; optionally prompts for confirmation.
