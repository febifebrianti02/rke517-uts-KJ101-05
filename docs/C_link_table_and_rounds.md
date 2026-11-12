# C. Link table and build plan (v1.1)

Changes made for CR-1 are marked **[CR-1]**.

## Link table (one owner per data)
| Data | Owner (system or person) | Who reads it | How it moves |
|---|---|---|---|
| Patient RM number and name | The registration counter of the site where the patient is registered (one owner per patient record) *(my assumption, Q-12)*; the app keeps a reference copy | Doctor, admin, management | Typed in by doctor or admin in round 1; name shown to confirm. No connection to registration in this plan. |
| Referring doctor list | Head of records unit *(my assumption)* | Doctor, admin | Entered once in the app; changed by request. **[CR-1]** Each doctor is entered with a site. |
| **[CR-1]** Site list (Main clinic, Branch clinic) | Head of records unit *(my assumption)* | Everybody | Two fixed values, set once. A new site would be a new change request. |
| **[CR-1]** Site of a referral | The app (automatic, from the logged-in user's site) | Doctor, admin, management | Written when the request is created; never typed. |
| Hospital list | Admin staff of the main clinic *(my assumption)* | Doctor, admin (both sites) | One list for both sites; entered in the app; new hospitals added when needed. |
| Diagnosis, specialty, destination | Doctor (clinical decision) | Admin, management | Entered by the doctor in the request. |
| Referral request and its status | The app | Doctor, admin, management | Created by the doctor's request; status changes by the app. |
| Approval | Doctor | Admin, management | Doctor clicks approve; the app records time and who. |
| Letter number, issue date, valid until | The app (automatic) | Admin, hospital via admin | Generated at printing. **[CR-1]** One running number for both sites, so the app (not a person at either site) owns the sequence. |
| Letter copy | The app (digital copy) | Admin (both sites, read only for the other site) | Created at printing; the paper copy handling in the RM folder is open (Q-04). |
| Reply letter record | Admin staff of the site that issued the referral (records it); original paper stays with the RM folder *(my assumption)* | Admin, management | Admin enters date and note on the referral. |
| Status events (history) | The app (automatic) | Management | Written at every status change. |
| Summary numbers | The app (calculated, not typed) | Management, director | Calculated from referrals and status events when the page opens, per site and in total. |

## Build plan in 3 rounds
| Round | What it delivers | What the client can check | What waits |
|---|---|---|---|
| 1 | Main clinic: referral request, doctor approval, official print only after approval, automatic letter number and valid-until date, the referral list with status, search by letter number / RM number / name. The digital log replaces the log book. **[CR-1]** The site is stored on every referral and doctor from the start, and the letter number is one running sequence, so adding the branch later needs no change in the data. | Requests appear at once in the admin queue (R-01). No referral missing at the end of the day (R-02). Pak Joko sees every status (R-03). A hospital's call is answered with one search (R-06). | The branch clinic, reply letters, expired marker, summary numbers. |
| 2 | **[CR-1]** The branch clinic starts: its users, its own work queue, the site filter in the list, search over both sites, no duplicate letter numbers (R-03, R-05, R-06, R-09). Also, as in v1.0, recording of hospital reply letters. | A branch doctor's request shows only in the branch queue and in Pak Joko's list (R-09). A letter issued at the branch is found from the main clinic (R-06). Pak Udin's surgeon letter can be recorded and linked (R-07). | Expired marker, summary numbers, any cost figures. |
| 3 | The expired marker after 90 days, and the summary page with counts per status and per day and the average waiting time, **[CR-1]** per site and in total; polish after real use. | Pak Joko can show the director the numbers for each site and compare with today's 40 minutes (R-08). Expired letters are marked (R-05). | Cost and savings figures until the client gives real data (Q-03); connections to other systems; more branches. |

**[CR-1] What moved and why.** The expired marker moved from round 2 to round 3, to make room for the branch in round 2. The client asked for the branch itself, but gave no size, computers or internet for it (Q-09), so the branch starts only after round 1 has been used at the main clinic. If Q-09 shows that the branch has no computer or no internet, the branch start moves to round 3 *(my assumption)*.

Why this order: round 1 attacks the three problems the client named first (waiting time, missing log entries, finding the copy). Reply letters and numbers need data that only exists after earlier rounds have been in use. Round 1 stays small because the clinic has 2 medical records staff and only one shared computer *(my assumption)*.
