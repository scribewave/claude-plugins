---
description: Follow up meetings recorded in Airgap: enhanced notes, transcript corrections, context note
argument-hint: [meeting id; empty for every meeting waiting]
---

Follow up meetings recorded in Airgap: $ARGUMENTS

If no meeting is named, take every meeting `list_meetings(when="waiting")` returns whose status is done; leave the ones still transcribing for later. For each meeting:

1. `get_meeting(id)`: the prep, the notes the user took, the context note, and the versions you need to write.
2. Read the whole transcript with `review_transcript(job_id)`, following its `More:` line page by page.
3. Write enhanced notes and save them with `save_meeting_notes(id, markdown, base_version)`. Start with a `# <title>` line, then `## Summary`, `## Key points`, `## Decisions` and `## Action items` (owner and due date where said). Build on the user's own notes: they show what the user found important. Add what the transcript says that they missed, with the time of each point (`12:05`). Don't invent anything; write "None noted." for an empty section. Use the language of the meeting.
4. Propose transcript corrections with `propose_edits`, following the airgap skill's rules (verbatim, vocabulary from the prep, only what the recogniser got wrong). Airgap decides what applies; the rest waits for the user in its editor.
5. Update the context note with `save_context`: keep what is there and add what a later conversation will need (decisions, commitments, who owns what, open questions, follow-up dates).
6. Report briefly per meeting: notes saved, corrections applied and waiting, anything that needs the user.
