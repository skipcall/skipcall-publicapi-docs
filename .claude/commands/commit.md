# Incremental Commit (Frontend)

You are tasked with creating an incremental commit in English for frontend changes.

## Pre-commit checks

1. **Check current branch**:
   - Run `git branch --show-current`
   - Display current branch name to user

2. **Check git status**:
   - Run `git status`
   - If no changes: inform user and stop
   - Show summary of changes to user

## Commit process

1. **Stage changes**:
   - Run `git add -A` to stage all changes

2. **Analyze changes**:
   - Review the staged changes with `git diff --cached --stat`
   - Understand what was modified, added, or deleted
   - Identify the type of change (feat, fix, refactor, docs, style, test, chore)
   - Identify the scope (component name, feature area, or general area like "ui", "styles", "types")

3. **Generate commit message**:
   - Follow conventional commits format: `type(scope): description`
   - Write in English
   - Be concise but descriptive
   - Type can be:
     - `style`: CSS/styling changes or code formatting
     - `docs`: Documentation only
     - `chore`: Build process, dependencies, or tooling
   - Include a body with bullet points

4. **Create commit**:
   - Use heredoc format for proper formatting
   - Example:
     ```bash
     git commit -m "$(cat <<'EOF'
     feat(dialer): add visual feedback for call status

     - Added loading spinner during call initiation
     - Improved button states (idle, loading, error)
     - Updated TypeScript interfaces for new props

     Co-Authored-By: Claude <noreply@anthropic.com>
     EOF
     )"
     ```

5. **Confirm**:
   - Show the commit hash
   - Show the commit message
   - Ask user if they want to push

## Important notes

- **ALWAYS** use English for commit messages
- **ALWAYS** follow conventional commits
- **ALWAYS** remove the Co-Authored-By footer
- Keep commits atomic and focused on a single concern
