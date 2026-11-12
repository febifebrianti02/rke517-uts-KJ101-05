# Changelog

## v1.1 (__ November 2026: write the day you tag v1.1)
Change request CR-1 from Bapak Joko: the app must also cover the branch clinic in the next village, which will use the same app, and it will have more users than planned.
- Changed:
  - `docs/A_requirements.md`: new requirement R-09 (every referral has a site, set automatically from the user's site); R-03, R-05, R-06 and R-08 changed (site filter, no duplicate letter numbers, search over both sites, numbers per site and in total); new open questions Q-08 to Q-12; Q-05 marked as partly replaced by Q-09.
  - `docs/B_models/`: ERD gets the new attribute `site` in REFERRAL and DOCTOR (still 6 entities); DFD context and level 1 get new labels (both sites, site filter, numbers per site), with the same processes, flows and stores; README of the models updated, balance check redone.
  - `docs/PRD.md`: scope (IN: one branch, several users at once; OUT: more branches, moving a referral between sites, a separate number series per site), user story US-9, check C-9, data list (+ site).
  - `docs/C_link_table_and_rounds.md`: link table (site list, site of a referral, one running letter number owned by the app); the plan: branch starts in round 2, the expired marker moves to round 3.
  - `creative/`: mock-up shows the site; poster's "coming later" box follows the new plan.
  - `docs/AI_LOG.md`: entries for this change.
- Not changed, and why:
  - The core flow (request, approve, print, log) and the 90-day validity rule: CR-1 does not touch them.
  - The flowmap of today's work: it shows how the main clinic works, and nobody has described how the branch works (Q-08).
  - The DFD processes, flows and data stores, and the number of ERD entities: a site is a property of a referral and a doctor, so no new process, store or entity is needed.
  - Print order (Q-01), who approves (Q-02), money in reports (Q-03), reply letter details (Q-04): still open, CR-1 does not answer them.
  - Scope: only the one branch the client named. No other branches, no integration with other systems.
  - Round 1 stays the main clinic: the client gave no size, computers or internet for the branch (Q-09), so the branch starts in round 2, after round 1 has been in use.
- Why: the client asked for one more site, so only what depends on the site changes; everything else stays so that v1.0 and v1.1 stay comparable.

## v1.0 (date)
- Parts A, B and C.
