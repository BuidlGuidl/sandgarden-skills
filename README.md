# Sandgarden Skills

A collection of agent skills for Claude Code and other AI coding assistants, following the [skills.sh](https://github.com/vercel-labs/skills) convention.

## Installation

Install skills using the skills CLI:

```bash
# Install all skills from this repository
npx skills add technophile-04/sandgarden-skills

# Install a specific skill
npx skills add technophile-04/sandgarden-skills -s code-reviewer
```

## Available Skills

### code-reviewer

Review TypeScript, React, and Next.js code against high standards for clarity, simplicity, and maintainability. Provides brutally honest but supportive feedback following best practices.

**Use when:**
- Code has just been written or modified
- You want explicit code review
- Refactoring has been completed
- New features or components have been implemented
