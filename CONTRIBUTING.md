# Contributing to TurboCASH FAQ

Thank you for your interest in contributing to the TurboCASH FAQ! This document provides guidelines for adding new FAQs or improving existing ones.

## How to Contribute

### 1. Fork and Clone the Repository

```bash
git clone https://github.com/philipdc/turbocashFAQ.git
cd turbocashFAQ
```

### 2. Create a New Branch

```bash
git checkout -b add-faq-[topic-name]
# Example: git checkout -b add-faq-multi-currency
```

### 3. Add or Edit FAQ Pages

#### Creating a New FAQ

1. Create a new HTML file in the `faqs/` directory
2. Use the provided template below
3. Follow the naming convention: `topic-name.html` (lowercase, hyphen-separated)

#### FAQ Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Brief description of the FAQ topic">
    <title>Your FAQ Title - TurboCASH FAQ</title>
    <link rel="stylesheet" href="../assets/css/style.css">
    
    <!-- Schema.org structured data -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "FAQPage",
        "mainEntity": {
            "@type": "Question",
            "name": "Your main question?",
            "acceptedAnswer": {
                "@type": "Answer",
                "text": "Brief answer summary"
            }
        },
        "datePublished": "YYYY-MM-DD",
        "dateModified": "YYYY-MM-DD"
    }
    </script>
</head>
<body>
    <header>
        <nav>
            <h1>TurboCASH FAQ</h1>
            <div class="breadcrumb">
                <a href="../index.html">Home</a>
                <span>›</span>
                <span>Your Topic</span>
            </div>
        </nav>
    </header>

    <main>
        <article class="faq-item">
            <h2 class="faq-question">Your Main Question?</h2>
            
            <div class="metadata">
                Last updated: Month Day, Year | Category: Category Name
            </div>

            <div class="faq-answer">
                <!-- Your content here -->
                <h3>Section Title</h3>
                <p>Your content...</p>

                <!-- Use these styled boxes for different types of information -->
                <div class="solution-box">
                    <strong>Solutions:</strong>
                    <p>Solution content...</p>
                </div>

                <div class="warning-box">
                    <strong>Warning:</strong>
                    <p>Warning content...</p>
                </div>

                <div class="error-box">
                    <strong>Error:</strong>
                    <p>Error description...</p>
                </div>

                <div class="info-box">
                    <strong>Info:</strong>
                    <p>Information content...</p>
                </div>

                <!-- Tags -->
                <div class="tags">
                    <span class="tag">Tag1</span>
                    <span class="tag">Tag2</span>
                </div>
            </div>
        </article>

        <section class="related-faqs">
            <h3>Related FAQs</h3>
            <ul>
                <li><a href="related-faq-1.html">Related FAQ 1</a></li>
                <li><a href="related-faq-2.html">Related FAQ 2</a></li>
            </ul>
        </section>
    </main>

    <footer class="no-print">
        <p>
            <a href="../index.html">← Back to FAQ Index</a> | 
            <a href="https://github.com/philipdc/turbocashFAQ">Contribute on GitHub</a>
        </p>
    </footer>
</body>
</html>
```

### 4. Update the Index Page

Add your new FAQ to the appropriate category in `index.html`:

```html
<article class="category">
    <h3>Your Category</h3>
    <ul>
        <!-- Add your new FAQ here -->
        <li><a href="faqs/your-new-faq.html">Your FAQ Title</a></li>
    </ul>
</article>
```

### 5. Writing Guidelines

#### Content Guidelines

- **Be Clear and Concise**: Use simple language that both technical and non-technical users can understand
- **Be Specific**: Include version numbers, error codes, and specific steps when applicable
- **Be Accurate**: Test solutions before documenting them
- **Be Complete**: Include prerequisites, steps, and verification procedures
- **Use Examples**: Provide code snippets, command examples, or screenshots when helpful

#### Structure Guidelines

- **Start with Overview**: Brief explanation of the problem
- **List Symptoms**: Help users identify if this FAQ applies to them
- **Explain Causes**: What typically causes this issue?
- **Provide Solutions**: Step-by-step instructions, ordered from most common to advanced
- **Include Prevention**: How to avoid the issue in the future
- **Add Related FAQs**: Link to relevant topics

#### Formatting Guidelines

- Use semantic HTML5 elements (`<article>`, `<section>`, `<header>`, etc.)
- Use appropriate heading hierarchy (h2 for main question, h3 for sections, h4 for subsections)
- Use styled boxes for different content types:
  - `solution-box` for solutions and fixes
  - `warning-box` for warnings and cautions
  - `error-box` for error messages
  - `info-box` for additional information
- Include code snippets in `<pre><code>` blocks
- Use `<strong>` for emphasis, not `<b>`
- Use ordered lists `<ol>` for sequential steps
- Use unordered lists `<ul>` for non-sequential items

#### Semantic Markup

All FAQs must include Schema.org structured data for:
- Better SEO and discoverability
- LLM optimization (easier for AI assistants to parse)
- Rich snippets in search results

**Example Schema.org markup:**

```html
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": {
        "@type": "Question",
        "name": "How do I backup my TurboCASH database?",
        "acceptedAnswer": {
            "@type": "Answer",
            "text": "You can backup your TurboCASH database using the built-in backup tool or manual database export methods."
        }
    },
    "datePublished": "2025-11-17",
    "dateModified": "2025-11-17"
}
</script>
```

### 6. Testing Your Changes

Before submitting:

1. **Validate HTML**: Use [W3C Validator](https://validator.w3.org/)
2. **Test Links**: Ensure all internal and external links work
3. **Check Responsiveness**: Test on different screen sizes
4. **Verify Semantic Markup**: Use [Schema.org Validator](https://validator.schema.org/)
5. **Test in Different Browsers**: Chrome, Firefox, Edge, Safari
6. **Test on GitHub**: Preview markdown files in GitHub interface

#### Local Testing

Open the HTML files directly in your browser:

```bash
# On Windows
start index.html

# On Linux
xdg-open index.html

# On macOS
open index.html
```

### 7. Commit Your Changes

Use clear, descriptive commit messages:

```bash
git add .
git commit -m "Add FAQ: How to configure multi-currency support"

# For updates to existing FAQs:
git commit -m "Update: Database connection errors FAQ - Add PostgreSQL troubleshooting"
```

### 8. Push and Create Pull Request

```bash
git push origin add-faq-[topic-name]
```

Then:
1. Go to the repository on GitHub
2. Click "New Pull Request"
3. Select your branch
4. Fill in the PR template:
   - **Title**: Brief description of what you're adding/changing
   - **Description**: 
     - What FAQ(s) you added or modified
     - Why this change is needed
     - Any relevant issue numbers
   - **Testing**: How you tested your changes

### 9. Pull Request Review Process

Your PR will be reviewed for:
- **Accuracy**: Is the information correct?
- **Clarity**: Is it easy to understand?
- **Completeness**: Does it cover the topic thoroughly?
- **Formatting**: Does it follow the style guidelines?
- **Links**: Do all links work correctly?
- **Schema**: Is semantic markup properly implemented?

Reviewers may request changes. Please address feedback promptly and update your PR.

## FAQ Categories

Organize your FAQs into these categories:

- **Installation & Setup**: Initial installation, configuration, first-time setup
- **Common Problems**: Frequent issues users encounter
- **Features & Usage**: How to use specific features
- **Performance & Troubleshooting**: Performance issues, advanced troubleshooting

If you think a new category is needed, propose it in your PR description.

## Style Guide

### Code Examples

Use proper syntax highlighting and formatting:

```sql
-- SQL examples should be properly formatted
SELECT * FROM invoices 
WHERE date >= '2025-01-01' 
ORDER BY invoice_number;
```

```bash
# Shell commands should show the prompt or comment
sudo systemctl restart mysql
```

### Screenshots and Images

- Place images in `assets/images/`
- Use descriptive filenames: `database-connection-settings.png`
- Optimize images (compress, resize to appropriate dimensions)
- Always provide alt text for accessibility
- Reference images using relative paths: `../assets/images/filename.png`

### Links

- Use relative links for internal pages: `<a href="database-setup.html">Database Setup</a>`
- Use full URLs for external links
- Ensure external links open in the same tab (don't use `target="_blank"` unless necessary)

## Questions or Need Help?

- Open an issue on GitHub
- Review existing FAQs for examples
- Check this CONTRIBUTING guide for answers

## Code of Conduct

- Be respectful and constructive
- Focus on the content, not the contributor
- Assume good faith
- Help newcomers learn

## License

By contributing to this project, you agree that your contributions will be licensed under the GNU General Public License v3.0.

---

Thank you for helping make TurboCASH documentation better for everyone! 🎉
