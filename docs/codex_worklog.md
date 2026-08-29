# Codex Worklog

## 2026-08-30 — Interaction structure and visual-evidence bridge

Goal: strengthen `grill-me-for-ui` without changing its upstream design-router role or turning it into a framework-specific implementation skill.

Changes:

- added an on-demand interaction and information-architecture playbook for consequential uncertainty about objects, actions, navigation, permissions, state transitions, and task continuity;
- added a lowest-useful-fidelity visual-probe playbook for decisions that remain abstract in text;
- routed complex Operate, multi-page, and structural work through Interaction / IA only when product structure can still change the design;
- expanded the optional implementation module with component reuse strategy, dimensional state transitions, operational copy, accessibility details, and vertical implementation handoff slices;
- expanded visual critique with tool-independent evidence alignment and an optional task walkthrough for complex flows;
- updated the long-term design contract and public README to reflect the new capabilities.

Scope decisions:

- retained the existing Surface, Scenario, Tier, Depth, and action taxonomy;
- did not add framework-specific component maps, fixed browser or MCP commands, an AI-style blacklist, or mandatory generated prototypes;
- preserved the installed local opt-in policy file as a local-only customization;
- did not run model, prompt-behavior, or forward tests, following the user's instruction.

Publication:

- Reviewed the final routing and handoff diff without running prompt or model tests.
- Backed up the installed skill to `C:\Users\40218\.codex\skill-backups\grill-me-for-ui-20260830T010028+0800`.
- Synchronized all 17 repository skill files to the installed copy; SHA-256 comparison found no mismatches.
- Preserved the local-only `agents/openai.yaml` opt-in policy file.
- Published and squash-merged through pull request #6. The resulting main-branch commit is `1de61f4d6407151506b0be51a2ea5f86bb847610`.

## 2026-08-30 — Routing lifecycle consolidation

Goal: resolve lifecycle ambiguity introduced by Interaction / IA and Visual Probe while preserving the existing architecture and action taxonomy.

Changes:

- separated main design stages from the Interaction / IA conditional stage, Visual Probe evidence insertion, Task Walkthrough verification substep, and persistent delivery templates;
- added a stage contract that records the direct caller, return point, and compact write-back location for Interaction / IA and Visual Probe;
- constrained Visual Probe to unresolved design decisions and excluded direct calls from verify, audit, document, and delivery;
- limited cross-stage carry-over to compact Cards and decision records instead of full exploration histories or reloaded completed references;
- updated the medical research Dashboard example to route through object, action, context, permission, state, and recovery questions before choosing Tabs, Drawer, or other component forms.

Scope decisions:

- did not add a new Playbook, action, code or static-audit path, Design-to-Code path, or compressed master template;
- did not change the installed skill copy; GitHub publication and merge were authorized after the local iteration review;
- did not run model, prompt-behavior, forward, or wording-match tests, following the user's instruction.

Review:

- reviewed the Markdown diff for routing consistency, return paths, and scope boundaries;
- recorded installed-copy synchronization as not performed; GitHub publication details are reported in the task handoff.
