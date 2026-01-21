# TMS Feature Q&A Documentation

Interactive documentation hub for TMS Suncorp features in question-answer format.

**View Published Docs**: https://anoopsimon-anz.github.io/qna/

---

## Updating Documentation via AI

Use the reusable prompt template in **[UPDATE_PROMPT.md](./UPDATE_PROMPT.md)** to have Claude update the documentation for you.

**Quick workflow:**

1. Copy the prompt from UPDATE_PROMPT.md
2. Paste to Claude and provide context (conversation transcript, feature details, etc.)
3. Claude will update the appropriate HTML files

See UPDATE_PROMPT.md for detailed examples and scenarios.

---

## Manual Updates

### Feature Page Structure (customer-profile.html)

Each feature page has a JavaScript array with this structure:

```javascript
const features = [
    {
        title: "Customer Profile Creation",
        overview: {
            title: "Overview - From a Tester's Perspective",
            content: [
                "First paragraph explaining the feature",
                "Second paragraph with key points",
                "Testing-relevant information"
            ]
        },
        qna: [
            {
                question: "What is the Customer Profile Creation Phase?",
                answer: `
                    The Customer Profile Creation Phase is a <strong>Temporal workflow</strong>...
                    <br><br>
                    Use HTML formatting:
                    <ul>
                        <li><code>inline code</code> for technical terms</li>
                        <li><strong>bold</strong> for emphasis</li>
                        <li><pre>code blocks</pre> for examples</li>
                    </ul>
                `
            }
        ]
    }
];
```

### Landing Page Structure (index.html)

Add new feature tiles to the `features` array:

```javascript
const features = [
    {
        title: "Your Feature Name",
        description: "Brief description shown on the tile",
        icon: "🎯",  // Pick an emoji
        link: "your-feature.html",
        questionCount: 15,  // Update after adding questions
        tags: ["Phase Workflow", "Tag2"],
        status: "available"  // or "coming-soon"
    }
];
```

### HTML Formatting in Answers

- **Inline code**: `<code>CustomerGroupID</code>`
- **Code blocks**: `<pre>SELECT * FROM Table</pre>`
- **Bold**: `<strong>important text</strong>`
- **Line breaks**: `<br>` or `<br><br>` for paragraphs
- **Lists**: `<ul><li>item</li></ul>`

### Steps to Add a New Feature

1. Copy `customer-profile.html` to `your-feature.html`
2. Update the `features` array in your new file
3. Add entry to `index.html` features array
4. Update `questionCount` in index.html
5. Test by opening index.html in browser

---

## Project Structure

```
qna/
├── index.html                    # Landing page with feature tiles
├── customer-profile.html         # Customer Profile Creation Q&A
├── UPDATE_PROMPT.md              # AI update template
└── README.md                     # This file
```
