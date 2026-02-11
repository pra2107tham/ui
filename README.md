We are designing an AI-powered UI validation architecture for this repository.

IMPORTANT:
Do NOT assume any application pages.
Do NOT assume selectors.
Do NOT assume flows.
Do NOT generate Java or test code.
Do NOT generate execution scripts yet.

The system we want to build should:

• Read UI scenarios or Jira feature descriptions provided as prompts
• Understand the business flow described
• Use Playwright MCP server to interact with the live application
• Validate actual UI behavior
• Produce structured results
• Scale for a very large enterprise application with many pages

We want to architect this properly at a project level using:

1) A master agent file
2) Modular page/feature-based skills
3) A global umbrella instructions file
4) A scalable folder structure

However:

You do NOT know our application pages.
You do NOT know our UI structure.
You must consult us before finalizing skill structure.

YOUR TASK

Step 1:
Propose a clean, scalable architecture for:

- agents/
- .github/skills/
- .github/copilot-instructions.md

Explain:

• How the master agent should behave
• How skills should be structured
• How skills should be grouped (by page? by domain? by feature?)
• What sections each SKILL.md should contain
• What the umbrella instructions file should contain
• How the agent should dynamically load relevant skills
• How it should handle very large applications
• How it should process:
     - Jira feature descriptions
     - Direct UI scenario prompts

Step 2:
Before creating any files, ask me:

• What are the major domains/pages of the application?
• Are there stable data-test selectors?
• How authentication works?
• Any known edge-case patterns?
• Any navigation rules?
• Any environment constraints?

Do NOT create any files until you ask me for this information.

Step 3:
After I respond with real application details,
generate:

- One master agent file
- A proposed skill folder structure based on actual pages/domains
- A structured copilot-instructions.md
- Template SKILL.md format (not filled with fake selectors, but structured placeholders)

Everything must be:

• Modular
• Enterprise scalable
• Maintainable
• Deterministic
• No hardcoded pages
• No assumptions

Do not simplify the architecture.
Do not guess application structure.
Consult me first.
Proceed with Step 1 only.
