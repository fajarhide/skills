# fajarhide/skills

Skills for AI coding agents that work on web interfaces. One builds a page with a look of its own, and the other opens a page in a real browser and tries to break it. Both were tested with blind evals, and each README publishes the rounds it lost as well as the ones it won.

| Skill | Use it when | You get back | skills.sh |
| --- | --- | --- | --- |
| [`ui-direction`](skills/ui-direction/README.md) | You are building a new page or a page looks generic | The page, plus a `DESIGN.md` that records why it looks the way it does | [![ui-direction installs on skills.sh](https://img.shields.io/badge/dynamic/regex?url=https%3A%2F%2Fwww.skills.sh%2Ffajarhide%2Fskills%2Fui-direction&search=Installs%3C%5C%2F%5Ba-z%5D%2B%3E%5Cs%2A%28%3F%3A%3C%5B%5E%3E%5D%2B%3E%5Cs%2A%29%2A%28%5B0-9.%2CKM%E2%80%93-%5D%2B%29&replace=%241&label=installs)](https://www.skills.sh/fajarhide/skills/ui-direction) |
| [`ui-receipts`](skills/ui-receipts/README.md) | A page exists and you want to know what is wrong with it | Up to ten ranked findings, each with the action, number or labelled judgment behind it | [![ui-receipts installs on skills.sh](https://img.shields.io/badge/dynamic/regex?url=https%3A%2F%2Fwww.skills.sh%2Ffajarhide%2Fskills%2Fui-receipts&search=Installs%3C%5C%2F%5Ba-z%5D%2B%3E%5Cs%2A%28%3F%3A%3C%5B%5E%3E%5D%2B%3E%5Cs%2A%29%2A%28%5B0-9.%2CKM%E2%80%93-%5D%2B%29&replace=%241&label=installs)](https://www.skills.sh/fajarhide/skills/ui-receipts) |

## Install

```sh
# Both skills, for your user
npx skills add fajarhide/skills -g

# Or one of them
npx skills add fajarhide/skills --skill ui-direction -g
npx skills add fajarhide/skills --skill ui-receipts -g

# Both skills measure pages in a browser
pip install playwright && playwright install chromium
```

Without `-g`, a skill lands inside whichever project you ran the command from.

The install counts are read live from each skill's skills.sh page. A skill shows a dash until its first counted install, and skills.sh only counts installs made through the CLI.

## Using them

Ask your agent in plain words:

```
Build a landing page for our letterpress shop
This page looks AI generated, give it its own look
Audit the UI and UX of http://localhost:3000
Why does this checkout feel off?
```

To use both, build with `ui-direction`, then audit the result with `ui-receipts`. We tested each skill alone and have not measured the pair together.

## ui-direction

Asked for a coffee site, agents produce cream, terracotta and a serif. This skill has the agent list what only this subject has, name seven worlds its audience knows by heart, and roll a die, because a model left to choose picks the safest one.

Screens people work in skip the die. The first line names what needs doing now, with a button, and the sample data opens on the hard cases.

Final test round, scored from anonymous screenshots:

| Mean over 4 judgments | ui-direction | A popular design skill | No skill |
| --- | --- | --- | --- |
| Overall score, of 10 | **8.32** | 7.55 | 5.60 |
| Marked as generic AI output | **0 of 4** | **0 of 4** | 4 of 4 |
| Tokens per build | 93k | 132k | **70k** |

Nearly the same text scored 6.50 when it lived inside `ui-receipts`, and we cannot say why it moved. The sample is four briefs, and the judges were models. [Every round and its limits](skills/ui-direction/README.md#how-it-was-measured).

## ui-receipts

Most agents review UI by reading code, and guess at how the page behaves. This skill has the agent drive the page and force what a happy path never shows: double submits, failed requests, empty states, long text, reloads and keyboard use.

Test site with 18 seeded defects and 4 decoys, things that look wrong but are fine:

| Mean per run | ui-receipts (9 runs) | No skill (6 runs) |
| --- | --- | --- |
| Defects found, of 18 | **13.9** (range 9 to 17) | 10.3 (range 7 to 13) |
| Decoys reported as defects, of 4 | **0.3** | 3.2 |
| Factual claims the source contradicts | **1.1** | 2.3 |

Runs vary a lot, so run it twice on anything important. The author wrote the test site and its answer key. [Before and after screenshots and the full results](skills/ui-receipts/README.md).

## Why two skills

They began as one. With the build instructions inside the audit skill, a blind audit fell from 12.0 to 10.3 defects found, in three runs each. Splitting them keeps the audit as it was and loads the build instructions only when you are building.

## Licence

Apache 2.0. See `LICENSE`.
