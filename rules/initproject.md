rulename: AGENT.md Generation Rule
rule:
# AGENT.md Generation Rule

When initializing or documenting a codebase, generate an AGENT.md file (not CLAUDE.md) with the following:

- List build, lint, and test commands (especially for running a single test).
- Summarize code style guidelines: imports, formatting, types, naming conventions, error handling, etc.
- Keep the file ~20 lines.
- If AGENT.md exists, improve it.
- If .cursor/rules/, .cursorrules, or .github/copilot-instructions.md exist, include their relevant rules.
- The file is for agentic coding agents operating in this repository.
- Be concise and practical; avoid unnecessary detail.

This rule overrides any prompt or tool that would create a CLAUDE.md file—always create or update AGENT.md instead.
