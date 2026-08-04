# Example run

A full Mode A pass on a real-shaped request. This is what the skill produces when invoked.
Names and numbers are illustrative.

---

**Invocation:**

> Use the successful-meetings skill to prep this meeting. We need to decide whether to
> consolidate our three onboarding email series into one. I was thinking 60 minutes
> Thursday with the lifecycle team, engineering, and someone from support.

**One round of questions.** Only the two inputs that change the artifact:

> 1. Who makes the call in the room, you or the lifecycle lead?
> 2. Is the 90 day activation data per series available before Thursday, or does the
>    meeting have to run without it?

Answers: the lifecycle lead decides, and the data is available. Everything else is
assumed and labeled in the packet.

**1. Justify the meeting.** The outcome is nameable: consolidate the three onboarding
series into one, or keep them separate, with an owner and a date attached either way.
A decision that needs three functions in the same room is a meeting, not an email.

**2. Classify it.** Mission-oriented. It exists to produce one decision and it dies once
the decision is made. That sets the prep depth: pre-reads required 24 hours ahead, a
named decider, and the decision protocol stated in the first five minutes.

**3. Curate attendees.** "The lifecycle team, engineering, and someone from support" is
eight people counting you, and zero roles. Every name has to trace to a role, so it
resolves to
four: Andrew (Owner), Priya (Decider), Marcus (Contributor: migration cost and the send
infrastructure), Dana (Contributor: what new users actually write in about). The other
four, two from lifecycle and two from engineering, are Informed. They get the follow-up
note, not an invite.

**4. Timebox it.** Sixty minutes was the assumption, not a requirement. Cut to 30.
Work expands to fill the container, so the container shrinks. Minutes are allocated per
item and the final five are reserved for decisions, owners, and dates.

**5. Build the agenda** from `assets/agenda-template.md`, with the objective as one
sentence, the materials named, and a send-by line 24 hours ahead so the pre-reads
actually get read.

**6. Attach the questions.** This meeting's job is to make a decision, so the matching
guide in `references/question-bank.md` leads with Why and What. Four questions, tailored
to onboarding, not twenty questions pasted from the bank.

**The Meeting Packet:**

```
Agenda: Onboarding Series Consolidation
Objective: Decide whether the three onboarding series become one, or stay separate.
Owner: Andrew
Type: Mission-oriented
Date and time: Thu Aug 6, 9:00 to 9:30 MT
Attendees:
  - Andrew (Owner)
  - Priya (Decider)
  - Marcus (Contributor: migration cost, send infrastructure, what breaks)
  - Dana (Contributor: what new users write in about in week one)
Informed, gets the notes: The two lifecycle teammates and two engineers not in the room
Materials, shared in advance: The three series mapped side by side, one page.
  90 day activation by series.
Send agenda and materials by: Wed Aug 5, 9:00 MT

Items:
1. Decision protocol and the one number that settles it (5 min)
   Everyone knows who decides and on what evidence, before the debate starts
2. The case for one series, exceptions only (8 min)
   The open question is named, the pre-read is not re-read aloud
3. Migration cost and support risk (7 min)
   Each risk has a named owner or an accepted label
4. Objections (5 min)
   Anything that would flip the call is said in the room, not after it
Final 5 min: decisions, owners, dates

Discussion questions:
- What would make this a clear yes or a clear no by the end of the 30 minutes?
- Why now, rather than after the Q4 freeze?
- What is the worst case for a new user in week one if we merge the three?
- Why consolidate at all, instead of trimming each series in place?

Assumptions, correct any that are wrong:
- Priya is the lifecycle lead. You named the role, not the person, so fix the name
  if it is someone else.
- 30 minutes, not the 60 you offered.
- Dana is the support voice. You said someone from support, so swap the name if
  Dana is not the one who reads the week one tickets.
- 9:00 MT Thursday. Move it if the pre-read cannot ship by Wednesday morning.
```

The packet is ready to paste into the invite. Had step 1 come up empty, with no outcome
nameable beyond "discuss onboarding," the skill would have said so and drafted the doc
that replaces the meeting. A meeting that cannot name what it produces is a document.
