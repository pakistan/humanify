# humanify

`SKILL.md` is a skill for Claude that replaces "make this better" with four
specific reads of a draft. Each pass asks one checkable question — how long are
the sentences, which words survive deletion, which phrases arrived
pre-assembled, which sentences claim a quality instead of showing it. A
question with an answer can be acted on. "Is this good?" returns the same
verdict that produced the draft.

## The four passes

1. **The audit.** Count sentence lengths, sentence openings, "to be" verbs,
   subject-to-verb distance, abstract nouns, and repeated parallel structures.
   The numbers are comparative, so they resist flattery.
2. **The strip test.** Delete every sentence-initial connective, the opener
   that clears its throat, the conclusion that restates, and every sentence
   whose subject is another sentence. Restore only what the prose fails
   without. Expect to restore almost nothing.
3. **The volunteer-sentence pass.** Find the phrasings that would occur to
   anyone writing on the topic, and rewrite them from the thought rather than
   from the words already sitting on the page.
4. **The enactment check.** Cut the sentence that announces its own
   importance, empathy, or authority, and let the sentence it was propping up
   carry the weight.

Run them in order, one read each. Merged into a single sweep they collapse back
into "is this good?"

## Scope

Use it on prose meant to be read as prose: essays, articles, posts, docs
written in paragraphs, an email that matters. Skip it on runbooks,
step-by-step instructions, and API reference, where the signposting and
connectives it strips out are what make the page usable.

## Install

Copy `SKILL.md` into a directory Claude reads skills from.

Personal, available in every session:

```bash
mkdir -p ~/.claude/skills/humanify
curl -o ~/.claude/skills/humanify/SKILL.md \
  https://raw.githubusercontent.com/pakistan/humanify/main/SKILL.md
```

Per project, checked in alongside the code:

```bash
mkdir -p .claude/skills/humanify
curl -o .claude/skills/humanify/SKILL.md \
  https://raw.githubusercontent.com/pakistan/humanify/main/SKILL.md
```

Start a new session to pick it up.

## Use

Claude loads the skill on its own when a task is prose revision. To reach for
it directly:

```
/humanify
```

Or just say so: "run the humanify passes over this draft."

## License

MIT — see [LICENSE](LICENSE).
