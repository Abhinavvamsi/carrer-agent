@./AGENTS.md
<!-- Codex API / Execution Environment Wrapper -->

# Codex Evaluation Mappings

When passing job postings to Open AI Codex execution environments:
1. **Piping Mode**: Ensure standard inputs bypass interactive user shell confirmations during multi-threaded batch operations.
2. **Scoring Logic Enforcement**: Apply structured 10-dimension weighted scoring logic exactly as documented in `modes/_shared.md` and `modes/oferta.md`.
3. **Autonomous Skill-Gap Bridging** — CLONE FIRST, BUILD LAST:
   - **Step 1 — GitHub Search**: Query `https://api.github.com/search/repositories?q={skill_keywords}&sort=stars&per_page=5` to find a top-starred existing public repo matching the skill gap. Never build from scratch.
   - **Step 2 — Clone & Personalize**: Clone the best match, strip `.git`, reinitialize, replace `README.md` with a version crediting **Gopu Abhinav Vamsi** and describing the project against the JD requirements.
   - **Step 3 — Push to GitHub**: Create a new repo via GitHub API, push the personalized codebase under the candidate's account (`Abhinavvamsi`).
   - **Step 4 — Hyperlink in Resume**: Embed the live repo link as a `\href{}{}` anchor inside the matching LaTeX project heading.
   - This saves significant compute credits and engineering time — cloning is always preferred over generating.
