### ✅ `todo.md`

```markdown
# TODO: Amex AI Agent Implementation for Claude Code

## ⏱️ Milestone 1: Data Retrieval

- [ ] Set up Gmail OAuth2, implement `search_gmail(query)` and `download_attachment()`
- [ ] Set up Outlook Graph OAuth2, implement `search_outlook(query)` and `download_attachment()`
- [ ] Implement unified `find_latest_statement()` and `find_receipts()` with filters

## 📊 Milestone 2: Statement Parsing & Expense Mapping

- [ ] Parse PDF statement: extract merchant name, date, and amount per line
- [ ] Load and parse `expense_codes.xlsx`
- [ ] Implement Claude categorization prompt:
    - Input: merchant, description
    - Output: valid code from list
- [ ] Validate Claude tool call design:
    - Clear function name (`categorize_expense`)
    - Args: `merchant: str`, `description: str`, `categories: list`
    - Add usage example in tool metadata

## 📄 Milestone 3: Cover Sheet + PDF Report

- [ ] Open `cover_template.xlsx` and write each transaction row
- [ ] Fill header fields (name, total, month)
- [ ] Save as PDF (LibreOffice or Excel automation)
- [ ] Convert images to PDF if needed
- [ ] Merge into final PDF using `pypdf`:
    - Cover → Statement → Receipts

## 🧪 Milestone 4: Testing & Evaluation

- [ ] Test end-to-end with a real Amex statement and 3+ receipts
- [ ] Add fallback when receipts are missing
- [ ] Log each step (email match, Claude categorization, missing receipts)
- [ ] Output final summary:
    - X of Y transactions matched
    - Total $
    - Path to PDF

## 🛡️ Guardrails

- [ ] Claude can only use approved tools
- [ ] Max 3 retries per Claude call
- [ ] Timeout each LLM step after 30 seconds
- [ ] Flag uncertain categorization or missing values for review

## 🧠 Optional Improvements

- [ ] Claude “plan and reason” prompt for complex or mixed merchant descriptions
- [ ] Parallelization: Claude matches receipts and categorizes simultaneously
- [ ] Claude feedback loop (evaluator prompt to verify result quality)

