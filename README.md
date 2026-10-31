# fajarhide/skills

Agent skills, published so they can be installed by name:

```sh
npx skills add fajarhide/skills
npx skills add fajarhide/skills --skill omni
```

| skill | what it is for | source |
| --- | --- | --- |
| [`omni`](skills/omni/SKILL.md) | Installing, verifying and reading the markers of [OMNI](https://github.com/fajarhide/omni), a local hook that shortens shell output before the model reads it | [fajarhide/omni](https://github.com/fajarhide/omni/blob/main/plugins/claude-code/skills/omni/SKILL.md) |
| [`ui-receipts`](skills/ui-receipts/README.md) | Auditing the UI and UX of a web app in a real browser, where every finding carries a receipt, and proving a UI change before calling it done | this repository |

## Where to edit

A skill that documents one project is pulled from that project by
`.github/workflows/sync.yml`, which runs daily and can be triggered by hand. It
lives next to the code it documents, because that is the only arrangement where
the two cannot drift apart. An edit made here is an edit the next sync deletes, so
change the source. The table above links each one.

A skill with no project of its own, marked "this repository" in the table, is
edited here. The sync does not touch it.

## Licence

Apache 2.0, the same as the projects the skills are pulled from. See `LICENSE`.
