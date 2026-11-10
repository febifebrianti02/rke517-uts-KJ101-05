# C. Link table and build plan

## Link table (one owner per data)
| Data | Owner (system or person) | Who reads it | How it moves |
|---|---|---|---|
| Patient RM number and name | Registration counter (existing process) *(my assumption)*; the app keeps a reference copy | Doctor, admin, management | Typed in by doctor or admin in round 1; name shown to confirm. No connection to registration in this plan. |
| Referring doctor list | Head of records unit *(my assumption)* | Doctor, admin | Entered once in the app; changed by request. |
| Hospital list | Admin staff *(my assumption)* | Doctor, admin | Entered in the app; new hospitals added when needed. |
| Diagnosis, specialty, destination | Doctor (clinical decision) | Admin, management | Entered by the doctor in the request. |
| Referral request and its status | The app | Doctor, admin, management | Created by the doctor's request; status changes by the app. |
| Approval | Doctor | Admin, management | Doctor clicks approve; the app records time and who. |
| Letter number, issue date, valid until | The app (automatic) | Admin, hospital via admin | Generated at printing. |
| Letter copy | The app (digital copy) | Admin | Created at printing; the paper copy handling in the RM folder is open (Q-04). |
| Reply letter record | Admin staff (records it); original paper stays with the RM folder *(my assumption)* | Admin, management | Admin enters date and note on the referral. |
| Status events (history) | The app (automatic) | Management | Written at every status change. |
| Summary numbers | The app (calculated, not typed) | Management, director | Calculated from referrals and status events when the page opens. |

## Build plan in 3 rounds
| Round | What it delivers | What the client can check | What waits |
|---|---|---|---|
| 1 | Referral request, doctor approval, official print only after approval, automatic letter number and valid-until date, the referral list with status, search by letter number / RM number / name. The digital log replaces the log book. | Requests appear at once in the admin queue (R-01). No referral missing at the end of the day (R-02). Pak Joko sees every status (R-03). A hospital's call is answered with one search (R-06). | Reply letters, expired marker, summary numbers, status history screens. |
| 2 | Recording of hospital reply letters, expired marker after 90 days, status events with times. | Pak Udin's surgeon letter can be recorded and linked (R-07). Expired letters are marked (R-05). | Summary numbers, any cost figures. |
| 3 | Summary page with counts per status and per day and the average waiting time; polish after real use on the shared computer. | Pak Joko can show the director the numbers and compare with today's 40 minutes (R-08). | Cost and savings figures until the client gives real data (Q-03); connections to other systems. |

Why this order: round 1 attacks the three problems the client named first (waiting time, missing log entries, finding the copy). Reply letters and numbers need data that only exists after rounds 1 and 2 have been in use. Round 1 stays small because the clinic has 2 medical records staff and only one shared computer *(my assumption)*.
