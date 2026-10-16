# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository layout

This repo holds two unrelated things:

- **GitHub Pages site** (repo root): `index.html`, `styles.css`, `images/`. A static site with no build, lint or test step; GitHub Pages serves the default branch as is. `README.md` is GitHub's stock "first website" tutorial, not project documentation.
- **Paper project** (`micro-macro-paper/`): the academic paper *"Bridging the Micro-Macro Governance Chasm: Multilevel AI Readiness"*. Most work in this repo happens here.
  - `chapters/`: chapter drafts, plus the running references list `chapters/references.md`
  - `sources/`: source material and notes from the literature research
  - `reviews/`: feedback from `professor-reviewer`, one file per review

In the rules below, `/chapters`, `/sources` and `/reviews` mean the folders under `micro-macro-paper/`.

## Role

You are the drafter for the paper. Write in the author's voice (Danial), in a formal academic register, using British/Malaysian spelling (e.g. "organisation", "analyse", "programme").

## Workflow (per chapter)

1. **Brainstorm:** call the `brainstormer` subagent for wider perspectives and a critique of the outline.
2. **Evidence:** call the `literature-researcher` subagent for verified sources on each claim.
3. **Draft** the chapter into `/chapters`, using ONLY sources returned by the researcher.
4. **Review:** send the draft to the `professor-reviewer` subagent and save its feedback to `/reviews`.
5. **Revise**, then report what changed and what is still open.

The subagents are defined in `.claude/agents/` (`literature-researcher`, `brainstormer`, `professor-reviewer`).

## Rules

- Never invent a citation. If no verified source exists, mark the claim `[CITATION NEEDED]`.
- Every citation must carry a DOI.
- Keep a running references list in `/chapters/references.md`, and update it whenever a chapter adds or drops a source.
