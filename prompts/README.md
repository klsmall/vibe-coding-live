# Workshop Prompts

These prompts guide the AI-assisted development workflow for the **Vibe Coding Live** workshop's Sales Call Note Builder Prototype.

Use them in order. Each prompt builds on the work completed by the previous one.

## How to use the prompts

1. Open the prompt you need from the list below.
2. Select the **Copy raw file** button in the upper-right corner of the file preview.
3. Paste the prompt into your AI coding environment.
4. Review the agent's plan, commands, and changes carefully before approving them.

> [!IMPORTANT]
> Prompt 1 refers to `sales_call_note_builder_prototype_requirements.md`. Make sure that requirements file is available to your AI coding agent before submitting the prompt.

## Prompt files

1. [Plan the Sales Call Note Builder Prototype](./prompt_1.txt) — inspect the Salesforce DX project, account for the required custom field, and produce an implementation plan without editing files.
2. [Create permissions and deploy](./prompt_2.txt) — create the targeted permission set, validate and deploy the required metadata, and assign access to the authenticated workshop user.
3. [Make questions configurable](./prompt_3.txt) — replace hard-coded questions with Lightning App Builder properties while preserving the existing component behavior.