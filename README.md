# resume-writer

A [Claude Code](https://claude.com/claude-code) subagent that writes and tailors resumes and cover letters in LaTeX. It works from a durable master resume and generates job-specific, ATS-aware tailored versions without fabricating experience.

## What it does

- Builds a `master-resume.tex` from your background (interviews you for anything missing, or reads from an existing `achievements.md`)
- Tailors a copy of your resume to a specific job posting (paste text or a URL), reordering/trimming/rephrasing real bullets to match — never inventing experience, skills, or accomplishments
- Drafts a matching cover letter
- Compiles both to PDF via `latexmk`/`pdflatex`

See [`agents/resume-writer.md`](agents/resume-writer.md) for the full agent definition and workflow rules.

## Install

Copy the agent definition into your Claude Code agents directory:

```
cp agents/resume-writer.md ~/.claude/agents/resume-writer.md
```

Claude Code will pick it up automatically. Invoke it by asking to tailor, build, or update a resume — e.g. "tailor my resume to this job posting."

### Requirements

- A LaTeX distribution with `pdflatex`/`latexmk` on your `PATH` (e.g. [BasicTeX](https://tug.org/mactex/morepackages.html) or [MacTeX](https://tug.org/mactex/) on macOS, TeX Live on Linux)
- Your resume data lives in `~/Playground/Resume/` by default (see the agent file's directory layout) — adjust the paths in `agents/resume-writer.md` if you keep it elsewhere

## Contributing

Issues and PRs welcome — especially around:

- Improving the LaTeX templates
- Better ATS keyword handling
- Support for different resume directory layouts / non-LaTeX output

Please keep the "never fabricate experience" rule intact in any workflow changes — it's the core safety property of this agent.

## License

MIT
