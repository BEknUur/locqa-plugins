# locqa plugin

Teaches a coding agent to quality-check Flutter ARB localization files with the
[locqa](https://pypi.org/project/locqa/) CLI: untranslated or copied strings,
broken placeholders and ICU plurals, glossary and length problems, wrong-language
text, and Kazakh orthography and suffix errors. The agent runs `uvx locqa@0.4.0`,
summarizes `report.json`, and proposes fixes; a human approves every wording change.

Requirement: [uv](https://docs.astral.sh/uv/) on PATH. Export of a corrected ARB
also needs a Flutter SDK. Ask: "Check the Kazakh ARB against the Russian source."

Install: `/plugin marketplace add BEknUur/locqa-plugins`, then `/plugin install locqa@locqa-plugins`.
