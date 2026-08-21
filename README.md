# DeepSeek Harness Documentation

This repository is our working guide to the DeepSeek Harness architecture,
tool surface, agent presets, and extension workflows.

The architectural material is currently based on DeepSeek Harness
`dsh-v0.1.0-rc.8` unless a document states a more specific revision.

## Start here

| Document | Purpose |
|---|---|
| [Project guide](project.md) | Repository structure, important package groups, runtime composition, turn flow, and Cordis concepts. |
| [Tool reference](tools.md) | Model-visible tools, argument schemas, execution modes, and tool-organization guidance. |
| [Ephemeral AI Harness preset](ephemeral_ai_harness_preset.md) | The selected tool surface and composition for our coding-agent preset. |

## How-to guides

| Guide | Outcome |
|---|---|
| [Create and load a preset](how-to/create-a-preset.md) | Copy a preset, edit its Cordis composition, load it in a real session, and understand reload boundaries. |
| [Create a background tool with jobs and notifications](how-to/create-a-background-tool-with-jobs-and-notifications.md) | Promote long-running work into `ctx.jobs`, expose one `job_id`, retain tool-owned output, wake the owning agent safely, and prevent duplicate completion delivery. |
| [Publish npm packages](how-to/publish-npm-packages.md) | Validate identity and contents, authenticate securely, publish directly or through an existing-package stage, verify the public tarball, and recover from common registry failures. |
| [pi-ai 0.82.1 → 0.84.2 compatibility study](how-to/pi-ai-0.82.1-to-0.84.2-compatibility-study.md) | Compare catalog, thinking, stop-reason, deferred-request, tool, replay, and Grok 4.6 changes against the DSH `llm-pi-ai` adapter. |
| [Route DSH Codex and xAI through Veee](how-to/route-dsh-codex-and-xai-through-veee.md) | Persist the Veee `x.ai` proxy rule, route DSH/Codex/Grok through Veee, auto-load Codex authentication, and verify the complete route. |

## Documentation boundaries

- `project.md` is the architectural index. It explains where behavior lives and
  how the runtime is composed.
- `tools.md` is the model-facing contract reference. It describes what agents
  can call and how the tools are grouped.
- `ephemeral_ai_harness_preset.md` records one concrete preset decision.
- `how-to/` contains task-oriented procedures that lead to a verifiable result.

## Verification convention

Architecture claims should identify the DeepSeek Harness revision against
which they were checked. Implementation guides should include both automated
checks and a live event-order check when agent scheduling is part of the
contract. UI row placement alone is not sufficient evidence for inbox or turn
causality; inspect the persisted session events.
