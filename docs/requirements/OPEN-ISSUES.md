# Open Issues

**Project:** Monning Meteorite and Gallery App
**Team:** Team 6

---

_**What this file is.** Every question about the project that you cannot answer yet, in one place, with the name of the person who can answer it. It is the shortest document in `docs/requirements/` and the one your client meetings run on._

_**Why it exists.** A draft specification with confident guesses in the gaps is more dangerous than one with holes in it, because nobody can tell the guesses from the facts. Writing "we do not know" is not an admission of failure in week 3, it is the correct state. What fails is knowing and not writing it down._

_**Where entries come from.** Three places, and all three are routine:_

- _Drafting a section of [vision-and-scope.md](vision-and-scope.md) and hitting something the client brief does not say._
- _Your agent's list. When you ask it to draft a section, ask it to list every question it could not answer from the material you gave it. Its list is longer than yours and it is not embarrassed to ask obvious things._
- _The meeting itself. Your client says something that contradicts your notes, or answers a question with "I would have to check"._

_**How they leave.** Answered in a client meeting, in Slack, or by reading a document. Record the answer and the date, mark it resolved, and put the substance where it belongs (an objective, a term in the [glossary](project-glossary.md), a business rule). This file is a queue, not a home: an answer that stays here has not been filed._

_**Identifiers here are numbers**, `OI-1` upward, and that is deliberate. Numbers are fine for a list that only ever grows at the bottom and gets cited lightly. The slug convention in [vision-and-scope.md](vision-and-scope.md) exists for identifiers that get **reordered** or **cited often**, which is not this list._

## Before a client meeting

_[Sort the open list by what it costs you to stay wrong, not by what is easy to ask. You will get through fewer questions than you plan to. Take the ones where a wrong guess sends the whole team down the wrong path for a month, and leave the ones you can settle by reading a document or trying the client's current tool yourself.]_

_[Send the shortlist to your client the day before. A client who has seen the questions arrives with answers instead of promises.]_

## Open

| ID | Question | Why it matters | Who can answer | Raised |
|---|---|---|---|---|
| OI-1 | _[The question, phrased so it has a definite answer. Not "tell us about reporting" but "who is allowed to see another student's evaluation scores?"]_ | _[What we get wrong if we guess. Name the artifact or decision it blocks.]_ | _[Client, instructor, a specific user, or the team itself]_ | _[YYYY-MM-DD]_ |

| ID | Question | Why it matters | Who can answer | Raised |
|---|---|---|---|---|
| OI-1 | What is the main use of this app if only one thing could be done and then is there a list of priorities you have for features? (e.g. Visually impaired aid, interactivity for children, etc.)  | If we build based on one feature that isn't important, we miss the whole point. | Heather, Dr. Mayne | 2026-10-21 |

| ID | Question | Why it matters | Who can answer | Raised |
|---|---|---|---|---|
| OI-2 | If we have time to re-create the meteorite crashing into earth interactive activity, what platform would this be made for so that it can run efficiently without crashing. | Vital requirement. | Dr. Mayne, Asa, Heather | 2026-10-21 |

| ID | Question | Why it matters | Who can answer | Raised |
|---|---|---|---|---|
| OI-3 | If we are building to ADA standards, which one specifically? If not, should we do some research or outsource to ADA consultant? | If we get this wrong, we miss one of the major uses of the app. |Heather, Dr. Mayne | 2026-10-21 |
| OI-4 | Where does the app's meteorite data come from: read live from monnigcatalog.tcu.edu, an export we copy into our own database, or something else? Who owns the catalog, can we get an export or API, which fields does it have (composition, location found, date found, on display), and is a meteorite different from its samples? | Decides whether we build a back end at all, and blocks SRS §7.2, `SI-monnig-catalog`, `PER-*`, `AVL-gallery-hours`. The database we were sent has very little per meteorite. | Asa, Dr. Mayne (Cody contacting Asa) | 2026-11-07 |
| OI-5 | Who maintains the app after we graduate, what do they know how to run (is Flutter OK), who owns the App Store and Google Play accounts, and who approves gallery purchases? | Decides `CO-maintainer-stack`, `MNT-setup-docs`, `MNT-handoff`, `DE-app-store-accounts`. | Heather, Dr. Mayne, Asa | 2026-11-07 |
| OI-6 | How will the team build and test on iOS (Mac owners, a remote Mac)? | `INT-two-platforms` and store release can't be verified without it. | Team (Cody) | 2026-11-06 |
| OI-7 | Will the gallery provide tablets for visitors, and if so which kind? | Decides whether `FR-PREF-reset-for-new-visitor` and `OE-gallery-tablets` are needed. | Heather | 2026-10-30 |
| OI-8 | Are preferences kept across app launches (11/2 decision) or only for one session (`UC-PREF-identify-language-preference` POST-1)? What is the default text size? (Default color mode is settled by `OI-18`.) | The SRS and the use case currently disagree (`FR-PREF-persist`). | Team | 2026-11-07 |
| OI-9 | English and Spanish for 1.0; when do French and Vietnamese (`BO-language-options`) come? Is machine translation acceptable, and who reviews translated scientific terms before they are published? | Drives `FR-LANG-*`, `DE-gallery-content-review`, `RI-translation-accuracy`. | Heather, Dr. Mayne | 2026-11-07 |
| OI-10 | Is the visitor survey in release 1.0? Which questions and age ranges does the grant require, how often must results be reported, and in what format? | Answers not captured from launch can't be reported later (`BR-visitor-survey-data`, SRS §7.3). | Heather | 2026-10-30 |
| OI-11 | Who counts as a gallery administrator, and does release 1.0 need a way for them to add or edit meteorites (e.g., a web portal), or is content loaded by the team? | Drives `SEC-admin-authenticated`, `MNT-content-update`, `FR-PLAN-visitor-info`. | Heather, Dr. Mayne | 2026-11-07 |
| OI-12 | Must the full collection be readable with no network, and how much downtime of the data source is acceptable during gallery hours and tours? | No guest Wi-Fi; drives `ROB-offline`, `AVL-gallery-hours`, `RI-connectivity`. | Heather; team | 2026-11-07 |
| OI-13 | What load times are acceptable for the database list, detail view, and filters? Measure in the gallery on a first build, then agree with the client. | `PER-*` thresholds are TBD; no number until measured. | Team, then Heather | 2026-11-07 |
| OI-14 | What are the oldest iOS and Android versions the app must support? | `OE-mobile-platforms`; affects which visitors can install it. | Team, check with Heather | 2026-11-07 |
| OI-15 | What does the no-photography rule cover, and why? Who owns the meteorite photos the app will use, and what credit do they need? | Blocks any camera feature (`CO-no-in-gallery-photography`) and image licensing (SRS §11). | Heather, Dr. Mayne | 2026-10-30 |
| OI-16 | Is the app meant for children to use on their own devices? Should it collect any visitor data at all? | Children's-privacy law and App Store / Google Play rules for kids apps apply if it collects data from children (`DI-no-personal-data`, `FR-CONTENT-no-visitor-account`). | Heather; team to research | 2026-11-07 |
| OI-17 | What is the app's name, and who publishes it: does "no TCU affiliation" cover the name, the publisher account, and the store listing, or only branding? | Drives `CO-monnig-branding` and store setup (`BR-no-tcu-affiliation`). | Heather, TCU Marketing | 2026-10-30 |
| OI-19 | Will the chosen accessibility standard (`OI-3`) require more setup questions, such as font style, high contrast, or turning text-to-speech on? | Could add steps to `UC-PREF-first-launch-survey`. | Heather, Dr. Mayne | 2026-11-11 |
| OI-26 | Do visitors' iOS and Android devices reliably have a Spanish text-to-speech voice installed? If not, should the app tell visitors how to add one, or should the gallery pay for a speech service (`BR-monnig-funds-costs`)? | If the voice is missing, `UC-TTS-listen-to-content` 4a fires and Spanish speakers can't listen at all (`DE-device-tts`, `SI-device-speech`). | Team (test on devices), then Heather | 2026-11-12 |
| OI-27 | Which meteorites have 3D scans, in what file format, who owns them, and where will they be hosted for the app? | The 3D model replaces the hero image in `UC-DAT-view-meteorite` and drives `UC-DAT-view-3d-model`; SRS §7.2 has no 3D scan field yet. | Dr. Mayne, Asa | 2026-11-12 |
| OI-28 | Which meteorites will have a written description in release 1.0, and who writes and approves them? | The catalog may not hold descriptions (SRS §7.4); the description in `UC-DAT-view-meteorite` and Listen (`UC-TTS-listen-to-content` PRE-2) depend on it. | Heather, Dr. Mayne | 2026-11-12 |



## Resolved

| ID | Question | Answer | Answered by | Date | Filed in |
|---|---|---|---|---|---|
| OI-0 | _[Example row, delete it]_ | _[What we were told]_ | _[Name]_ | _[YYYY-MM-DD]_ | _[`BO-grading-time`, or the glossary term, or the section]_ |
| OI-18 | Is the default color mode Light or Dark? | Light for now. A future version may default to the device's own light or dark setting. | Team (Cody Pinkston) | 2026-11-11 | `UC-PREF-first-launch-survey` step 4 and Associated Information |
