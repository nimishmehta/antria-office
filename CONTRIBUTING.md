# Contributing

Thanks for taking an interest. This plugin is small on purpose — 20 agent files and 3 skills, no runtime, no build step. That makes it easy to contribute to and easy to review.

## Ground rules

**Prompts are the product.** Every file here is Markdown that a model reads. A change to wording *is* a functional change, so describe the behaviour you are trying to alter, not just the text you edited.

**Keep the roster stable.** Role keys are part of the public interface — `antria-office:copywriter` appears in user prompts and in other people's workflows. Renaming or removing a role is a breaking change.

**Prefer sharpening over adding.** A new role has to earn its place against the option of making an existing one better. Twenty is already a lot for a lead to choose between.

## Making a change

1. Fork and branch.
2. Edit the relevant `agents/*.md` or `skills/*/SKILL.md`.
3. Validate the structure:
   ```bash
   claude plugin validate ./.claude-plugin/plugin.json
   ```
4. Install your branch locally and actually run it:
   ```bash
   /plugin marketplace add /path/to/your/checkout
   /plugin install antria-office@antria-office
   ```
5. Open a pull request describing the behaviour change and what you observed before and after.

## What a good change looks like

Agent `description` fields are how the lead decides who to staff, and in Cowork they are also how a skill gets triggered at all. If you are editing one, say in the PR which phrasings should now route differently.

Bug reports are most useful when they include the prompt you gave, the roles that got staffed, and the roles you expected.

## Code of conduct

Be decent. Assume good faith. Disagree about the work, not the person.
