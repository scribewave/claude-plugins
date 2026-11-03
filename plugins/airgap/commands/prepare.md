---
description: Prepare a meeting in Airgap from your mail, calendar and documents
argument-hint: <which meeting, and where to look>
---

Prepare a meeting in Airgap: $ARGUMENTS

1. Find out what the meeting is about with your own tools: the user's mail, calendar and documents, wherever the user pointed you. Airgap never reads mail; you do, and you pass on only what the meeting needs.
2. If the meeting may already be prepared, check `list_meetings(when="upcoming")`. To change an existing prep, read it with `get_meeting` and pass its `prepare_meeting base_version`.
3. Call `prepare_meeting` with:
   - `title`, and `when` as a local date and time (`2026-11-05 14:00`);
   - `people`: who attends, full names as they write them;
   - `agenda`: short markdown the user will see at the top of their meeting notes (topics, questions to ask, decisions needed);
   - `vocabulary`: names, companies, products, places and acronyms likely to be said, spelled correctly. This is what makes the transcript get them right;
   - `files`: absolute paths of local documents worth having at hand (PDF, Word, text, Markdown);
   - `folder` only when the user names one; otherwise leave it out and don't ask: the prep goes to Unfiled, where you can still read and change it.
4. Call `save_context` (with the `save_context base_version` from `get_meeting`) with the background the user will want later: short mail excerpts with sender and date, document titles and paths, open questions, what was agreed so far. Quote, don't invent, and keep it under a few pages.
5. Tell the user it is under Upcoming in Airgap, and that they start the recording from it.
