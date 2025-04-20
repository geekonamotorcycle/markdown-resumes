# Markdownlint Configuration (PDF-Optimized)

This project uses Markdown for content that will be converted to PDF (e.g., resumes, documentation, reports). To improve flexibility and formatting control, we have customized the default `markdownlint` rules.

This documentation explains the rules that have been disabled or adjusted and the reasons behind each change.

---

## 📄 Active Rule Exceptions

### MD003 – Heading Style

**Disabled**  
Allows mixed heading styles (e.g., `# Heading` and `===` underlines) for flexibility and visual consistency in PDF output.

---

### MD004 – Unordered List Style

**Disabled**  
Accepts all bullet styles (`*`, `-`, `+`). These render identically in PDF and allow for varied aesthetics.

---

### MD007 – List Indentation

**Disabled**  
Permits non-standard indent levels for list items. Useful when fine-tuning layout or indentation for readability in exported documents.

---

### MD012 – Multiple Consecutive Blank Lines

**Disabled**  
Extra blank lines may be used for intentional spacing or visual separation in PDF documents.

---

### MD013 – Line Length

**Customized**  
Increased maximum line length to **120 characters**.  
Ignores line length limits in:

- Code blocks
- Tables

This change improves editing comfort in modern code editors and avoids forcing unnatural line breaks in prose.

```json
"MD013": {
  "line_length": 120,
  "ignore_code_blocks": true,
  "ignore_tables": true
}
```
