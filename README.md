# locqa plugins

Agent plugin for [locqa](https://pypi.org/project/locqa/), a CLI that checks
Flutter ARB localization files: untranslated or copied-from-source strings,
broken `{placeholders}` and ICU plurals, glossary violations, overlong UI
labels, text in the wrong language, Kazakh orthography and suffix-after-placeholder
errors. Structural checks work for any locale; the deepest language rules are
for Kazakh and Uzbek.

The plugin ships one skill that teaches a coding agent when and how to run
`locqa`. Fixes stay human-approved: the agent proposes, a person decides.

## Install

**Claude Code**

```
/plugin marketplace add BEknUur/locqa-plugins
/plugin install locqa@locqa-plugins
```

**Codex**

```
codex plugin marketplace add BEknUur/locqa-plugins
```

Then run `/plugins` in Codex, install **locqa**, and start a new session.

**Requirement:** [uv](https://docs.astral.sh/uv/) on PATH. The skill runs
`uvx locqa@0.4.0`, so nothing else needs installing. Corrected-ARB export also
needs a Flutter SDK.

## Use

Ask the agent, for example:

- "Check the Kazakh translation against the Russian ARB."
- "Find broken placeholders in our Flutter translations."
- "Review `lib/l10n/app_uz.arb` before I merge."

Claude Code also exposes the skill as `/locqa:locqa`; Codex as `$locqa`.

## Layout

```
.claude-plugin/marketplace.json     Claude Code marketplace
.agents/plugins/marketplace.json    Codex marketplace
plugins/locqa/
  .claude-plugin/plugin.json        Claude Code manifest
  .codex-plugin/plugin.json         Codex manifest
  plugin.json                       portable manifest (agent-plugins.org)
  skills/locqa/SKILL.md             the skill, shared by both
```

## License

MIT
