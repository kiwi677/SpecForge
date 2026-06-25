---
name: specforge
description: Turn product requirements, vague PRD fragments, Chinese requirement notes, or digital-human requests into project-aware研发方案 with a rendered local HTML preview. Use when the user asks to generate, refine, or preview a需求方案; mentions SpecForge; provides requirements for OREF, AI平台, 数据集, DP/BI, DataAgent, log-search/log-query, 苏州大数据局; or asks for visual prototypes, frontend/backend/ops/risk/schedule breakdowns.
---

# SpecForge

Use SpecForge to convert a user requirement into a project-aware, review-ready研发方案 with a visual HTML preview page.

## Core Workflow

1. Read `references/project-overview.md` to identify the project and confidence.
2. Read the matching file in `references/project/`.
3. Classify the requirement type and read the relevant playbooks:
   - Frontend interaction: `references/playbooks/frontend-interaction.md`
   - Admin console: `references/playbooks/admin-console.md`
   - Model/data/task flow: `references/playbooks/model-data-taskflow.md`
   - Permission/approval: `references/playbooks/permission-approval.md`
   - Ops/deployment: `references/playbooks/ops-deployment.md`
4. If a historical example matches, read the relevant file in `references/examples/`.
5. Use `references/templates/acceptance-checklist.md` as the quality gate before finalizing.
6. Generate one complete offline `.html` preview file under the workspace, preferably `SpecForge/outputs/YYYY-MM-DD_<project>_<topic>_plan.html` when that folder exists.
7. Open or provide the local preview URL/path. The user must see the rendered page, not HTML source.

## Output Contract

Always return exactly these two high-level parts:

1. `需求提要`: 3-5 Chinese sentences explaining the problem, target users, usage scenario, expected result, and key assumptions.
2. `方案预览窗口`: the rendered `.html` preview file or link. Do not paste the HTML source into the answer.

The preview page may include these sections, in this order, omitting empty sections:

- 需求摘要
- 问题
- 方案的主要流程/步骤
- 原型图片
- 前端事项
- 后端事项
- 运维事项
- 前期准备事项
- 风险评估
- 排期

## Project Handling

- High confidence: read the project file and generate the plan.
- Medium confidence: generate using the most likely project and put the uncertainty in `问题`.
- Low confidence: ask the user to confirm the project before generating.
- New project: ask for project basics, create a project file from `references/templates/project-template.md`, update the project overview, then generate.
- Never store or output plaintext passwords, tokens, SSH passwords, or production credentials. Use `见密码管理器/联系负责人`.

## Prototype Rules

- Include `原型图片` whenever the requirement changes pages, entry points, interaction, edit/config state, modal/drawer behavior, dashboards, charts, lists, or forms.
- Use one or more low-fidelity visual prototypes drawn in HTML/CSS inside the preview page.
- Each prototype needs a short title and scenario description.
- Prototypes must show necessary business details: selected tabs, table column names, form field names, buttons, status labels, key actions, filters, and error/empty states.
- Desktop layouts must show at most two prototype cards per row.
- When page width is `<= 800px`, prototype cards must be one per row.
- Do not use vague gray blocks without business labels.

## HTML Requirements

- Create a full file with `<!doctype html>`, `html`, `head`, and `body`.
- Use inline CSS and optional lightweight inline JS only.
- Do not depend on external CSS, JS, fonts, or network images.
- Keep the page clear, compact, review-friendly, and usable offline.
- If there is already a local static server for the workspace, use its URL. Otherwise the HTML file path is acceptable, or start a local server when appropriate.

## Validation

Before final response:

- Check the file exists.
- Validate basic HTML syntax when possible, for example `python3 -m html.parser <file>`.
- Check the rendered page or local HTTP endpoint when a browser/server is available.
- Search the output for key requirement terms to ensure they appear in the plan.

## Useful References

- Main digital-human specification: `references/specforge.md`
- Project routing: `references/project-overview.md`
- HTML template: `assets/html-preview-template.html`
- Prototype guidance: `references/templates/prototype-template.md`
- Quality gate: `references/templates/acceptance-checklist.md`
