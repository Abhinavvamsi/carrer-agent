@./AGENTS.md
<!-- Antigravity Subagent Instruction & Capability Wrapper -->

# Antigravity Execution Directives

Antigravity is designed for high-autonomy engineering workflows. When executing `career-ops` commands within the Antigravity environment:
1. **Subagent Invocation**: Use native tools like `browser_subagent` when parsing application forms or validating job URLs visually via Chromium/Playwright.
2. **Context Resolution**: Always automatically read `cv.md` and `config/profile.yml` to resolve user personalization parameters prior to invoking evaluation logic under `modes/*.md`.
3. **Artifact Integrity**: Preserve original LaTeX formatting when compiling target PDFs/resumes to guarantee zero whitespace truncation.
4. **Autonomous Skill-Gap Bridging** — CLONE → STRIP → PERSONALIZE → PUSH:
   - **Step 1 — Find a Relevant Project**: Search GitHub (`https://api.github.com/search/repositories?q={role_skill_keywords}&sort=updated&per_page=10`) for any publicly available project that is relevant to the missing skill domain. Do NOT filter by star count — relevance to the JD is the only criteria.
   - **Step 2 — Clone it**: `git clone {repo_clone_url} {local_dir}` inside the workspace directory.
   - **Step 3 — Delete `.git`**: Immediately run `Remove-Item -Recurse -Force .git` (Windows) inside the cloned directory to strip all upstream history.
   - **Step 4 — Rewrite README**: Replace the `README.md` entirely. Credit **Gopu Abhinav Vamsi** (abhinavvamsi2004@gmail.com, GRIET Hyderabad) as the developer. Describe the project in terms of the target JD's specific requirements and tech stack.
   - **Step 5 — Push to GitHub**: Create a new public repo via the GitHub API, initialize fresh git (`git init -b main`), add all files, commit, set remote, and push.
   - **Step 6 — Hyperlink in Resume**: Embed the live repo URL as a `\href{https://github.com/Abhinavvamsi/{repo-name}}{\textbf{Project Title}}` inside the LaTeX resume project heading.
