# CLAUDE.md - Generic AI Assistant Guidelines

## Oracle/Shadow Philosophy

This project follows the Oracle/Shadow philosophy.

Core principles:
1. **Nothing is Deleted** - Append only, timestamps = truth
2. **Patterns Over Intentions** - Observe what happens
3. **External Brain, Not Command** - Mirror reality, don't decide

See `.claude/knowledge/oracle-philosophy.md` for full details.
See `.claude/knowledge/writing-style.md` for voice and style guide.

---

## Executive Summary

This document provides comprehensive guidelines for an AI assistant working on any software development project. It establishes safe, efficient, and well-documented workflows to ensure high-quality contributions.

### Key Responsibilities
-   Code development and implementation
-   Testing and quality assurance
-   Documentation and session retrospectives
-   Following safe and efficient development workflows
-   Maintaining project context and history

### Quick Reference - Short Codes
#### Context & Planning Workflow (Core Pattern)
-   `ccc` - Create context issue and compact the conversation.
-   `nnn` - Smart planning: Auto-runs `ccc` if no recent context → Create a detailed implementation plan.
-   `gogogo` - Execute the most recent plan issue step-by-step.
-   `lll` - List project status (issues, PRs, commits)

#### Project Management
-   `rrr` - Create a detailed session retrospective.


## Quick Start Guide

### Prerequisites
```bash
# Check required tools
node --version
git --version
gh --version      # GitHub CLI
```

### Initial Setup
```bash
# 1. Clone the repository
git clone https://github.com/Soul-Brews-Studio/claude-code-workshops.git
cd claude-code-workshops

# 2. Install dependencies (if any)
pnpm install

# 3. Setup environment variables
cp .env.example .env
# Edit .env with required values
```

### First Task
1.  Run `lll` to see the current project status.
2.  Run `nnn` to analyze the latest issue and create a plan.
3.  Use `gogogo` to implement the plan.

## Project Context

### Project Overview
Workshop materials for teaching Claude Code and Agentic AI at SIIT Thammasat University.

### Architecture
-   **Content**: Markdown slides (Marp format)
-   **Knowledge Base**: Obsidian vault with linked notes
-   **Deployment**: Cloudflare Workers (static assets)
-   **Version Control**: GitHub with PR-based workflow

### Current Features
-   CLAUDE.md Deep Dive slides
-   Short Codes workflow slides
-   Retrospectives (rrr) slides
-   Lessons Learned / Meta Workshop slides
-   Cloudflare Deploy slides

## Critical Safety Rules

### Repository Usage
-   **NEVER create issues/PRs on upstream**

### Command Usage
-   **NEVER use `-f` or `--force` flags with any commands.**
-   Always use safe, non-destructive command options.
-   If a command requires confirmation, handle it appropriately without forcing.

### Git Operations
-   Never use `git push --force` or `git push -f`.
-   Never use `git checkout -f`.
-   Never use `git clean -f`.
-   Always use safe git operations that preserve history.
-   **NEVER MERGE PULL REQUESTS WITHOUT EXPLICIT USER PERMISSION**
-   **Never use `gh pr merge` unless explicitly instructed by the user**
-   **Always wait for user review and approval before any merge**

### File Operations
-   Never use `rm -rf` - use `rm -i` for interactive confirmation.
-   Always confirm before deleting files.
-   Use safe file operations that can be reversed.

## Development Workflows

### GitHub Workflow

#### Creating Issues
When starting a new feature or bug fix:
```bash
# 1. Update main branch
git checkout main && git pull

# 2. Create a detailed issue
gh issue create --title "feat: Descriptive title" --body "..."
```

#### Standard Development Flow
```bash
# 1. Create a branch from the issue
git checkout -b feat/issue-number-description

# 2. Make changes
# ... implement feature ...

# 3. Commit with a descriptive message
git add -A
git commit -m "feat: Brief description

- What: Specific changes made
- Why: Motivation for the changes
- Impact: What this affects

Closes #issue-number"

# 4. Push and create a Pull Request
git push -u origin branch-name
gh pr create --title "Same as commit" --body "Fixes #issue_number"

# 5. CRITICAL: NEVER MERGE PRs YOURSELF
# ONLY provide the PR link to the user
# WAIT for explicit user instruction to merge
```

## Context Management & Short Codes

### Why the Two-Issue Pattern?
The `ccc` → `nnn` workflow uses a two-issue pattern:
1.  **Context Issues** (`ccc`): Preserve session state and context.
2.  **Task Issues** (`nnn`): Contain actual implementation plans.

This separation ensures a clear distinction between context dumps and actionable tasks, leading to better organization and cleaner task tracking. `nnn` intelligently checks for a recent context issue and creates one if it's missing.

### Core Short Codes

#### `ccc` - Create Context & Compact
**Purpose**: Save the current session state and context to forward to another task.

1.  **Gather Information**: `git status --porcelain`, `git log --oneline -5`
2.  **Create GitHub Context Issue**: Use a detailed template to capture the current state, changed files, key discoveries, and next steps.
3.  **Compact Conversation**: `/compact`

#### `nnn` - Next Task Planning (Analysis & Planning Only)
**Purpose**: Create a comprehensive implementation plan based on gathered context. **NO CODING** - only research, analysis, and planning.

1.  **Check for Recent Context**: If none exists, run `ccc` first.
2.  **Gather All Context**: Analyze the most recent context issue or the specified issue (`nnn #123`).
3.  **Deep Analysis**: Read context, analyze the codebase, research patterns, and identify all affected components.
4.  **Create Comprehensive Plan Issue**: Use a detailed template to outline the problem, research, proposed solution, implementation steps, risks, and success criteria.
5.  **Provide Summary**: Briefly summarize the analysis and the issue number created.

#### `lll` - List Project Status
When you see `lll`, execute relevant `gh` and `git` commands in parallel to get a full overview of the project's state, then provide a visual summary of open issues, recent PRs, and current focus.

#### `rrr` - Retrospective
**Purpose**: Document the session's activities, learnings, and outcomes.

**CRITICAL**: The AI Diary and Honest Feedback sections are MANDATORY. These provide essential context and continuous improvement insights. Never skip these sections.

1.  **Gather Session Data**: `git diff --name-only main...HEAD`, `git log --oneline main...HEAD`, and session timestamps.
2.  **Create Retrospective Document**: Use the template to create a markdown file in `retrospectives/` with ALL required sections, especially:
    - **AI Diary**: First-person narrative of the session experience
    - **Honest Feedback**: Frank assessment of what worked and what didn't
3.  **Validate Completeness**: Use the retrospective validation checklist to ensure no sections are skipped.
4.  **Update CLAUDE.md**: Copy any new lessons learned to the main guidelines. **Append to bottom only**
5.  **Link to GitHub**: Commit the retrospective and comment on the relevant issue/PR.

**Time Zone Note**:
-   **PRIMARY TIME ZONE: GMT+7 (Bangkok time)** - Always show GMT+7 time first
-   UTC time included for reference only (shown in parentheses)

#### `gogogo` - Execute Planned Implementation
1.  **Find Implementation Issue**: Locate the most recent `plan:` issue.
2.  **Execute Implementation**: Follow the plan step-by-step, making all necessary code changes.
3.  **Test & Verify**: Run all relevant tests and verify the implementation works.
4.  **Commit & Push**: Commit with a descriptive message, push to the feature branch, and create/update the PR.

## Technical Reference

### Available Tools

#### Version Control
```bash
# Git operations (safe only)
git status
git add -A
git commit -m "message"
git push origin branch

# GitHub CLI
gh issue create
gh pr create
```

#### Search and Analysis
```bash
# Ripgrep (preferred over grep)
rg "pattern" --type md

# Find files
fd "[pattern]"
```

### Deployment
```bash
# Deploy to Cloudflare Workers
npx wrangler deploy
```

## Development Practices

### Code Standards
-   Follow Markdown best practices for slides
-   Use Marp format for presentations
-   Keep slides focused (one concept per slide)

### Git Commit Format
```
[type]: [brief description]

- What: [specific changes]
- Why: [motivation]
- Impact: [affected areas]

Closes #[issue-number]
```
**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

## Lessons Learned

### Planning & Architecture Patterns (2025-12-23)
-   **Pattern**: Use parallel agents for analyzing different aspects of complex systems
-   **Anti-Pattern**: Creating monolithic plans that try to implement everything at once
-   **Pattern**: Ask "what's the minimum viable first step?" before comprehensive implementation
-   **Pattern**: 1-hour implementation chunks are optimal for maintaining focus and seeing progress

### Workshop-Specific Learnings (2025-12-23)
-   **Overview > Detail**: 12-slide overview presentations work better than 27-slide detailed versions
-   **Short Codes Workflow**: `nnn` → `gogogo` → `rrr` provides excellent structure
-   **Archive Pattern**: "archive can be messy" = pragmatic cleanup approach
-   **/trace Command**: 5 parallel agents help find context quickly

### Common Mistakes to Avoid
-   **Creating overly comprehensive initial plans** - Break complex projects into 1-hour phases instead
-   **Trying to implement everything at once** - Start with minimum viable implementation, test, then expand
-   **Skipping AI Diary and Honest Feedback in retrospectives** - These sections provide crucial context and self-reflection

### User Preferences (Observed)
-   **Prefers manageable scope** - Appreciates tasks completable in under 1 hour
-   **Values phased approaches** - Recognizes when plans are "too huge" and appreciates splitting work
-   **Appreciates workflow patterns** - Likes using established patterns like "ccc nnn gh flow"
-   **Time zone preference: GMT+7 (Bangkok/Asia)**

## Troubleshooting

### Common Issues

#### Wrangler Deploy Issues
```bash
# Check wrangler config
cat wrangler.jsonc

# Test locally
npx wrangler dev

# Deploy
npx wrangler deploy
```

#### Slide Preview Issues
```bash
# Preview Marp slides
npx @marp-team/marp-cli slides/path/to/slides.md --preview
```

## Quick Command Reference
```bash
# Development
npx wrangler dev        # Start dev server
npx wrangler deploy     # Deploy to Cloudflare

# GitHub
gh issue create         # Create issue
gh pr create            # Create PR
gh issue list           # List issues
gh pr list              # List PRs

# Git
git status              # Check status
git log --oneline -10   # Recent commits
```

**Last Updated**: 2025-12-23
**Version**: 1.0.0
