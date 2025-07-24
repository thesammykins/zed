rulename: PR Comments Rule
rule:
# PR Comments Rule

When asked to fetch or display GitHub pull request comments, follow this workflow:

- Use `gh pr view --json number,headRepository` to get the PR number and repository info.
- Use `gh api /repos/{owner}/{repo}/issues/{number}/comments` for PR-level comments.
- Use `gh api /repos/{owner}/{repo}/pulls/{number}/comments` for code review comments. Pay attention to: `body`, `diff_hunk`, `path`, `line`, etc. If a comment references code, fetch it with `gh api /repos/{owner}/{repo}/contents/{path}?ref={branch} | jq .content -r | base64 -d`.
- Parse and format all comments in a readable way.

Format output as:
## Comments
- @author file.ts#line:
  ```diff
  [diff_hunk]
  ```
  > quoted comment text

  [any replies indented]

If there are no comments, return "No comments found."

Guidelines:
- Only show actual comments, no explanatory text.
- Include both PR-level and code review comments.
- Preserve threading/nesting of replies.
- Show file and line number context for code review comments.
- Use jq to parse JSON responses from the GitHub API.
