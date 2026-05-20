# Skill Creator — Industrial Real Estate & ERP Edition

Build reusable Claude skills for real estate, fund management, and ERP workflows.

## Core Purpose
Encode institutional knowledge into a reusable skill when workflows repeat or gaps exist in your skill library.

## Essential Structure
Each skill requires a `SKILL.md` file (under 150 lines) with instructions for Claude. Optional: reference documents and templates.

## Creation Process

**Step 1 — Definition**
Answer five questions:
1. What is the skill name? (verb-noun format)
2. What triggers it? (what does the user say/need?)
3. What inputs are required?
4. What is the output format?
5. What are the quality standards / acceptance criteria?

**Step 2 — Documentation**
Write SKILL.md with sections:
- Trigger conditions
- Required inputs (and what to ask for if missing)
- Workflow steps (numbered)
- Output format (with example)
- Quality gates / checklist

**Step 3 — Testing**
Validate that Claude:
- Requests missing information
- Follows the steps in order
- Matches the specified output format
- Produces usable results

**Step 4 — Installation**
Save to `~/.claude/commands/[skill-name].md` for global availability.

## Suggested Skills to Build
- CAM reconciliation
- Broker opinions of value
- Tenant credit analysis
- Yardi report building
- Waterfall calculations
- Capital call notices
