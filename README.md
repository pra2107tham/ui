We are designing an AI-powered UI validation architecture for this repository.

This system must validate real UI behavior using the Playwright MCP server.

IMPORTANT CONSTRAINTS:
- Do NOT assume any application pages.
- Do NOT assume selectors.
- Do NOT assume flows.
- Do NOT generate Java or Cucumber test code.
- Do NOT create execution scripts yet.
- Do NOT invent application structure.
- Do NOT proceed with file creation until consulting me.

=====================================================
SYSTEM GOAL
=====================================================

We want a project-level architecture that:

• Reads UI scenarios or Jira feature descriptions provided as prompts
• Understands the described business flow
• Uses Playwright MCP server as a tool to interact with the live application
• Executes navigation, interaction, assertions, and screenshots through MCP
• Produces structured validation output (PASS/FAIL, evidence, observations)
• Scales for a very large enterprise application with many domains/pages
• Remains modular and maintainable

Playwright MCP server must be treated as:

- The execution layer (browser automation)
- The only mechanism for interacting with the live UI
- A tool available to the master agent
- Used for navigation, interaction, state inspection, and screenshot capture

=====================================================
ARCHITECTURE COMPONENTS TO DESIGN
=====================================================

We want to implement:

1) A master agent file (under agents/)
   - Responsible for reasoning, orchestration, and MCP tool usage
   - Explicitly lists Playwright MCP as a tool
   - Processes both:
        • Jira feature descriptions
        • Direct UI scenario prompts
   - Dynamically determines which skills to consult
   - Uses phase-based reasoning (explore, validate, report)
   - Outputs structured results

2) A modular skill structure under:
   .github/skills/

   Skills must:
   - Be grouped intelligently (by domain/page/feature — you decide and justify)
   - Contain application knowledge (NOT assumptions)
   - Guide MCP usage per domain
   - Be scalable for large apps
   - Avoid duplicating global rules

3) A global umbrella instructions file:
   .github/copilot-instructions.md

   It must:
   - Define overall validation philosophy
   - Define selector priority strategy
   - Define MCP usage principles
   - Define retry logic expectations
   - Define artifact/reporting format
   - Explain how scenarios are interpreted
   - Apply across all agents and skills

=====================================================
YOUR TASK
=====================================================

STEP 1:
Propose a scalable architecture for:

- agents/
- .github/skills/
- .github/copilot-instructions.md

Explain in detail:

• How the master agent should reason
• How it should use Playwright MCP server safely and deterministically
• How skills should be structured
• How skills should be grouped for a very large application
• What sections each SKILL.md must contain
• How the umbrella instructions file should be structured
• How dynamic skill loading should work
• How Jira descriptions and UI scenario prompts should both be handled
• How the agent separates reasoning vs execution

Do NOT create any files yet.

STEP 2:
Ask me structured discovery questions about:

• Major domains/pages of the application
• Authentication mechanism
• Navigation patterns
• Whether data-test selectors exist
• Any known fragile UI areas
• Any domain-specific business rules
• Any environment constraints for MCP execution
• How failures should be reported

You must wait for my answers before proceeding.

STEP 3:
After I provide real application details,
generate:

- One master agent file
- A domain-based skill folder structure
- Template SKILL.md files (structured placeholders, not fake selectors)
- A global copilot-instructions.md

Everything must be:

• Modular
• Enterprise-scalable
• Deterministic
• Explicit about Playwright MCP usage
• Explicit about reading Jira or UI scenario prompts
• Free of assumptions
• Structured and maintainable

Do NOT simplify the design.
Do NOT invent pages.
Consult me first.

Proceed with STEP 1 only.
