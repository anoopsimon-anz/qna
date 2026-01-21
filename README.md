# TMS Feature Q&A Documentation

Interactive documentation hub for TMS Suncorp features in question-answer format.

## Project Structure

```
qna/
├── index.html                    # Landing page with feature tiles
├── customer-profile.html         # Customer Profile Creation Q&A
├── account-number-allocation.html (coming soon)
├── migration-indicator.html      (coming soon)
└── README.md                     # This file
```

## How to Use

1. Open `index.html` in your browser
2. Click on any feature tile to access its Q&A page
3. Use search bars to filter content
4. Click questions to expand/collapse answers

## Adding a New Feature Page

### Step 1: Create the HTML file

Copy `customer-profile.html` as a template:

```bash
cp customer-profile.html your-feature.html
```

### Step 2: Update the features array

Edit your new HTML file's JavaScript `features` array:

```javascript
const features = [
    {
        title: "Your Feature Name",
        overview: {
            title: "Overview - From a Tester's Perspective",
            content: [
                "First paragraph about the feature",
                "Second paragraph with key points",
                "Testing focus areas"
            ]
        },
        qna: [
            {
                question: "What is this feature?",
                answer: "Your detailed answer with HTML formatting..."
            }
        ]
    }
];
```

### Step 3: Add to index page

Edit `index.html` and add to the `features` array:

```javascript
{
    title: "Your Feature Name",
    description: "Brief description for the tile",
    icon: "🎯", // Pick an emoji
    link: "your-feature.html",
    questionCount: 15, // Update after adding questions
    tags: ["Tag1", "Tag2"],
    status: "available" // or "coming-soon"
}
```

## Answer Formatting Tips

### Inline code
```html
<code>CustomerGroupID</code>
```

### Code blocks
```html
<pre>
SELECT * FROM Payloads
WHERE InterfaceName = 'OCVOnboarding'
</pre>
```

### Lists
```html
<ul>
  <li>First item</li>
  <li>Second item</li>
</ul>
```

### Formatting
- `<strong>` for bold
- `<br>` for line breaks
- `&nbsp;` for spacing
- `<code>` for inline code

## Current Features

### Available
- ✅ **Customer Profile Creation** (18 questions)
  - Phase workflow execution
  - Scheduler behavior
  - Event tracking
  - Testing patterns

### Coming Soon
- ⏳ Account Number Allocation
- ⏳ Migration Indicator
- ⏳ File Ingestion
- ⏳ Scheduler Patterns
- ⏳ Testing Best Practices

## Quick Start

```bash
# Open the documentation hub
open index.html

# Or directly open a feature
open customer-profile.html
```
