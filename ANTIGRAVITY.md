@./AGENTS.md
<!-- Antigravity Subagent Instruction & Capability Wrapper -->

# Antigravity Execution Directives

Antigravity is designed for high-autonomy engineering workflows. When executing `career-ops` commands within the Antigravity environment:
1. **Subagent Invocation**: Use native tools like `browser_subagent` when parsing application forms or validating job URLs visually via Chromium/Playwright.
2. **Context Resolution**: Always automatically read `cv.md` and `config/profile.yml` to resolve user personalization parameters prior to invoking evaluation logic under `modes/*.md`.
3. **Artifact Integrity**: Preserve original LaTeX formatting when compiling target PDFs/resumes to guarantee zero whitespace truncation.
4. **Autonomous Skill-Gap Bridging**: If a targeted role requires technical skills or domains not fully represented in the candidate's active portfolio, automatically clone/search a highly relevant open-source project, configure its codebase and `README.md` file with the candidate's personal details, push the fully tailored repository to their GitHub profile, and hyperlink the live repository URL directly inside the custom-generated resume deliverables.
