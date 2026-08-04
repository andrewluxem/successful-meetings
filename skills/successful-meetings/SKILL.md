---
name: successful-meetings
description: Turn meetings into decisions and owned follow-ups. Use this skill whenever the user wants to plan or prep a meeting, write a meeting agenda, decide whether something should be a meeting or an email, pick or trim an attendee list, timebox a discussion, generate discussion questions, turn raw meeting notes or a transcript into a recap with decisions and action items, or audit recurring meetings to cut or fix them. Trigger on phrases like prep this meeting, write an agenda, should this be a meeting, meeting recap, follow-up notes, meeting minutes, too many meetings, this standing meeting feels useless. Even if the user only asks for an agenda, use this skill so the agenda gets an owner, an objective, a timebox, and pre-reads. Produces three artifacts, a Meeting Packet, a Follow-Up Note with every action item owned and dated, and a Meeting Audit with keep, fix, shrink, or kill verdicts.
license: MIT. See LICENSE.md.
---

# Successful Meetings

Andy Grove called meetings "the medium through which managerial work is performed" (High Output Management). Treat them that way: a meeting is work product with a real cost, not calendar filler. This skill executes the Successful Meetings playbook from andrewluxem.com. It produces prep packets, follow-up notes, and meeting audits. It does not summarize meeting philosophy back at the user.

## Artifacts

| Mode | Input | Output |
|------|-------|--------|
| A. Prep | Purpose, context, candidate attendees | Meeting Packet |
| B. Recap | Raw notes, bullets, or a transcript | Follow-Up Note |
| C. Audit | A recurring meeting, or a list of them | Meeting Audit |

Pick the mode from what the user asked for. If the request spans two (prep now, recap later), do the one that is actionable today and mention the other is available.

## Related skills

If these skills are installed, hand off rather than duplicate: `3ps-framework` for weekly status updates, `silent-meetings` for read-first meeting format, `4-blocker-business-reviews` for executive reviews, `weekly-schedule-of-meetings` for designing a team's full meeting calendar. If they are not installed, cover the need with this skill's general procedure and keep going. `3ps-framework` sets `disable-model-invocation`, so it will not pick itself up: tell the user to name it, as in use the 3ps-framework skill, rather than handing off to it silently.

## Inputs and assumptions

Ask at most one round of clarifying questions, and only for inputs that change the artifact: the decision or outcome sought, who is in the room, the time slot. For everything else make a sensible assumption and label it in the artifact so the user can correct it in one pass. A packet with two labeled assumptions beats two rounds of questions.

## Mode A: Meeting Packet

1. **Justify the meeting.** Name the outcome: a decision to make, a plan to align on, a problem to work. If no outcome can be named, say so plainly and draft the email or doc that replaces the meeting. That counts as success for this skill, not failure.
2. **Classify it.** Process-oriented (recurring alignment: 1:1s, staff meetings, operating reviews) or mission-oriented (one-time: decide, plan, brainstorm). Read `references/meeting-types.md` if classification is unclear. Classification sets prep depth: mission-oriented meetings get pre-reads and a decision protocol; process-oriented meetings get a stable standing structure.
3. **Curate attendees.** Every name gets a role: Owner (runs it), Decider, or Contributor (has input the room needs). People who only need to know the outcome are Informed: they get the follow-up note, not an invite. If the list exceeds 8, propose a cut and say why.
4. **Timebox it.** Default to half the time the user assumed. Work expands to fill the container, so shrink the container. Never propose more time than the user offered. Allocate minutes per agenda item and reserve the final 5 for decisions, owners, and dates.
5. **Build the agenda** using `assets/agenda-template.md`. One-sentence objective at the top. List materials to be shared in advance, and include a "send by" line at least 24 hours before the meeting so pre-reads actually happen.
6. **Attach 3 to 5 discussion questions** tailored to the topic, drawn from `references/question-bank.md`. Match the interrogative to the meeting's job: Why and What for decisions, How and When for planning, Who for accountability.

Output: one Meeting Packet in the agenda template's structure, ready to paste into the invite. No motivational framing.

## Mode B: Follow-Up Note

1. Ingest whatever exists: typed notes, a transcript, a memory dump. Messy input is the normal case.
2. Sort the signal into four buckets using `assets/follow-up-template.md`: Decisions, Summary (3 sentences maximum), Action items, Learnings.
3. Every action item carries an owner and a due date. If the notes do not name one, write "Owner needed" or "Date needed" and surface those gaps at the top of the note so the sender resolves them before hitting send. Never silently drop an unowned action; unowned actions are how meeting output evaporates.
4. Write decisions as decisions ("We will X"), not as topics that were discussed.
5. Head the note with the meeting name and date. Remind the user it should go out within 24 hours, because the note's value decays fast.

Output: one Follow-Up Note ready to send, plus a gaps list if owners or dates are missing.

## Mode C: Meeting Audit

1. Gather the inventory: each meeting's cadence, length, attendee count, and what it actually produces.
2. Score each against the four tenets using `assets/audit-scorecard.md`:
   - **Owned and purposeful**: it has an owner, an objective, and an agenda shipped in advance
   - **Right sized**: attendee count matches the outcome, no audience members
   - **Participatory**: people contribute and debate; it is not a status readout a doc could carry
   - **Decisive**: it ends in decisions and owned actions, and prior actions get checked
3. Verdict per meeting: Keep, Fix (name the one change), Shrink (time or attendees), Make async (becomes a doc, a status update, or an email), or Kill.
4. Quantify the recovery: hours per week returned to the team if the verdicts are applied. Hours are what make the audit land.

Output: the scorecard table plus a one-paragraph recommendation. If the user wants to redesign the whole weekly calendar from scratch, that is the `weekly-schedule-of-meetings` playbook; audit first, redesign second.

## Guardrails

- No agenda without a stated objective. An agenda without an objective is decoration.
- No action item without an owner and a date, even in drafts. Placeholders are visible, never silent.
- Do not add attendees, agenda items, or minutes to fill space. Shorter is the feature.
- Write artifacts in plain language and plain punctuation: no em dashes, no motivational filler. These are working documents someone will paste into an invite or an email.
- Keep quotes and claims checkable. The references carry only attributable material; do not invent meeting-productivity statistics to make a point.

## Worked example, condensed

Request: "Prep a 60-minute strategic review of the new plan with me, Katy, and Cindy, plus whoever else should be there."

Packet highlights: outcome named (approve the plan or send it back with owned revisions), mission-oriented, attendees stay at three with roles assigned (nobody joins as "whoever else" without a role), timebox cut to 30 minutes, plan doc and deck shipped 24 hours ahead, questions selected: What is the worst case if we ship this? Why now? How will we measure success? Final 5 minutes reserved for decisions, owners, and dates.

## References

- `references/meeting-types.md`: taxonomy and prep depth. Read when classification is unclear.
- `references/pitfalls.md`: failure modes and counter-strategies. Read for audits, or when the user asks why a practice matters.
- `references/question-bank.md`: the full Who, What, Where, When, Why, How bank. Read in Mode A step 6.
- `references/culture-rollout.md`: the 6-step adoption plan. Read when the user wants to change team behavior, not just fix one meeting.
