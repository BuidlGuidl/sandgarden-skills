---
name: pr-create
description: Create a GitHub PR with the changes you made.
---

**Trigger this skill when the user asks to create/open a PR or "ship it"**

If no other instructions are provided, create a PR from the current branch to the repository’s default branch.

## Before creating the PR:

- Verify the current branch is NOT the default branch
- Verify there are commits ahead of the default branch. If there are uncommitted changes, suggest committing them first
- Run `git diff <default-branch>...HEAD` and `git log <default-branch>..HEAD` to understand ALL changes on the branch, not just the latest commit.
- If the PR is already created, just push the changes to the branch

## Format of the PR

- title: concise description of the main change
- body:
  1. Summary: A really concise description of the changes
  2. How to test: Instructions on how reviewers can test the changes
  3. (optional) Tricky things to look out for when reviewing (database changes, auth, security, important copy, etc)
  4. (optional) A collapsible section with a detailed description of the changes

## Tool

Use the `gh` CLI to create the PR or interact with the GitHub repo. If the user doesn't have it, suggest installing it.
