# Issue Templates

This directory contains markdown files that are automatically converted into GitHub issues when a new repository is created from this template.

## How It Works

1. When a repository is created from this template, the GitHub Actions workflow reads all `.md` files in this directory
2. Each file's front matter (YAML between `---` markers) defines the issue metadata
3. The content after the front matter becomes the issue body
4. Issues are created in alphabetical order by filename

## File Format

Each issue template file should follow this format:

```markdown
---
title: "Issue Title"
labels: 
  - label1
  - label2
assignees: 
  - username1
  - username2
milestone: 1  # optional
---

Issue body content goes here in Markdown format.
```

## Adding New Issues

1. Create a new `.md` file in this directory
2. Prefix with a number to control order (e.g., `05-new-issue.md`)
3. Add front matter with at least a `title`
4. Write the issue body in Markdown

## Customizing Issues

- **Labels**: Must exist in the repository or they won't be applied
- **Assignees**: Use GitHub usernames; must have repository access
- **Milestone**: Must exist in the repository as a number
- **Body**: Supports full GitHub Flavored Markdown including task lists, code blocks, and tables

## Testing

To test issue creation without creating a new repository:
1. Temporarily modify the workflow trigger
2. Run the workflow manually
3. Check created issues
4. Delete test issues and revert workflow