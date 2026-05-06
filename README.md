# Stitch Agent Skills

A library of Agent Skills designed to work with the Stitch MCP server. Each skill follows the Agent Skills open standard, for compatibility with coding agents such as Antigravity, Gemini CLI, Claude Code, Cursor.

## Installation & Discovery

Install any skill from this repository using the `skills` CLI. This command will automatically detect your active coding agents and place the skill in the appropriate directory.

```bash
# List all available skills in this repository
npx skills add google-labs-code/stitch-skills --list

# Install all available skills at once (globally)
npx skills add google-labs-code/stitch-skills --all --global

# Install all available skills at once (locally in current workspace)
npx skills add google-labs-code/stitch-skills --all

# Install a specific skill (e.g., react-components)
npx skills add google-labs-code/stitch-skills --skill react:components --global
```

## Available Skills

### 1. Stitch Design Skills
Focused on creating, managing, and optimizing designs within the Stitch platform.

#### Core Workflows
These skills represent the primary pipeline for generating designs and syncing them with code.

##### code-to-design
Converts existing frontend code (React, Vue, etc.) to a Stitch Design by chaining static HTML extraction, design system extraction, and file upload.

##### generate-design
Unified entry point for generating new screens from text or images, editing existing screens, and generating design variants using Stitch MCP.

##### manage-design-system
Manages design systems in the Stitch platform using MCP tools, including uploading `DESIGN.md` and applying themes to screens.

##### extract-design-md
Extracts a comprehensive design system (`DESIGN.md`) directly from frontend source code files without needing to build or render the application.

##### extract-static-html
Extracts self-contained static HTML from a running local web application or React components, inlining CSS and images.

##### upload-to-stitch
Uploads local assets (images, mockups, HTML files) to a Stitch project using a Python script to bypass token limits.

**Install all Core Design Workflows at once:**
```bash
npx skills add google-labs-code/stitch-skills --skill code-to-design --global && \
npx skills add google-labs-code/stitch-skills --skill extract-design-md --global && \
npx skills add google-labs-code/stitch-skills --skill extract-static-html --global && \
npx skills add google-labs-code/stitch-skills --skill generate-design --global && \
npx skills add google-labs-code/stitch-skills --skill manage-design-system --global && \
npx skills add google-labs-code/stitch-skills --skill upload-to-stitch --global
```

### 2. Stitch Build Skills
Focused on code generation, integration, and asset compilation.

#### react-components
Converts Stitch screens to React component systems with automated validation and design token consistency.

```bash
npx skills add google-labs-code/stitch-skills --skill react:components --global
```

#### remotion
Generates walkthrough videos from Stitch projects using Remotion with smooth transitions, zooming, and text overlays to showcase app screens professionally.

```bash
npx skills add google-labs-code/stitch-skills --skill remotion --global
```

#### shadcn-ui
Expert guidance for integrating and building applications with shadcn/ui components. Helps discover, install, customize, and optimize shadcn/ui components with best practices for React applications.

```bash
npx skills add google-labs-code/stitch-skills --skill shadcn-ui --global
```

### 3. Design Utilities & Assistants
Supporting tools for enhancing prompts, generating specs, and enforcing design standards.

#### design-md
Analyzes Stitch projects and generates comprehensive DESIGN.md files documenting design systems in natural, semantic language optimized for Stitch screen generation.

```bash
npx skills add google-labs-code/stitch-skills --skill design-md --global
```

#### enhance-prompt
Transforms vague UI ideas into polished, Stitch-optimized prompts. Enhances specificity, adds UI/UX keywords, injects design system context, and structures output for better generation results.

```bash
npx skills add google-labs-code/stitch-skills --skill enhance-prompt --global
```

#### stitch-loop
Generates a complete multi-page website from a single prompt using Stitch, with automated file organization and validation.

```bash
npx skills add google-labs-code/stitch-skills --skill stitch-loop --global
```

#### taste-design
Generates `DESIGN.md` files that enforce premium, anti-generic UI standards (strict typography, calibrated colors, asymmetric layouts).

```bash
npx skills add google-labs-code/stitch-skills --skill taste-design --global
```


## Repository Structure

Every directory within `skills/` or at the root level follows a standardized structure to ensure the AI agent has everything it needs to perform "few-shot" learning and automated quality checks.

```text
skills/[category]/
├── SKILL.md           — The "Mission Control" for the agent
├── scripts/           — Executable enforcers (Validation & Networking)
├── resources/         — The knowledge base (Checklists & Style Guides)
└── examples/          — The "Gold Standard" syntactically valid references
```

## Adding New Skills
All new skills need to follow the file structure above to implement the Agent Skills open standard.

### Great candidates for new skills
* **Validation**: Skills that convert Stitch HTML to other UI frameworks and validate the syntax.
* **Decoupling Data**: Skills that convert static design content into external mock data files.
* **Generate Designs**: Skills that generate new design screens in Stitch from a given set of data.

This is not an officially supported Google product. This project is not eligible for the [Google Open Source Software Vulnerability Rewards Program](https://bughunters.google.com/open-source-security).
