# successful-meetings

A small, static agent skill that turns a meeting into a decision and a set of owned follow-ups. Ask it for one thing and it hands back a working document, not advice about meetings.

Three artifacts:

- **Meeting Packet**: the agenda you paste into the invite. Objective in one sentence, every attendee carrying a role, a timebox half the size you assumed, pre-reads with a send-by date, and 3 to 5 questions matched to the meeting's job.
- **Follow-Up Note**: decisions written as decisions, a three sentence summary, and action items where every single one has an owner and a due date. Missing owners get surfaced at the top as gaps, never dropped quietly.
- **Meeting Audit**: your recurring meetings scored against four tenets, each with a verdict (keep, fix, shrink, make async, or kill) and the hours per week you get back if you apply them.

It executes the [Successful Meetings playbook](https://andrewluxem.com/playbooks/successful-meetings) from andrewluxem.com. The playbook page teaches the framework. This skill runs it.

**Explicit invocation only: no self-firing, no remote fetch, no auto-update.** It makes no network calls, reads nothing outside its own folder, never edits your global agent config, and never updates itself in place. The whole thing is one `SKILL.md` you can read in five minutes, plus templates and reference files it loads only when a step needs them.

## The loop

Pick the mode from what you asked for. If a request spans two, the skill does the one that is actionable today and tells you the other exists.

| Mode | You bring | You get |
|---|---|---|
| **A. Prep** | The purpose, the context, who might attend | Meeting Packet |
| **B. Recap** | Raw notes, bullets, or a transcript | Follow-Up Note |
| **C. Audit** | A recurring meeting, or a list of them | Meeting Audit |

Mode C scores against the four tenets, which are also the standard the other two modes build toward:

1. **Owned and purposeful.** It has an owner, an objective, and an agenda that shipped in advance.
2. **Right sized.** Attendee count matches the outcome. No audience members.
3. **Participatory.** People contribute and debate. It is not a status readout a doc could carry.
4. **Decisive.** It ends in decisions and owned actions, and prior actions get checked.

What it refuses to shortcut, because these are the failure modes that make meetings evaporate:

- No agenda without a stated objective. An agenda without an objective is decoration.
- No action item without an owner and a date, even in a draft. Placeholders are visible, never silent.
- No attendees, agenda items, or minutes added to fill space. Shorter is the feature.
- No invented productivity statistics. Quotes and claims stay checkable.

If it cannot name what the meeting produces, it says so and drafts the email or doc that replaces the meeting. That is a successful run, not a failed one.

See [`examples/example-run.md`](examples/example-run.md) for a full Mode A pass, from a vague 60 minute request to a 30 minute packet.

## Install

**Manual (recommended, clone and copy):**

```bash
git clone https://github.com/andrewluxem/successful-meetings.git
cp -r successful-meetings/skills/successful-meetings ~/.claude/skills/
```

Then invoke it explicitly: `use the successful-meetings skill to prep this meeting`.

**As a Claude Code plugin (version-pinned, no auto-update):**

```
/plugin marketplace add andrewluxem/successful-meetings
/plugin install successful-meetings@successful-meetings
```

`plugin.json` carries an explicit `version`. Installing pins that version. It does not silently pull new commits. Taking an update means bumping the version and reinstalling, so the update is a decision rather than a background event.

**As a zip:** the packaged skill is on the playbook page at [andrewluxem.com/playbooks/successful-meetings](https://andrewluxem.com/playbooks/successful-meetings), for platforms that want a folder upload instead of a clone. Same files.

Portable by design: it is plain Markdown with no runtime, so it works anywhere a folder of skill files works.

## Usage

```
Prep a 45 minute decision meeting on the Q4 loyalty relaunch with growth and engineering
Turn these raw notes into a recap with action items
Audit my team's recurring meetings, here is the list
```

Naming the skill is the reliable path: `use the successful-meetings skill to prep this meeting`. It has no background behavior and nothing scheduled, so nothing happens until a request goes to it.

## Iterating

The skill is the folder [`skills/successful-meetings/`](skills/successful-meetings/):

- `SKILL.md` is the procedure, and it is the only file loaded every time.
- `references/` is the depth: meeting taxonomy, the question bank, the four pitfalls, and the culture rollout. Each one is read only at the step that needs it.
- `assets/` holds the three templates the artifacts are built from. The agenda and the follow-up note each carry a filled example under the blank one.
- `meta.yaml` carries the version, the invocation examples, and the changelog.

Edit it, invoke it on a meeting that is actually on your calendar, and see whether the artifact earns its place. The bar is that the output would have taken you an afternoon to build by hand.

When you change behavior meaningfully, bump `version` in both `.claude-plugin/plugin.json` and `meta.yaml` so plugin installs pick it up deliberately, and add the changelog line.

## License

MIT, see [`LICENSE`](LICENSE). The skill folder carries the same MIT text in [`skills/successful-meetings/LICENSE.md`](skills/successful-meetings/LICENSE.md), so the whole repo is one license.

The Grove quote is from *High Output Management*. Parkinson's Law, Drucker, and Vanderkam are attributed where they are used in [`references/pitfalls.md`](skills/successful-meetings/references/pitfalls.md).
