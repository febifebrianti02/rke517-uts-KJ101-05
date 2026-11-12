# Mini-PRD: KJ101-05 Referral Letter App (v1.1)

Anything the client did not say is labelled **(my assumption)**. Changes made for CR-1 are marked **[CR-1]**.

## 1. Problem and goal
Klinik Pratama Medika Utama (about 90 visits a day, 2 medical records staff) handles outgoing referral letters on paper. Patients wait about 40 minutes for a letter. The log book misses about one referral in five. When a hospital calls to verify a letter, finding the clinic's copy takes a long time. Reply letters from hospitals cannot be recorded anywhere.

**Goal:** one small app to request, approve, print and log referral letters, so that nothing gets lost and everybody can see the status of every case at any time. In three months the client wants to see every status without asking anyone, and the three problems above to happen much less.

**[CR-1]** The app will be used by more people than planned and must also cover the branch clinic in the next village. The goal holds for both sites: the main clinic and the branch clinic.

## 2. Users and scope
| User | What they do in the app |
|---|---|
| Doctor (main clinic or branch) | Creates a referral request. Approves it. |
| Admin staff (main clinic or branch) | Sees the queue of their own site, previews and prints the letter after approval, records hospital reply letters, searches referrals (both sites) when a hospital calls. |
| Management (Pak Joko, head of records unit) | Views the status list and the summary numbers for both sites, or for one site. |

The patient does not use the app. The patient only receives the printed letter. **[CR-1]** Each user belongs to one site, except management, who see both *(my assumption)*.

**IN (round 1 to 3):**
- Referral request, doctor approval, letter number, 90-day validity, printing
- Automatic log with status for every referral
- Search by letter number, RM number or patient name, with a copy of the letter
- Recording of hospital reply letters
- Summary numbers: referrals per status and per day, average waiting time
- **[CR-1]** Two sites: the main clinic and one branch clinic. A site on every referral and every doctor, a work queue per site, one running letter number for both sites, search over both sites, summary numbers per site and in total
- **[CR-1]** Several users at the same time, from both sites, on the same data *(my assumption, Q-09)*

**OUT (and why):**
- Cost and savings reports: no cost data exists in any source (Q-03). The client asked for money in every report, but this waits for real figures.
- Connection to other systems (registration, BPJS, claims, hospitals): not requested.
- Notifications to patients or hospitals, a patient app, incoming referrals: not requested.
- Clinical content of the reply letter (findings): only the received date and a short note are kept (Q-04).
- **[CR-1]** More branches than the one the client named, and moving a referral from one site to another: CR-1 names one branch only. A third site would be a new change request.
- **[CR-1]** A separate letter-number series for each site: not used unless the client answers Q-10 that way.
- **[CR-1]** A model of the branch's paper process today: nobody described it (Q-08).

## 3. User stories
- **US-1** As a doctor, I want to enter the referral request in the app, so that the patient does not carry a paper form and wait. (R-01)
- **US-2** As admin, I want every referral to be logged automatically, so that none is missed. (R-02)
- **US-3** **[CR-1 changed]** As Pak Joko, I want to see the status of every referral at any time, for both sites or for one, so that I do not need to ask anyone. (R-03)
- **US-4** As a doctor, I want admin to be able to print the official letter only after my approval, so that no unapproved letter leaves the clinic. (R-04, depends on Q-01)
- **US-5** **[CR-1 changed]** As admin, I want each letter to carry a unique letter number and a valid-until date, so that the 90-day rule is applied the same way at both sites and no two letters share a number. (R-05)
- **US-6** **[CR-1 changed]** As admin, I want to find a referral and its letter copy from either site in one search, so that I can answer a hospital's call quickly. (R-06)
- **US-7** As admin, I want to record that a reply letter came back, so that the referral shows it. (R-07)
- **US-8** **[CR-1 changed]** As the director's reporter (Pak Joko), I want a summary in numbers per site and in total, so that my director sees results without a story. (R-08)
- **US-9** **[CR-1 new]** As a doctor or admin at the branch clinic, I want my referrals to be marked with my site automatically, so that I only work with my own queue and management can tell the sites apart. (R-09)

## 4. Checks (Situation, Action, Result)
| ID | Story | Situation | Action | Result |
|---|---|---|---|---|
| C-1 | US-1 | Dr. Rina decides Wati (RM 7712) needs an eye referral for cataract to RSUD Kota. | She fills in the request in the app. | Status "Requested" with request time; it shows in the admin queue immediately. |
| C-2 | US-2 | Three referrals are requested on 3 November. | Admin opens the list at the end of the day. | All three are there. |
| C-3 | US-3 **[CR-1 changed]** | Pak Joko asks where Siti A.'s referral (RM 6519, Internal, dr. Bayu) stands, and how many referrals the branch has open. | He filters the list by status, then by site "Branch clinic". | He sees her referral and status, and the branch's open referrals, without asking. |
| C-4 | US-4 | Udin's request (RM 8030) is not yet approved. | Admin clicks "Print official letter". | Refused; draft preview only. After approval the print works. |
| C-5 | US-5 **[CR-1 changed]** | One letter is issued at the main clinic and one at the branch clinic on 2 November 2026 (examples). | Both are approved and printed. | The numbers are different (for example R/1104/XI and R/1105/XI), and each letter shows "valid until 31 January 2027"; after that date it is shown as expired. |
| C-6 | US-6 **[CR-1 changed]** | A hospital calls the main clinic about letter R/1105/XI, issued by the branch. | Main clinic admin searches the letter number. | The referral (site "Branch clinic") and a letter copy appear in one search, read only. |
| C-7 | US-7 | Pak Udin returns with the surgeon's letter. | Admin records the reply on his referral. | Status "Reply received" with the date; the reply is linked to his referral. |
| C-8 | US-8 **[CR-1 changed]** | The director asks for the week's numbers. | Pak Joko opens the summary and picks "All sites". | Counts per status and per day and the average waiting time in minutes, for the main clinic, the branch clinic and the total. |
| C-9 | US-9 **[CR-1 new]** | A doctor at the branch creates a referral request. | The doctor sends the request. | Saved with site "Branch clinic"; it is in the branch queue and in Pak Joko's list, and not in the main clinic's queue. |

## 5. Data list
| Data item | Example | Who enters it | Required? | Kept in (entity) |
|---|---|---|---|---|
| RM number | 7712 | Doctor or admin (typed, name shown to confirm) | Yes | PATIENT |
| Patient name | Wati | Doctor or admin | Yes | PATIENT |
| Referring doctor | dr. Rina | Doctor (chosen from list) | Yes | DOCTOR |
| **[CR-1]** Site of the doctor | Main clinic | Head of records unit when the doctor is added *(my assumption)* | Yes | DOCTOR |
| Destination hospital | RSUD Kota | Doctor (chosen from list) | Yes | HOSPITAL |
| Specialty | Eye | Doctor | Yes | REFERRAL |
| Diagnosis | Cataract | Doctor | Yes | REFERRAL |
| **[CR-1]** Site of the referral | Main clinic or Branch clinic | App (automatic, from the site of the logged-in user) | Yes | REFERRAL |
| Request date and time | 02/11/2026 09:10 *(example)* | App (automatic) | Yes | REFERRAL |
| Status | Requested, Approved, Issued, Reply received | App (automatic) | Yes | REFERRAL |
| Approval date and time | 02/11/2026 09:25 *(example)* | App when doctor approves | After approval | REFERRAL |
| Letter number | R/1102/XI | App (automatic, one running number for both sites) | After approval | REFERRAL |
| Issue date | 02/11/2026 | App at printing | After printing | REFERRAL |
| Valid until | 31/01/2027 | App (issue date + 90 days) | After printing | REFERRAL |
| Reply received date | 09/11/2026 *(example)* | Admin | Only if a reply comes | REPLY_LETTER |
| Reply note | Surgeon's letter received | Admin | No | REPLY_LETTER |
| Event status, time and who did it | Issued, 02/11/2026 09:40, admin | App (automatic) | Yes | STATUS_EVENT |

Expired is not stored: it is shown when today is after "valid until" *(my assumption)*. Waiting time is the time from the "Requested" event to the "Issued" event. **[CR-1]** Summary numbers are grouped by the site of the referral.

## 6. Open questions
See `docs/A_requirements.md`, Q-01 to Q-12. The most important are Q-01 (print before or after signing: the sources disagree), Q-03 (what "money in every report" means) and **[CR-1]** Q-09 (the branch's users, computers and internet, which decides when the branch can start) and Q-10 (one or two letter number series).
