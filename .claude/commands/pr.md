---
description: Create a draft Pull Request in English automatically
---

# Create Pull Request

You are tasked with creating a draft Pull Request in English.

## Pre-PR checks

1. **Check current branch**:
   - Run `git branch --show-current`
   - Display current branch name to user

3. **Check if branch is pushed**:
   - Run `git status`
   - If branch is not tracking remote, push it first with `git push -u origin <branch-name>`

4. **Check for existing PR**:
   - Run `gh pr list --head $(git branch --show-current)`
   - If PR already exists: **STOP** and provide the PR URL

## PR creation process

1. **Analyze commits**:
   - Run `git log origin/dev..HEAD --oneline` to see all commits
   - Run `git diff origin/dev...HEAD --stat` to see all changes since branching from dev
   - Understand the full scope of changes

2. **Generate PR content**:

   **Title format**: `type(scope): Brief description`
   - Use conventional commit format
   - Should summarize the entire PR, not just one commit

   **Body structure**:
   ```markdown
   ## Summary
   Brief overview of what this PR does (2-3 sentences max)

   ## Changes Overview

   **Styles:**
   - Styling changes if significant (layout, responsive, theme)

   **Docs:**
   - New or modified docs
   ```

3. **Create PR**:
   - Use `gh pr create --draft --base dev --title "..." --body "..."`
   - Use heredoc for body to preserve formatting:
     ```bash
     gh pr create --draft --base dev --title "feat: title" --body "$(cat <<'EOF'
     ## Summary
     ...

     ## Changes Overview


     **Styles:**
     - ...

     **Docs:**
     - ...

     EOF
     )"
     ```

4. **Confirm**:
   - Display the PR URL
   - Inform user the PR is in draft status
   - Remind them to mark as "Ready for review" when done

## Important notes

- **ALWAYS** create as draft first
- **ALWAYS** use English
- **ALWAYS** target `main` as  branch (unless explicitly told otherwise)
- **ALWAYS** remove the Co-Authored-By footer
- Be descriptive but concise
- NO Testing/Test plan section needed
