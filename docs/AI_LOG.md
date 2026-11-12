# AI log

Tool for all entries: Claude (Anthropic), chat on claude.ai. Date for all entries: 10 November 2026. My prompts were written in Indonesian; they are copied as I typed them. Case files were uploaded to the chat. I did not paste any real patient data (the case data is fictional).

## Entry 1
- Date and part (A-F): 10 Nov 2026, planning for A to F
- Tool: Claude chat
- My prompt (copy it): "ini cara ngerjain nya gimana?" (with the case pack uploaded)
- What the AI gave (short): a work order for the parts and the deadline for v1.0 (Wednesday 11 November, 08:00). A first list of things the sources do not agree on: print order, the reply letter from the staff chat, who approves, and the money wish with no cost data.
- What I kept, changed or rejected, and why: I kept the work order. I checked the list of disagreements against the interview, the form and the chat myself before using it in Part A.

## Entry 2
- Date and part (A-F): 10 Nov 2026, A (voice note)
- Tool: Claude chat
- My prompt (copy it): "saya cuma ada voice bentuk audio saja tidak ada txt atau lain nya"
- What the AI gave (short): it could not play the audio and told me to write down the voice note myself and what to listen for (validity days, print order, new things).
- What I kept, changed or rejected, and why: I kept the advice. The text of the voice note came from me, not from the AI.

## Entry 3
- Date and part (A-F): 10 Nov 2026, A
- Tool: Claude chat
- My prompt (copy it): "ini isi voice nya" (followed by the voice note text)
- What the AI gave (short): a table of the contradiction about when admin may print the letter (form and interview: after the doctor signs; voice note: before; Mas Rizky's description: before), a draft of open question Q-01 with a proposal, and the other open questions.
- What I kept, changed or rejected, and why: kept the table and the open questions Q-01 to Q-07. The proposal in Q-01 (draft preview before approval, official print after approval) is a compromise that the AI suggested. It leans to the SPO rule, while the voice note asks the app to print before signing, so the client must confirm it.

## Entry 4
- Date and part (A-F): 10 Nov 2026, A
- Tool: Claude chat
- My prompt (copy it): "Buat spreadsheet dari jawaban terakhir."
- What the AI gave (short): an Excel file with three sheets: contradiction, open questions, and what goes into the requirements.
- What I kept, changed or rejected, and why: kept as my working notes, not part of the repo. Its question IDs (OQ-1 to OQ-6) did not match Part A (Q-01 to Q-07), see the mistake below.

## Entry 5
- Date and part (A-F): 10 Nov 2026, A, B and C
- Tool: Claude chat (it also ran code to draw the diagrams: graphviz and matplotlib)
- My prompt (copy it): "oke sekarang mulai kerjain itu semua"
- What the AI gave (short): drafts of docs/A_requirements.md, docs/B_models (flowmap, DFD context, DFD level 1, ERD as PNG, plus the note on how they fit), docs/PRD.md and docs/C_link_table_and_rounds.md.
- What I kept, changed or rejected, and why: I kept the structure and the case data (RM numbers, hospitals, letter numbers from the form). Things the client never said are marked "(my assumption)" in the files, for example who approves, login by role and the shape of the three rounds. I checked the drafts against the four case files.

## Entry 6
- Date and part (A-F): 10 Nov 2026, F
- Tool: Claude chat
- My prompt (copy it): "Buat AI_LOG.md buatkan dan kenapa F_AI_policy_and_reflection.md tidak ada isi nya?"
- What the AI gave (short): this log, a draft of my five AI rules, and a draft of the reflection. It left one part of the reflection for me to write (what I can do without AI), because only I know that.
- What I kept, changed or rejected, and why: the rules are my own policy, adopted after reading them. The last part of the reflection I write myself.

## The AI mistake I caught
- What it said: the AI gave the open questions the IDs OQ-1 to OQ-6 in the spreadsheet, but Part A uses Q-01 to Q-07 and has one more question (Q-07, about the letter number and the "Doctor" column). The first draft of B_models/README.md also said Mas Rizky described "six steps", but the interview gives five stages (doctor fills the form, patient waits at the counter, admin types, prints and brings it for the signature, patient receives the letter and a copy goes to the folder, admin writes the log book). The first flowmap picture also had red notes on top of arrows.
- Why it was wrong for my case: wrong IDs would send the client to a different question than the one I mean in Part A and in the PRD. A wrong step count says the model does not match the interview.
- What I did: I compared the files with each other and with the interview, then fixed the IDs in the spreadsheet, the sentence in the README of B_models, and moved the notes in the flowmap.

## Entry 7
- Date and part (A-F): 10 Nov 2026, E (two creative pieces)
- Tool: Claude chat (it also ran code: matplotlib for the mock-up, reportlab for the poster)
- My prompt (copy it): "buatkan bisa?" (after we talked about choosing two of the five pieces, and the mock-up and the poster)
- What the AI gave (short): a mock-up with two screens (new referral request, and referral list with status, approve, draft preview and locked print button) as a PNG, and an A4 poster "What changes on Monday" for counter staff as a PDF. It also filled the table in creative/README.md.
- What I kept, changed or rejected, and why: I kept both pieces and the choice of mock-up and poster, because both are accurate to my PRD data list and rounds. The first mock-up picture had a status label that ran outside the screen and a text that overlapped a column; the first poster had the last status box outside the page margin. These were fixed before I used them. I check every field in the mock-up against the PRD data list before the oral check.

## Entry 8
- Date and part (A-F): 12 Nov 2026, D (change request CR-1), planning
- Tool: Claude chat
- My prompt (copy it): "terus gimana kalo ada ini" (with the CR-1 message and the task text for the change request), and then "Buat Claude Doc dari jawaban terakhir Anda."
- What the AI gave (short): a plan for CR-1: which files and diagrams are affected, what does not change, five new open questions (the branch's process, users and internet, letter numbering, who sees what, RM numbers), the GitHub steps, and a Claude Doc with this plan.
- What I kept, changed or rejected, and why: I kept the idea that the site is an attribute and not a new entity, because the ERD is already at six entities and the limit is six. The answers to the new questions are proposals only; the client did not say them, so they are marked "(my assumption)" and listed as open questions.

## Entry 9
- Date and part (A-F): 12 Nov 2026, D (drafts of the change)
- Tool: Claude chat (it also ran code: graphviz for the diagrams, matplotlib and reportlab for the creative pieces)
- My prompt (copy it): "buatkan semua nya untuk perubahan tersebut"
- What the AI gave (short): drafts of the changed files (A, B models and the three diagrams, PRD, C), the CHANGELOG entry, the mock-up and poster updated for the site, and the texts for issue CR-1, the pull request and the v1.1 release notes.
- What I kept, changed or rejected, and why: before I use them I compare each changed file with the CR-1 message, so that every new rule comes from the client and everything else is an assumption or a question. The PR checklist asks for exactly that.
