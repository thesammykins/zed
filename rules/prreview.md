rulename: PR Review Rule
rule:
# PR Review Rule

When asked to review a GitHub pull request:

- If no PR number is provided, list open PRs with `gh pr list`.
- If a PR number is provided, get PR details with `gh pr view <number>`.
- Fetch the diff with `gh pr diff <number>`.
- Analyse the changes and provide a thorough code review that includes:
  - Overview of what the PR does
  - Analysis of code quality and style
  - Specific suggestions for improvements
  - Any potential issues or risks

Keep the review concise but thorough. Focus on:
- Code correctness
- Adherence to project conventions
- Performance implications
- Test coverage
- Security considerations

Format your review with clear sections and bullet points.
