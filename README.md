# fajarhide/skills

Agent skills, published so they can be installed by name:

```sh
npx skills add fajarhide/skills
npx skills add fajarhide/skills --skill omni
```

| skill | what it is for | source |
| --- | --- | --- |
| [`omni`](skills/omni/SKILL.md) | Installing, verifying and reading the markers of [OMNI](https://github.com/fajarhide/omni), a local hook that shortens shell output before the model reads it | [fajarhide/omni](https://github.com/fajarhide/omni/blob/main/plugins/claude-code/skills/omni/SKILL.md) |

## Nothing here is edited here

Every file under `skills/` is pulled from the repository that owns it by
`.github/workflows/sync.yml`, which runs daily and can be triggered by hand. A
skill lives next to the code it documents, because that is the only arrangement
where the two cannot drift apart.

So an edit made here is an edit the next sync deletes. Change the source instead.
The table above links each one.

## Licence

Apache 2.0, the same as the projects the skills are pulled from. See `LICENSE`.
