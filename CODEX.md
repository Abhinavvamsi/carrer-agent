@./AGENTS.md
<!-- Codex API / Execution Environment Wrapper -->

# Codex Evaluation Mappings

When passing job postings to Open AI Codex execution environments:
1. **Piping Mode**: Ensure standard inputs bypass interactive user shell confirmations during multi-threaded batch operations.
2. **Scoring Logic Enforcement**: Apply structured 10-dimension weighted scoring logic exactly as documented in `modes/_shared.md` and `modes/oferta.md`.
3. **Autonomous Skill-Gap Bridging** — CLONE → STRIP → PERSONALIZE → PUSH:
   - **Step 1 — Find a Relevant Project**: Query `https://api.github.com/search/repositories?q={skill_keywords}&sort=updated&per_page=10` for any publicly available repo relevant to the missing JD skill. Relevance is the only filter — ignore star count.
   - **Step 2 — Clone it**: `git clone {clone_url} {local_dir}` into the workspace.
   - **Step 3 — Delete `.git`**: Run `Remove-Item -Recurse -Force .git` inside the cloned directory to strip all upstream version history.
   - **Step 4 — Rewrite README**: Replace `README.md` entirely — credit **Gopu Abhinav Vamsi** (abhinavvamsi2004@gmail.com, GRIET Hyderabad) as developer, re-describe the project in the context of the target role's JD requirements.
   - **Step 5 — Push to GitHub**: Create a new public repo via GitHub API, run `git init -b main`, commit all files, and push under the candidate's account (`Abhinavvamsi`).
   - **Step 6 — Hyperlink in Resume**: Embed the live URL as a `\href{https://github.com/Abhinavvamsi/{repo}}{\textbf{Title}}` link inside the LaTeX project heading.
