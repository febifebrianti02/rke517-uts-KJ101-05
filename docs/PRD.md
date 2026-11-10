# Mini-PRD: KJ101-05 Referral Letter App

Anything the client did not say is labelled **(my assumption)**.

## 1. Problem and goal
Klinik Pratama Medika Utama (about 90 visits a day, 2 medical records staff) handles outgoing referral letters on paper. Patients wait about 40 minutes for a letter. The log book misses about one referral in five. When a hospital calls to verify a letter, finding the clinic's copy takes a long time. Reply letters from hospitals cannot be recorded anywhere.

**Goal:** one small app to request, approve, print and log referral letters, so that nothing gets lost and everybody can see the status of every case at any time. In three months the client wants to see every status without asking anyone, and the three problems above to happen much less.

## 2. Users and scope
| User | What they do in the app |
|---|---|
| Doctor | Creates a referral request. Approves it. |
| Admin staff (Mas Rizky and colleague) | Sees the queue, previews and prints the letter after approval, records hospital reply letters, searches referrals when a hospital calls. |
| Management (Pak Joko, head of records unit) | Views the status list and the summary numbers. |

The patient does not use the app. The patient only receives the printed letter.

**IN (round 1 to 3):**
- Referral request, doctor approval, letter number, 90-day validity, printing
- Automatic log with status for every referral
- Search by letter number, RM number or patient name, with a copy of the letter
- Recording of hospital reply letters
- Summary numbers: referrals per status and per day, average waiting time
- Runs on the one shared computer *(my assumption: browser-based, log in by role)*

**OUT (and why):**
- Cost and savings reports: no cost data exists in any source (Q-03). The client asked for money in every report, but this waits for real figures.
- Connection to other systems (registration, BPJS, claims, hospitals): not requested, and the client has only one shared computer *(my assumption)*.
- Notifications to patients or hospitals, a patient app, incoming referrals, other clinics: not requested.
- Clinical content of the reply letter (findings): only the received date and a short note are kept (Q-04).

## 3. User stories
- **US-1** As a doctor, I want to enter the referral request in the app, so that the patient does not carry a paper form and wait. (R-01)
- **US-2** As admin, I want every referral to be logged automatically, so that none is missed. (R-02)
- **US-3** As Pak Joko, I want to see the status of every referral at any time, so that I do not need to ask anyone. (R-03)
- **US-4** As a doctor, I want admin to be able to print the official letter only after my approval, so that no unapproved letter leaves the clinic. (R-04, depends on Q-01)
- **US-5** As admin, I want each letter to carry a letter number and a valid-until date, so that the 90-day rule is applied the same way every time. (R-05)
- **US-6** As admin, I want to find a referral and its letter copy in one search, so that I can answer a hospital's call quickly. (R-06)
- **US-7** As admin, I want to record that a reply letter came back, so that the referral shows it. (R-07)
- **US-8** As the director's reporter (Pak Joko), I want a summary in numbers, so that my director sees results without a story. (R-08)

## 4. Checks (Situation, Action, Result)
| ID | Story | Situation | Action | Result |
|---|---|---|---|---|
| C-1 | US-1 | Dr. Rina decides Wati (RM 7712) needs an eye referral for cataract to RSUD Kota. | She fills in the request in the app. | Status "Requested" with request time; it shows in the admin queue immediately. |
| C-2 | US-2 | Three referrals are requested on 3 November. | Admin opens the list at the end of the day. | All three are there. |
| C-3 | US-3 | Pak Joko asks where Siti A.'s referral (RM 6519, Internal, dr. Bayu) stands. | He filters the list by status. | He sees her referral and status without asking. |
| C-4 | US-4 | Udin's request (RM 8030) is not yet approved. | Admin clicks "Print official letter". | Refused; draft preview only. After approval the print works. |
| C-5 | US-5 | A letter is issued on 2 November 2026. | Staff open the letter. | Letter number in the format R/1102/XI and "valid until 31 January 2027"; after that date shown as expired. |
| C-6 | US-6 | A hospital calls about letter R/1103/XI. | Admin searches the letter number. | Udin's referral to RS Karya Bhakti and a letter copy appear in one search. |
| C-7 | US-7 | Pak Udin returns with the surgeon's letter. | Admin records the reply on his referral. | Status "Reply received" with the date; the reply is linked to his referral. |
| C-8 | US-8 | The director asks for the week's numbers. | Pak Joko opens the summary. | Counts per status and per day, and the average waiting time in minutes. |

## 5. Data list
| Data item | Example | Who enters it | Required? | Kept in (entity) |
|---|---|---|---|---|
| RM number | 7712 | Doctor or admin (typed, name shown to confirm) | Yes | PATIENT |
| Patient name | Wati | Doctor or admin | Yes | PATIENT |
| Referring doctor | dr. Rina | Doctor (chosen from list) | Yes | DOCTOR |
| Destination hospital | RSUD Kota | Doctor (chosen from list) | Yes | HOSPITAL |
| Specialty | Eye | Doctor | Yes | REFERRAL |
| Diagnosis | Cataract | Doctor | Yes | REFERRAL |
| Request date and time | 02/11/2026 09:10 *(example)* | App (automatic) | Yes | REFERRAL |
| Status | Requested, Approved, Issued, Reply received | App (automatic) | Yes | REFERRAL |
| Approval date and time | 02/11/2026 09:25 *(example)* | App when doctor approves | After approval | REFERRAL |
| Letter number | R/1102/XI | App (automatic) | After approval | REFERRAL |
| Issue date | 02/11/2026 | App at printing | After printing | REFERRAL |
| Valid until | 31/01/2027 | App (issue date + 90 days) | After printing | REFERRAL |
| Reply received date | 09/11/2026 *(example)* | Admin | Only if a reply comes | REPLY_LETTER |
| Reply note | Surgeon's letter received | Admin | No | REPLY_LETTER |
| Event status, time and who did it | Issued, 02/11/2026 09:40, admin | App (automatic) | Yes | STATUS_EVENT |

Expired is not stored: it is shown when today is after "valid until" *(my assumption)*. Waiting time is the time from the "Requested" event to the "Issued" event.

## 6. Open questions
See `docs/A_requirements.md`, Q-01 to Q-07. The most important are Q-01 (print before or after signing: the sources disagree), Q-03 (what "money in every report" means) and Q-05 (the single shared computer).
