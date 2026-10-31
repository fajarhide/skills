---
name: ui-direction
description: Use when building a new web page or giving one a look of its own, when a page reads as templated, generic or AI-made, or when writing a DESIGN.md.
---
# UI direction

Use this when building a new page, or when asked to make one look better and the project has no design system that already decides. 

Models reach for the category default: asked for a coffee site, they produce cream, terracotta and a serif. This pass makes each visual decision answer to something true about this subject.

## 1. Name the mode

Pick from the surface, not the company. A tool's landing page is Persuade, and its settings screen is Operate.

| Mode | Success is | Ambition shows as |
| --- | --- | --- |
| Persuade | The visitor decides and acts | A clear idea, scale, one dominant thing per screen |
| Operate | The person finishes a task | Density, scanability, familiar patterns, exact states |
| Read | The reader understands | Structure, line length, navigation |
| Experience | The visitor is inside the work | The work leads and the interface recedes |

For Operate, skip steps 3 and 4 and use the work itself as the idea:

- The first line on the screen names what needs doing now, with the count and a button for the next action. "3 shifts have no vet. Fill the next one."
- Sample data puts the hard cases in the first view: gaps, conflicts, overdue items. A screen that opens on "all clear" shows nothing of the job.
- Every item states its consequence next to its action, such as "approving this leaves Monday with no nurse".
- A phone gets its own layout built around the next task, such as one day at a time, and never a squeezed table or one long list.
- Familiar controls and one typeface. Spend the character on the shape of the work.

## 2. Inventory the subject

Write 8 to 12 facts that belong to this subject and to no competitor, from the brief, the repo and the live product: its name and what it means, place, numbers, the constraint it lives with, materials, rituals and hours, the printed things of its world, what it outputs, how the person using it actually works.

Mark what really exists: photographs, screenshots, a logo. Plan only around those. Customers, quotes, logos and statistics that do not exist stay off the page, and sample details get listed for the owner to confirm.

## 3. List seven worlds

Name the mechanism in one sentence: what this does that makes it this product. Write down the page this category always ships and its predictable opposite. Both are out.

Then list seven things the audience already knows by heart, from the inventory and the world around it: artifacts, places, rituals, printed forms, instruments. For each, one line on how it could carry the mechanism and one on how it looks, its ground, type and main shape. A roastery could use a survey map of the farm, a roast log, a bag label. A changelog tool could use a carbon-copy form, a proof sheet, a stamped approval.

Cross out any that are decoration only, or that imply something untrue. At least three must remain, so add more if needed.

## 4. Roll, then commit

You will rank the safest one first, so do not rank them. Number the survivors and roll:

```sh
python -c "import random; print(random.randint(1, N))"
```

Build the world it lands on. Roll again only for a reason you can state: it would mislead, contradict a brand constraint, or cannot hold the real content.

Complete this sentence:

> On this page, **[the world]** becomes **[what the page does with it]**, so **[what the visitor understands at once]**.

Test it. Put the nearest competitor's name in it: if it still works, it is too general, so tie it to an inventory fact. Then ask what someone would remember a day after one look at the first screen. The answer should be that world, shown at full size as the page itself, never as a picture inside a standard hero. Carry its ground, type and shapes into every section, down to the footer.

If a safer choice tempts you, keep the world. Readability, contrast and the order path stay untouched.

## 5. Write DESIGN.md

Put it in the project root. An existing one decides, so skip steps 3 and 4 and follow it. Light or dark comes from where the person uses this.

```md
---
name: <product>
colors:
  ground: "#..."
  ink: "#..."
  accent: "#..."
typography:
  display: { fontFamily: <family>, fontSize: <size> }
  body: { fontFamily: <family>, fontSize: <size> }
rounded: { md: <size> }
spacing: { sm: <size>, md: <size>, lg: <size> }
---

## Overview
Mode. The world and the sentence from step 4. Density, motion and variance, each low, medium or high, with the reason.

## Colors and type
Where each came from in that world. A display face needs character of its own, so load one rather than a system font.

## Do not
Three to five looks this product must avoid, specific to it, with the reason.
```

If `npx` is available, validate it with `npx @google/design.md lint DESIGN.md`.

## 6. Build in this order

1. The words, complete: every section delivers its real content. List each section as a claim with its proof, and delete a section that has no claim.
2. Tokens from DESIGN.md, then the first screen at phone and desktop width. It demonstrates the world and the mechanism, and its title says plainly what this is.
3. Each section, carrying the idea through pricing, FAQ and footer. Neighbours differ in layout.
4. Space left by removing ornament goes to scale, content or a real picture, never to another ornament.
5. Motion last, and only where it explains something. The page must work without it.

## 7. Prove it

```sh
python scripts/probe.py OUT_DIR URL --design DESIGN.md
```

Open every screenshot and judge the pictures, not your code:

- **One second:** what did you see? "A website" means there is no focal point.
- **Five seconds:** what is this, who is it for, what do I do next?
- **Cover the name:** could a competitor use this page unchanged?
- **One day later:** what would you remember?
- **Follow the edges:** text left edges should be few and reused.

Fix the worst three things, then probe and look again, two rounds at most. Force the cases below, since a handsome page can still lose the order. Report the idea sentence, the numbers, what is sample content, and both screenshots. Whether it looks better is the owner's call.

## Force what a happy path never shows

On each primary action: double-click submit, bad input, reload after acting, an empty state, a 200 character string, Tab then Escape in any dialog. Say which you did not try.
