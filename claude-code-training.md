# Claude Code Internal Training Session
## 2-Hour Workshop for Kissflow Teams

---

# Overview

| Part | Duration |
|------|----------|
| Project Showcase | 15-20 min |
| Must Know | 50 min |
| Intermediate | 32 min |
| Advanced | 5-10 min |
| Q&A | 5-10 min |
| **Total** | **~2 hours** |

---

# Part 1: Project Showcase (15-20 min)

*Your 3 demos to hook the audience*

| Demo | Project | Highlight | Time |
|------|---------|-----------|------|
| 1 | ? | ? | ~5-7 min |
| 2 | ? | ? | ~5-7 min |
| 3 | ? | ? | ~5 min |

**Tips for Maximum Impact:**
- Show before/after: time saved, code quality improvements
- Highlight a "wow moment" — something that would've taken hours done in minutes
- If possible, do one quick live interaction so they see it's not scripted
- End with a teaser: "Now let me show you how to do this yourselves"

---

# Part 2: Must Know (50 min)

*Full coverage + live demos — essentials everyone should leave knowing*

| Topic | Duration | Demo |
|-------|----------|------|
| Starting & Basic Interaction | 7 min | ✅ |
| Making Code Changes | 8 min | ✅ |
| Essential Commands | 8 min | ✅ |
| Interaction Modes | 5 min | ✅ |
| Thinking Modes | 5 min | ✅ |
| Model Selection | 3 min | ✅ |
| Cost Awareness | 2 min | — |
| Git Workflows | 3 min | ✅ |
| todo.md | 4 min | ✅ |
| CLAUDE.md + Imports | 5 min | ✅ |

---

## 2.1 Starting & Basic Interaction (7 min)

### Concept to Explain
- Claude Code runs in your terminal, scoped to your project directory
- It automatically reads and understands your codebase
- No need to manually add files to context — Claude pulls what it needs

### Getting Started
```bash
cd your-project
claude
```

### First Things to Try

| Task | Example Prompt |
|------|----------------|
| Understand project | "What does this project do?" |
| Explore structure | "Explain the folder structure" |
| Find functionality | "Where is the authentication logic?" |
| Understand a file | "Explain what /src/utils/api.js does" |
| Ask about patterns | "What state management approach does this project use?" |

### How Context Works
- Claude reads files on-demand as needed
- It sees file names, directory structure, and content when relevant
- Large codebases work fine — Claude doesn't load everything at once

### ⚡ Live Demo (3-4 min)
1. Navigate to a project: `cd my-project`
2. Start Claude: `claude`
3. Ask: "What does this project do?"
4. Watch Claude analyze files and summarize
5. Follow up: "Where would I add a new API endpoint?"
6. Show how Claude navigates to relevant files

### Key Takeaway
> "Just ask questions in plain English — Claude figures out which files to read."

---

## 2.2 Making Code Changes (8 min)

### Concept to Explain
- Claude always asks for permission before modifying files
- You can approve individual changes or enable "Accept all" mode for a session
- You see a diff before anything changes
- You stay in control at every step

### The Change Flow
```
You ask for a change
       ↓
Claude proposes edits (shows diff)
       ↓
You review the diff
       ↓
Accept (y) / Reject (n) / Edit
       ↓
File is modified
```

### Approval Options

| Input | Action |
|-------|--------|
| `y` | Accept this change |
| `n` | Reject this change |
| `e` | Edit the proposed change |
| `a` | Accept all remaining changes in this task |

### Example Prompts for Changes

| Task | Prompt |
|------|--------|
| Bug fix | "Fix the null pointer error in UserService.getById" |
| Add feature | "Add a logout button to the navbar" |
| Refactor | "Extract the validation logic into a separate function" |
| Update code | "Change the API timeout from 5s to 10s" |

### ⚡ Live Demo (4-5 min)
1. Ask: "Add input validation to the login form — email should be valid format, password minimum 8 characters"
2. Claude proposes changes — walk through the diff
3. Explain each part of the diff view
4. Accept the change
5. Show the modified file
6. Optionally reject a change to show that flow

### Key Takeaway
> "You always see what's changing before it happens. Nothing is modified without your approval."

---

## 2.3 Essential Commands (8 min)

### Concept to Explain
- Slash commands control Claude Code behavior
- These are your core toolkit for daily use

### Must-Know Commands

| Command | What It Does | When to Use |
|---------|--------------|-------------|
| `/help` | Shows all available commands | When you forget something |
| `/clear` | Clears conversation context | Starting fresh, context got messy |
| `/model` | Switch between models (Sonnet/Opus) | Opus for complex, Sonnet for speed |
| `/compact` | Summarizes conversation to save tokens | Long sessions, running low on context |
| `/rewind` | Roll back to a previous checkpoint | Undo changes, try different approach |
| `/status` | Shows current session info | Check model, token usage |
| `/bug` | Report an issue to Anthropic | When something breaks |

### Checkpoint & Rewind
- The checkpoint system automatically saves your code state before each change
- You can instantly rewind to previous versions by tapping `Esc` twice or using `/rewind`
- When you rewind, you can choose to restore the code, the conversation, or both

### Rewind Options

| Rewind Type | What Gets Restored |
|-------------|-------------------|
| Code only | Files go back, conversation continues |
| Conversation only | Context resets, files stay changed |
| Both | Full rollback to that point |

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Esc Esc` (double tap) | Quick rewind |
| `Shift+Tab` | Cycle interaction modes |
| `Ctrl+C` | Cancel current operation |
| `Ctrl+R` | Search prompt history |

### ⚡ Live Demo (4-5 min)
1. Show `/help` — browse available commands
2. Show `/model` — switch to Opus, explain when to use each
3. Make a code change
4. Use `Esc Esc` to rewind
5. Show the checkpoint selection
6. Restore code to previous state
7. Show `/compact` — explain token savings

### Key Takeaway
> "Learn these commands — they'll save you time every single day."

---

## 2.4 Interaction Modes (5 min)

### Concept to Explain
- **Default Mode:** Tell Claude to do something, it suggests a change, waits for your permission, then executes.
- **Auto-accept mode:** The true vibe coder mode — Claude works on your code and edits files without waiting for permission.

### Mode Comparison

| Mode | Flow | Best For |
|------|------|----------|
| Default | Ask → Review → Approve → Apply | Learning, critical code, unfamiliar repos |
| Auto-accept | Ask → Claude does everything | Prototyping, boilerplate, trusted tasks |

### How to Switch
- `Shift+Tab` — cycle through modes
- `/auto-accept` — toggle auto-accept on/off

### Safety with Auto-accept
- Checkpoints still save before each change
- You can always `/rewind` if something goes wrong
- Git is your safety net — commit before big auto-accept sessions

### ⚡ Live Demo (2-3 min)
1. Start in default mode — make a change, show approval flow
2. Press `Shift+Tab` to switch to auto-accept
3. Ask: "Add error handling to all the API calls in this file"
4. Watch Claude work without stopping
5. Show the speed difference
6. Review changes with `git diff`

### Key Takeaway
> "Default mode for control, auto-accept for speed. Use checkpoints as your safety net."

---

## 2.5 Thinking Modes (5 min)

### Concept to Explain
- Claude can think step-by-step before responding
- Extended thinking = better results for complex problems
- Trade-off: more time and tokens for deeper reasoning

### Two Modes

| Mode | Behavior | Best For |
|------|----------|----------|
| Normal | Direct response | Simple tasks, quick fixes |
| Extended Thinking | Reasons through problem first | Complex bugs, architecture, tricky logic |

### How to Trigger Thinking

| Method | Example |
|--------|---------|
| Prompt words | "Think carefully about...", "Think step by step..." |
| Command | `/think` to toggle thinking mode |
| Model choice | Opus thinks more deeply by default |
| Levels | "think" < "think hard" < "think harder" < "ultrathink" |

### When to Use Extended Thinking

| ✅ Use Thinking | ❌ Skip Thinking |
|-----------------|------------------|
| Debugging race conditions | Adding a button |
| Architecture decisions | Simple refactors |
| Security analysis | Renaming variables |
| Complex algorithm design | Boilerplate code |

### Example Prompts

| Task | Prompt |
|------|--------|
| Bug investigation | "Think carefully about why the checkout sometimes creates duplicate orders" |
| Design decision | "Think through the pros and cons of using Redux vs Context for our state management" |
| Security review | "Think step by step about potential security vulnerabilities in our auth flow" |

### ⚡ Live Demo (2-3 min)
1. Ask a simple question: "What does the handleSubmit function do?" — instant response
2. Ask a complex question: "Think carefully about potential race conditions in our payment processing flow"
3. Show Claude's thinking process (if visible) or the more thorough response
4. Highlight the difference in depth

### Key Takeaway
> "Simple tasks — be fast. Complex problems — ask Claude to think."

---

## 2.6 Model Selection (3 min)

### Concept to Explain
- Claude Code supports multiple models — choose based on task complexity
- Switch anytime with `/model` command

### Model Comparison

| Model | Best For | Speed | Cost |
|-------|----------|-------|------|
| **Sonnet 4.5** | Daily coding, most tasks | Fast | $3/$15 per M tokens |
| **Opus 4.5** | Complex bugs, architecture, hard problems | Slower | $5/$25 per M tokens |
| **Haiku 4.5** | Quick questions, simple tasks | Fastest | $1/$5 per M tokens |

### When to Switch

| Situation | Action |
|-----------|--------|
| Stuck on a complex bug | `/model` → Opus |
| Simple repetitive tasks | `/model` → Haiku |
| Normal daily work | Stay on Sonnet (default) |
| Architecture decisions | `/model` → Opus |
| Quick "what does this do?" | Haiku is enough |

### How to Switch
```
/model
# Shows list — pick one
```

### ⚡ Quick Demo (1 min)
1. Show `/model` command
2. Switch to Opus
3. Ask a complex question
4. Switch back to Sonnet

### Key Takeaway
> "Sonnet for daily work, Opus when you're stuck, Haiku for quick stuff."

---

## 2.7 Cost Awareness (2 min)

### Concept to Explain
- Claude Code uses tokens — input + output
- Longer conversations = more tokens = higher cost
- `/compact` helps reduce token usage

### Ways to Monitor & Control Cost

| Method | What It Does |
|--------|--------------|
| `/status` | Shows current session info including token usage |
| `/compact` | Summarizes conversation to save tokens |
| `/clear` | Resets conversation completely |
| Model choice | Haiku < Sonnet < Opus (cost) |

### Cost-Saving Tips

| Tip | Why |
|-----|-----|
| Use `/compact` in long sessions | Reduces context size |
| Start fresh for new tasks | Don't carry old context |
| Use Haiku for simple questions | 3x cheaper than Sonnet |
| Be specific in prompts | Fewer back-and-forth = fewer tokens |

### Subscription vs API
- **Pro/Max subscription**: Fixed monthly cost, usage limits
- **API (Console)**: Pay per token, no limits but can get expensive

### Key Takeaway
> "Use `/compact` often, pick the right model, and start fresh conversations for new tasks."

---

## 2.8 Git Workflows (3 min)

### Key Points
- Many Anthropic engineers use Claude for 90%+ of git interactions
- Claude looks at your changes and recent history automatically to compose commit messages

### Essential Commands

| Task | Prompt |
|------|--------|
| Commit | "commit" |
| Create PR | "pr" |

### The "pr" Shorthand
Just type "pr" and Claude will:
1. Stage changes if needed
2. Generate a meaningful commit message
3. Push to remote
4. Create PR with description
5. Give you the link

### ⚡ Quick Demo (1-2 min)
1. Make a small code change
2. Type "commit" — show Claude generating a message
3. Type "pr" — show Claude creating the PR

### Key Takeaway
> "Just type 'commit' or 'pr' — Claude handles the rest."

---

## 2.9 todo.md (4 min)

### Concept to Explain
- When working on a big feature, Claude creates a todo.md with a plan
- Claude tracks progress, checks off completed items
- Helps Claude stay on track during complex tasks

### How It Works
```
You give a complex task
       ↓
Claude creates todo.md with steps
       ↓
Works through each item
       ↓
Checks off as it completes
       ↓
You see progress in real-time
```

### Example todo.md
```markdown
# Todo: Add User Authentication

- [x] Create User model with email/password fields
- [x] Set up password hashing utility
- [ ] Build login API endpoint
- [ ] Build signup API endpoint
- [ ] Add JWT token generation
- [ ] Create auth middleware
- [ ] Write tests for auth flow
```

### When Claude Creates It
- Complex multi-step features
- Tasks with many files to modify
- Anything that takes more than a few minutes

### You Can Also Create It
- Write your own todo.md before starting
- Claude will follow your plan instead of making its own

### ⚡ Live Demo (2 min)
1. Ask: "Add a complete password reset flow with email verification"
2. Watch Claude create todo.md
3. Show the checklist structure
4. Show items getting checked off as Claude works

### Key Takeaway
> "For big tasks, Claude makes a plan first. You can see exactly what's happening and what's left."

---

## 2.10 CLAUDE.md File + Imports (5 min)

### Concept to Explain
- CLAUDE.md is a special file that Claude automatically pulls into context when starting a conversation
- CLAUDE.md files can now import other files using `@path/to/file.md`

### Basic CLAUDE.md
```markdown
# Project: MyApp

## Tech Stack
- React 18 + TypeScript
- TailwindCSS for styling

## Commands
- `npm run dev` — start dev server
- `npm test` — run tests

## Code Conventions
- Use functional components only
- Prefer named exports
```

### What to Include

| Section | Examples |
|---------|----------|
| Repository etiquette | Branch naming, merge vs rebase, PR process |
| Developer environment | Required tools, versions, setup commands |
| Unexpected behaviors | Known quirks, things to avoid |
| Tech stack | Languages, frameworks, key libraries |
| Code style | Formatting rules, naming conventions |
| Testing | How to run tests, coverage requirements |

### Using Imports
```markdown
# CLAUDE.md

## Project Overview
This is our main web application.

## Imports
@docs/coding-standards.md
@docs/api-patterns.md
@docs/testing-guide.md
```

### Import Use Cases

| Scenario | How to Use |
|----------|------------|
| Shared team standards | Import from central docs folder |
| Large documentation | Split into multiple files |
| Different contexts | Import only what's relevant |
| Monorepo | Each package has own CLAUDE.md with shared imports |

### File Structure Example
```
project/
├── CLAUDE.md              # Main file with imports
├── docs/
│   ├── coding-standards.md
│   ├── api-patterns.md
│   └── testing-guide.md
└── src/
```

### ⚡ Live Demo (2 min)
1. Show a CLAUDE.md with imports
2. Show the imported files
3. Ask Claude a question that requires info from imported file
4. Show Claude using that context

### Key Takeaway
> "Use imports to keep CLAUDE.md clean while loading all the context Claude needs."

---

# Part 3: Intermediate (32 min)

*Cover concepts + select demos*

| Topic | Duration | Demo |
|-------|----------|------|
| Effective Prompting | 7 min | ✅ |
| Multi-file Operations | 5 min | Optional |
| Test-Driven Workflow | 4 min | Optional |
| Subagents | 5 min | ✅ |
| Custom Commands | 5 min | ✅ |
| @ Mentions | 2 min | ✅ |
| Image/Screenshot Support | 3 min | ✅ |
| VS Code Extension | 4 min | ✅ |

---

## 3.1 Effective Prompting (7 min)

### The Problem
- Without research and planning steps, Claude tends to jump straight to coding a solution
- The common mistake isn't being too vague — it's not giving Claude the context to make good decisions

### The Multi-Step Workflow

| Step | Prompt | Why |
|------|--------|-----|
| 1. Research | "Look at how X is currently done" | Understand existing patterns |
| 2. Plan | "Create a plan — don't code yet" | Catch issues early |
| 3. Implement | "Now implement the plan" | Focused execution |
| 4. Verify | "Run tests and fix failures" | Quality check |
| 5. Commit | "Commit and create a PR" | Clean handoff |

### Good vs Bad Prompts

| ❌ Vague Prompt | ✅ Better Prompt |
|----------------|------------------|
| "Fix the login bug" | "Fix the null pointer error in UserService.getById — check the database query and add null handling" |
| "Add a feature" | "Add a dark mode toggle to the settings page. Use our existing theme context in /contexts/theme.js. Match the style of other toggles on that page." |
| "Refactor this" | "Refactor the UserService class to use dependency injection. Keep the public API the same so existing tests pass." |

### Prompt Structure Template
```
[What] — What you want done
[Where] — Which files/areas to focus on
[Constraints] — What to preserve, avoid, or match
[Verification] — How to know it's done right
```

### ⚡ Live Demo (3-4 min)
1. Show a vague prompt: "Add validation to the form"
   - Claude might ask questions or make assumptions
2. Show a structured prompt: "Add email and password validation to the signup form in /components/SignupForm.jsx. Email should check format, password needs 8+ chars with one number. Show inline error messages matching our existing error styles in FormError component."
   - Claude executes with precision
3. Highlight the difference in output quality

### Key Takeaway
> "Two minutes of prompt clarity saves twenty minutes of back-and-forth."

---

## 3.2 Multi-file Operations (5 min)

### Concept to Explain
- Claude can read and modify multiple files in a single task
- Understands relationships between files (imports, dependencies, types)

### Common Use Cases

| Task | Example Prompt |
|------|----------------|
| Rename/refactor | "Rename the User class to Account and update all imports across the codebase" |
| Bulk updates | "Add TypeScript types to all functions in the /utils folder" |
| Pattern changes | "Replace all console.log statements with our logger utility" |
| API changes | "The getUserById endpoint now returns { user, metadata } instead of just user. Update all call sites." |

### Tips
- Be explicit about scope: "only in /src" or "across the entire repo"
- Ask Claude to list affected files first before making changes
- Use default mode for large refactors to review each change

### Demo (Optional — 2 min if time permits)
- "Find all places where we catch errors and just log them. Replace with proper error handling using our ErrorBoundary pattern."

### Key Takeaway
> "Think of Claude as a codebase-aware find-and-replace on steroids."

---

## 3.3 Test-Driven Workflow (4 min)

### Concept to Explain
- This is an Anthropic-favorite workflow for changes that are easily verifiable with tests

### The TDD Flow with Claude
```
Step 1: "Write failing tests for [feature/fix] — don't implement yet"
         ↓
Step 2: "Run the tests and confirm they fail"
         ↓
Step 3: "Now implement the code to make tests pass"
         ↓
Step 4: "Run tests again and fix any failures"
         ↓
Step 5: "Commit with message describing the change"
```

### Example Prompts

| Step | Prompt |
|------|--------|
| Tests first | "Write unit tests for a new calculateDiscount function that takes price and percentage, handles edge cases like negative values and values over 100%" |
| Verify failing | "Run the tests — they should fail since the function doesn't exist" |
| Implement | "Now implement calculateDiscount to make all tests pass" |
| Verify passing | "Run tests again" |

### Why This Works
- Tests define the expected behavior upfront
- Claude has clear success criteria
- You get test coverage as a byproduct
- Easy to verify Claude did the right thing

### Key Takeaway
> "When you can define 'done' with a test, let the test guide Claude."

---

## 3.4 Subagents (5 min)

### Concept to Explain
- Subagents delegate specialized tasks — like spinning up a backend API while the main agent builds the frontend
- Main Claude can spawn focused subagents for specific tasks
- Subagents work independently, report back to main agent

### How It Works
```
Main Agent (your conversation)
       ↓
   Spawns subagent for specific task
       ↓
   Subagent works independently
       ↓
   Returns result to main agent
       ↓
Main Agent continues with that context
```

### When Subagents Help

| Scenario | How Subagents Work |
|----------|-------------------|
| Large feature | Main plans, subagents implement different parts |
| Research + implement | Subagent researches patterns, main implements |
| Parallel tasks | Multiple subagents work on independent components |

### Example Prompts

| Task | Prompt |
|------|--------|
| Parallel work | "Create the API endpoints and have a subagent build the frontend components simultaneously" |
| Focused research | "Use a subagent to analyze how error handling is done across the codebase, then suggest improvements" |
| Complex feature | "Build the user dashboard — use subagents for the chart component, data fetching, and styling" |

### ⚡ Live Demo (2 min)
1. Ask: "Build a contact form with validation — use a subagent to create the email service while you build the form component"
2. Show subagent spawning
3. Show parallel work happening
4. Show results coming together

### Key Takeaway
> "Subagents let you parallelize work — think of them as delegating to junior devs."

---

## 3.5 Custom Commands (5 min)

### Concept to Explain
- You can create your own slash commands for repetitive tasks
- Commands live in your project and are reusable
- Great for team-specific workflows

### Where Commands Live

| Location | Scope |
|----------|-------|
| `.claude/commands/` | Project-specific commands |
| `~/.claude/commands/` | Global commands (all projects) |

### Command File Structure
```markdown
# .claude/commands/component.md

Create a new React component with the following structure:
- Functional component with TypeScript
- Use our standard Props interface pattern
- Include basic unit test file
- Add to the components index

Component name: $ARGUMENTS
```

### Using Custom Commands
```
/component UserProfile
/component PaymentForm
```

### Example Commands to Create

| Command | What It Does |
|---------|--------------|
| `/component <name>` | Creates React component + test + index export |
| `/api <endpoint>` | Creates API route with error handling |
| `/test <file>` | Generates tests for a specific file |
| `/review` | Runs code review checklist on staged changes |
| `/deploy-check` | Runs pre-deployment verification |

### Example: /review Command
```markdown
# .claude/commands/review.md

Review the staged changes for:
1. Security issues (SQL injection, XSS, auth problems)
2. Performance concerns (N+1 queries, unnecessary re-renders)
3. Code style violations
4. Missing error handling
5. Missing tests for new functionality

Provide a summary with severity levels.
```

### ⚡ Live Demo (2-3 min)
1. Show `.claude/commands/` folder
2. Create a simple command file (e.g., `/component`)
3. Use the command: `/component TestCard`
4. Show Claude following the template
5. Show how arguments (`$ARGUMENTS`) get passed in

### Key Takeaway
> "Custom commands turn your team's best practices into one-word actions."

---

## 3.6 @ Mentions (2 min)

### Concept to Explain
- Quickly reference files, folders, or symbols in your prompts
- Saves time vs typing full paths

### How to Use

| Syntax | What It Does |
|--------|--------------|
| `@filename` | References a specific file |
| `@folder/` | References a folder |
| `@symbol` | References a function/class/variable |

### Examples

| Task | Prompt |
|------|--------|
| Explain a file | "Explain @src/utils/auth.js" |
| Compare files | "Compare @old-api.js and @new-api.js" |
| Focus on folder | "Find all bugs in @src/components/" |
| Reference function | "Optimize the @calculateTotal function" |

### With Custom Commands
```markdown
# .claude/commands/test.md
Write tests for @$ARGUMENTS
```
Usage: `/test src/utils/validator.js`

### ⚡ Quick Demo (1 min)
1. Type a prompt with `@` and show autocomplete
2. Select a file
3. Ask Claude to explain it

### Key Takeaway
> "Use @ to quickly reference files instead of typing full paths."

---

## 3.7 Image/Screenshot Support (3 min)

### Concept to Explain
- Claude Code can analyze images and screenshots
- Useful for debugging UI, understanding diagrams, reading error screenshots

### What Claude Can Analyze

| Image Type | Use Case |
|------------|----------|
| Screenshots of errors | "What's wrong here?" |
| UI mockups | "Implement this design" |
| Architecture diagrams | "Explain this system" |
| Handwritten notes | "Convert to code" |
| Console output | "Debug this error" |

### How to Use

| Method | How |
|--------|-----|
| Drag & Drop | Drag an image into the Claude Code terminal |
| File Path | "Analyze the screenshot at ./screenshots/error.png" |
| Clipboard | Take screenshot, paste directly (if supported) |

### Example Prompts

| Task | Prompt |
|------|--------|
| Debug UI | "Here's a screenshot of the bug. The button should be blue, not red. Fix it." |
| Implement design | "Implement this Figma mockup as a React component" [drag image] |
| Read error | "What does this error mean and how do I fix it?" [drag screenshot] |
| Understand diagram | "Explain this architecture diagram and implement the auth flow" |

### ⚡ Live Demo (1-2 min)
1. Take a screenshot of an error or UI
2. Drag into Claude Code
3. Ask: "What's wrong here?" or "Implement this"
4. Show Claude analyzing and responding

### Key Takeaway
> "Screenshot an error or UI, drop it in, and let Claude see what you see."

---

## 3.8 VS Code Extension (4 min)

### Concept to Explain
- Native VS Code extension brings Claude Code directly into your IDE
- Dedicated sidebar panel with inline diffs
- Same capabilities, graphical interface

### Terminal vs Extension

| Terminal | VS Code Extension |
|----------|-------------------|
| Full keyboard control | Visual diff previews |
| Faster for power users | Better for reviewing changes |
| Works anywhere (SSH, containers) | Integrated with editor |
| Multiple sessions easy | Side-by-side with code |

### How to Install
1. Open VS Code Extensions (Cmd/Ctrl + Shift + X)
2. Search "Claude Code"
3. Install the official Anthropic extension
4. Authenticate (same as terminal)

### Key Features to Show
- Sidebar chat panel
- Inline diffs before accepting
- File tree awareness
- Quick actions from editor context menu

### ⚡ Live Demo (2-3 min)
1. Open VS Code with extension installed
2. Start a task from sidebar: "Explain this function"
3. Make a change request: "Add input validation here"
4. Show the inline diff preview
5. Accept/reject flow

### Key Takeaway
> "Terminal for speed, extension for visual review — use both based on the task."

---

# Part 4: Advanced — Awareness Only (5-10 min)

*Just name these so they know what's possible*

| Topic | What It Is | One-liner |
|-------|-----------|-----------|
| **Headless Mode** | `claude -p` runs Claude programmatically without UI | CI/CD automation, scripts |
| **Git Worktrees** | Run multiple Claude sessions on different branches simultaneously | Parallel development |
| **Background Tasks** | Keep dev servers active without blocking Claude | Non-blocking operations |
| **Skills** | Pre-built capabilities for docx, pptx, xlsx, pdf | Document generation |
| **Hooks** | Custom scripts before/after Claude actions | Team guardrails, automation |
| **MCP** | Model Context Protocol — connect to external tools | Extensibility layer |
| **Plugins** | Claude Code plugins extend functionality | Team-specific tools |
| **Claude Agent SDK** | Build custom agents using Claude Code's core | Your own AI agents |
| **Claude Code on Web** | Browser-based, no terminal needed | Delegate from anywhere |
| **GitHub Actions** | Auto-label issues, review PRs, background tasks | Automated workflows |
| **JetBrains Extension** | Native integration with IntelliJ, PyCharm, etc. | IDE choice |

---

### Quick Explainers (if time permits)

**Headless Mode:**
```bash
# Simple command
claude -p "Update all copyright headers to 2025"

# In CI/CD
gh pr diff 123 | claude -p "Review for security issues" --output-format json
```

**Skills:**
- Claude has built-in "skills" for creating professional documents
- Ask Claude to create a PowerPoint → it reads the pptx skill and follows best practices
- Available for: Word docs, Excel, PDFs, presentations

**Hooks:**
- Scripts that trigger automatically on Claude events
- Pre-commit: Run linter before every commit
- Post-edit: Auto-format changed files
- Location: `.claude/hooks/`

**MCP (Model Context Protocol):**
- Standard protocol for connecting Claude to external tools
- Examples: Database access, Slack, Google Drive, custom APIs
- Growing ecosystem of MCP servers

---

# Part 5: Q&A (5-10 min)

- Questions from the team
- Share internal guidelines or policies
- Discuss next steps for adoption
- Point to documentation: **claude.ai/code**

---

# Quick Reference Cheat Sheet

## Essential Commands
| Command | Purpose |
|---------|---------|
| `/help` | Show all commands |
| `/clear` | Reset conversation |
| `/model` | Switch models |
| `/compact` | Save tokens |
| `/rewind` | Undo changes |
| `Esc Esc` | Quick rewind |
| `Shift+Tab` | Change mode |
| `Ctrl+R` | Search history |

## Models
| Model | Use For |
|-------|---------|
| Sonnet | Daily work |
| Opus | Hard problems |
| Haiku | Quick tasks |

## Key Files
| File | Purpose |
|------|---------|
| `CLAUDE.md` | Project context |
| `todo.md` | Task planning |
| `.claude/commands/` | Custom commands |

## Magic Words
| Say | Get |
|-----|-----|
| "commit" | Auto commit message |
| "pr" | Create pull request |
| "think" | Extended thinking |
| "ultrathink" | Maximum thinking |

---

# Resources

- **Documentation:** https://claude.ai/code
- **Best Practices:** https://www.anthropic.com/engineering/claude-code-best-practices
- **VS Code Extension:** Search "Claude Code" in VS Code Marketplace
- **GitHub:** https://github.com/anthropics/claude-code

---

*Document prepared for Kissflow internal training session*
*Last updated: November 2024*
