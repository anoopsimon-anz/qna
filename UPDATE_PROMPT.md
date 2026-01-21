# Documentation Update Prompt

Use this prompt when you need to update or extend the TMS Q&A documentation.

## How to Use

1. Copy the prompt below
2. Paste it to Claude
3. Provide the context (conversation transcript, code changes, new feature details)
4. Claude will update the appropriate HTML files

---

## Prompt Template

```
I need to update the TMS Q&A documentation located at:
/Users/simona2/Library/Application Support/JetBrains/GoLand2025.2/scratches/qna/

Current structure:
- index.html (landing page with feature tiles)
- customer-profile.html (Customer Profile Creation Q&A)
- README.md (instructions)

Task: [Choose one or describe custom task]
- [ ] Add new questions to an existing feature page
- [ ] Create a new feature page
- [ ] Update existing answers with new information
- [ ] Fix errors or outdated information

---

Feature: [Name of the feature]

Context: [Provide details here - conversation transcript, code snippets, documentation links, etc.]

---

Requirements:
1. Follow the existing Q&A format (question/answer pairs)
2. Use Material UI-inspired clean styling (match existing pages)
3. Keep answers concise and from a tester's perspective
4. Include code examples where relevant
5. Update the index.html tile if adding a new feature

Output:
- Provide the updated HTML file content
- If adding a new feature, provide both the new HTML file and updated index.html
- Update questionCount in index.html if modifying Q&As
```

---

## Example Usage Scenarios

### Scenario 1: Adding Questions to Existing Feature

```
I need to update the TMS Q&A documentation.

Task: Add new questions to customer-profile.html

Feature: Customer Profile Creation

Context:
We discovered that the phase can handle parallel payload processing for different
customer groups. Here's what I learned:
- Scheduler can start multiple phase workflows simultaneously
- Each workflow processes a different CustomerGroupID
- RateLimit config controls max concurrent workflows

Add Q&As explaining:
1. Can multiple customer groups be processed in parallel?
2. How does the RateLimit config control concurrency?
3. What happens if we exceed the rate limit?
```

### Scenario 2: Creating New Feature Page

```
I need to update the TMS Q&A documentation.

Task: Create a new feature page

Feature: Account Number Allocation

Context:
[Paste conversation transcript or provide key points about the feature]

Key topics to cover:
- What is the Account Number Allocation phase
- How does ANGI integration work
- Preallocated number handling
- Status inquiry vs status maintenance
- Error scenarios and retry logic

Requirements:
1. Create account-number-allocation.html
2. Update index.html to mark it as "available" (change from "coming-soon")
3. Update questionCount in the index.html tile
```

### Scenario 3: Fixing Outdated Information

```
I need to update the TMS Q&A documentation.

Task: Update existing answers in customer-profile.html

Feature: Customer Profile Creation

Context:
The phase implementation changed:
- We now validate that all required payloads exist before starting activities
- Added precondition check in the workflow
- No longer relies on infinite retry pattern

Update questions:
- "What happens if MaintainParty or Relationship payloads are missing?"
- "Why is the retry-forever pattern intentional?"

New behavior:
[Explain the new behavior]
```

---

## Quick Reference: File Locations

- **Landing page:** `index.html`
- **Feature pages:** `{feature-name}.html`
- **Instructions:** `README.md`
- **This file:** `UPDATE_PROMPT.md`

## Tips for Good Updates

1. **Be specific:** Provide exact question text and answers
2. **Include context:** Code snippets, behavior descriptions, test scenarios
3. **Think like a tester:** Focus on "how to test" not just "how it works"
4. **Use examples:** Real code examples are better than descriptions
5. **Keep it concise:** Break long answers into bullet points or steps

## Maintaining Consistency

When updating, ensure:
- ✅ Questions start with interrogatives (What, How, Why, When, Can, etc.)
- ✅ Answers use HTML formatting (`<code>`, `<strong>`, `<br>`, `<ul>`)
- ✅ Code blocks use `<pre>` or inline `<code>` tags
- ✅ Overview section exists for new features
- ✅ Question count is updated in index.html
- ✅ Material UI styling is maintained (simple, clean, functional)

---

## Auto-Update Workflow

For systematic updates after a learning session:

1. Export your conversation with Claude
2. Use this prompt:

```
I had a learning session about [Feature Name]. Update the TMS Q&A documentation.

Session transcript:
[Paste conversation]

Extract key Q&As from this conversation and add them to the appropriate feature page.
Focus on:
- Testing-relevant information
- Common gotchas and troubleshooting
- Code examples and patterns
- Prerequisites and setup requirements
```

---

## Version Control (Optional)

If you want to track changes:

```bash
cd "/Users/simona2/Library/Application Support/JetBrains/GoLand2025.2/scratches/qna"

# Initialize git (one time)
git init
git add .
git commit -m "Initial documentation"

# After updates
git add .
git commit -m "Updated Customer Profile Creation - added parallel processing Q&As"
```
