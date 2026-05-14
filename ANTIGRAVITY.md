@./AGENTS.md
<!-- Antigravity Subagent Instruction & Capability Wrapper -->

# Antigravity Execution Directives

Antigravity is designed for high-autonomy engineering workflows. When executing `career-ops` commands within the Antigravity environment:
1. **Subagent Invocation**: Use native tools like `browser_subagent` when parsing application forms or validating job URLs visually via Chromium/Playwright.
2. **Context Resolution**: Always automatically read `cv.md` and `config/profile.yml` to resolve user personalization parameters prior to invoking evaluation logic under `modes/*.md`.
3. **Artifact Integrity**: Preserve original LaTeX formatting when compiling target PDFs/resumes to guarantee zero whitespace truncation.
4. **Autonomous Skill-Gap Bridging** — CLONE FIRST, BUILD LAST:
   - **Step 1 — GitHub Search**: Use the GitHub search API (`https://api.github.com/search/repositories?q={keywords}&sort=stars`) to identify an existing well-maintained public repository that closely matches the missing skill domain. Prefer repositories with >50 stars, recent commits, and a clear README.
   - **Step 2 — Clone & Personalize**: Run `git clone {repo_url} {local_target_dir}` inside the workspace. Then:
     - Replace `README.md` entirely with a custom-written version crediting **Gopu Abhinav Vamsi** (email: abhinavvamsi2004@gmail.com) as the developer, describing the project in terms of the target JD requirements.
     - Strip `.git` directory and reinitialize: `rm -rf .git && git init -b main`.
   - **Step 3 — Push to GitHub**: Create a new public repo on GitHub via API, set remote, commit, and push.
   - **Step 4 — Hyperlink in Resume**: Embed the live repository URL as a `\href{}{}` hyperlink inside the corresponding project heading in the generated LaTeX resume.
   - **NEVER build a project from scratch** if an appropriate open-source repository already exists. Cloning saves significant engineering time and compute credits.
