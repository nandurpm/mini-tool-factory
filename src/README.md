# Src

## Purpose

Contains the production implementation of Mini Tool Factory: command handling, domain rules, storage, reports, and local serving as applicable.

## Contents

- `cli.mjs` — Implements Mini Tool Factory's command-line interface and coordinates validation, persistence, report generation, and local serving.
- `engine.mjs` — Validates tool specifications and coordinates Mini Tool Factory's deterministic project-generation pipeline.
- `render.mjs` — Generates and serves Mini Tool Factory's demonstration report through a deployment-friendly HTTP host.
- `report.mjs` — Builds Mini Tool Factory's self-contained report artifacts and browser-side interactions from validated data.
- `schema.mjs` — Defines and validates the controlled specification schema accepted by Mini Tool Factory.
- `templates.mjs` — Renders the bounded project templates emitted by Mini Tool Factory's generation engine.

## Responsibilities

Production behavior belongs here. Generated reports, user data, and repository documentation should remain outside this folder.

## Important Notes

- This folder is part of **Mini Tool Factory** and should be kept consistent with the commands and architecture documented in the root README.
- Paths and file roles listed above reflect the current repository implementation.

