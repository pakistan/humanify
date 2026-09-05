# humanify

`SKILL.md` is a writing skill that replaces "make this better" with four
specific reads of a draft. Each pass asks one checkable question: how long are
the sentences, which words survive deletion, which phrases arrived
pre-assembled, which sentences claim a quality instead of showing it. A
question with an answer can be acted on. "Is this good?" returns the same
verdict that produced the draft.

The file is plain Markdown with a name and a description at the top, so any
assistant that loads skills from disk can pick it up, and anyone who would
rather run the passes by hand can just read it.

## The four passes

1. **The audit.** Count sentence lengths, sentence openings, "to be" verbs,
   subject-to-verb distance, abstract nouns, and repeated parallel structures.
   The numbers are comparative, so they resist flattery.
2. **The strip test.** Delete every sentence-initial connective, every em dash,
   the opener that clears its throat, the conclusion that restates, and every
   sentence whose subject is another sentence. Restore only what the prose
   fails without. Expect to restore almost nothing.
3. **The volunteer-sentence pass.** Find the phrasings that would occur to
   anyone writing on the topic, and rewrite them from the thought rather than
   from the words already sitting on the page.
4. **The enactment check.** Cut the sentence that announces its own
   importance, empathy, or authority, and let the sentence it was propping up
   carry the weight.

Run them in order, one read each. Merged into a single sweep they collapse
back into "is this good?"

## Why the em dash gets cut

Pass 2 deletes them on sight, which is a rule about frequency rather than
about grammar. Language models reach for the em dash far more often than human
writers do, so a draft dotted with them announces how it was written, and the
same interrupted rhythm repeats down the page. Almost every one of them wants
to be a comma, a colon, a semicolon, or a full stop instead. The few that
survive the strip test are the ones the sentence genuinely needed.

## Scope

Use it on prose meant to be read as prose: essays, articles, posts, docs
written in paragraphs, an email that matters. Skip it on runbooks,
step-by-step instructions, and API reference, where the signposting and
connectives it strips out are what make the page usable.

## Install

Download the file:

```bash
curl -O https://raw.githubusercontent.com/pakistan/humanify/main/SKILL.md
```

Then put it where your assistant looks for skills, one directory per skill:

```
<skills-directory>/humanify/SKILL.md
```

Most tools read a user-level skills directory, for skills available in every
session, and a project-level one for skills checked in alongside the code.
Start a new session to pick it up.

## Use

An assistant that loads skills on its own will reach for this one when the
task is prose revision. To invoke it directly:

```
/humanify
```

Or just say so: "run the humanify passes over this draft."

## License

MIT, see [LICENSE](LICENSE).
