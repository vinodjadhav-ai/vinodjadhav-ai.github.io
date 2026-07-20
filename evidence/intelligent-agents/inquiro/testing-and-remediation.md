# Testing and Remediation

## Testing Approach

I used both unit tests and functional tests.

The pytest suite covered:

- Planner search-query extraction
- Processor output-folder creation
- Retriever fallback queries
- Main workflow availability
- Writer Jinja2 report generation

The final pytest run completed successfully:

```text
5 passed in 0.16s