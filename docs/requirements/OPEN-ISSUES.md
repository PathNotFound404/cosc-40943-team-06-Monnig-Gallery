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
| OI-11 | Who counts as a gallery administrator, and does release 1.0 need a way for them to add or edit meteorites (e.g., a web portal), or is content loaded by the team? | Drives `SEC-admin-authenticated`, `MNT-content-update`. (Where the gallery hours are kept is `OI-51`.) | Heather, Dr. Mayne | 2026-11-07 |
| OI-12 | Must the full collection be readable with no network, and how much downtime of the data source is acceptable during gallery hours and tours? | No guest Wi-Fi; drives `ROB-offline`, `AVL-gallery-hours`, `RI-connectivity`. | Heather; team | 2026-11-07 |
| OI-13 | What load times are acceptable for the database list, detail view, and filters? Measure in the gallery on a first build, then agree with the client. | `PER-*` thresholds are TBD; no number until measured. | Team, then Heather | 2026-11-07 |
| OI-14 | What are the oldest iOS and Android versions the app must support? | `OE-mobile-platforms`; affects which visitors can install it. | Team, check with Heather | 2026-11-07 |
| OI-15 | What does the no-photography rule cover, and why? Who owns the meteorite photos the app will use, and what credit do they need? | Blocks any camera feature (`CO-no-in-gallery-photography`) and image licensing (SRS §11). | Heather, Dr. Mayne | 2026-10-30 |
| OI-16 | Is the app meant for children to use on their own devices? Should it collect any visitor data at all? | Children's-privacy law and App Store / Google Play rules for kids apps apply if it collects data from children (`DI-no-personal-data`, `FR-CONTENT-no-visitor-account`). | Heather; team to research | 2026-11-07 |
| OI-17 | What is the app's name, and who publishes it: does "no TCU affiliation" cover the name, the publisher account, and the store listing, or only branding? | Drives `CO-monnig-branding` and store setup (`BR-no-tcu-affiliation`). | Heather, TCU Marketing | 2026-10-30 |
| OI-19 | Will the chosen accessibility standard (`OI-3`) require more setup questions, such as font style, high contrast, or turning text-to-speech on? | Could add steps to `UC-PREF-first-launch-survey`. | Heather, Dr. Mayne | 2026-11-11 |
| OI-20 | Does the chosen accessibility standard (`OI-3`) require more from text-to-speech playback, such as highlighting the text being read, working with the lock-screen media controls, or a rule for when the device's screen reader and the app's text-to-speech both speak? | Could add controls or steps to `UC-TTS-control-playback`. | Heather, Dr. Mayne | 2026-11-11 |
| OI-21 | Do meteorite descriptions, and any other text read aloud, come with paragraph breaks? | Skip forward and back in `UC-TTS-control-playback` move by paragraph. Text with no breaks is one paragraph, so skipping would only end or restart reading. | Team, once the data is seen (`OI-4`) | 2026-11-11 |
| OI-22 | Where a platform's speech engine cannot resume in the middle of a paragraph, is resuming from the start of that paragraph acceptable? | Decides whether `UC-TTS-control-playback` step 4 can be met the same way on iOS and Android (`INT-two-platforms`). | Team | 2026-11-11 |
| OI-23 | What are the gallery's themed sections: their names, which room each is in, the order a visitor walks them, and which displays each holds? | `UC-TOUR-browse-gallery-section` has no content without it, and the SRS domain model (§7.1) has no Section yet. | Heather, Dr. Mayne | 2026-11-11 |
| OI-24 | Where do section names, descriptions, and display lists come from (the catalog, the app's own data, or the gallery), and who keeps them current? | The catalog fields in SRS §7.2 do not record sections. Blocks the data design for `UC-TOUR-browse-gallery-section`; related to `OI-4` and `OI-11`. | Heather, Dr. Mayne, Team | 2026-11-11 |
| OI-26 | Do visitors' iOS and Android devices reliably have a Spanish text-to-speech voice installed? If not, should the app tell visitors how to add one, or should the gallery pay for a speech service (`BR-monnig-funds-costs`)? | If the voice is missing, `UC-TTS-listen-to-content` 4a fires and Spanish speakers can't listen at all (`DE-device-tts`, `SI-device-speech`). | Team (test on devices), then Heather | 2026-11-12 |
| OI-27 | Which meteorites have 3D scans, in what file format, who owns them, and where will they be hosted for the app? | The 3D model replaces the hero image in `UC-DAT-view-meteorite` and drives `UC-DAT-view-3d-model`; SRS §7.2 has no 3D scan field yet. | Dr. Mayne, Asa | 2026-11-12 |
| OI-28 | Which meteorites will have a written description in release 1.0, and who writes and approves them? | The catalog may not hold descriptions (SRS §7.4); the description in `UC-DAT-view-meteorite` and Listen (`UC-TTS-listen-to-content` PRE-2) depend on it. | Heather, Dr. Mayne | 2026-11-12 |
| OI-29 | Where does the gallery map graphic come from, and who supplies it and the room outlines? | Blocks `UC-TOUR-view-gallery-map` step 4; the floor plan was requested in the client interview and receipt is not recorded. | Heather, team | 2026-11-12 |
| OI-30 | Is the map a fixed picture, or can the visitor zoom and pan? Are sections tappable on the map, or only rooms? | Changes steps 4 and 5 of `UC-TOUR-view-gallery-map`. | Team | 2026-11-12 |
| OI-32 | Is View gallery map in release 1.0? | `UI-room-selection` is Proposed and `FEAT-section-screens` is out of MVP scope; ties to `OI-1`, `OI-25`. | Team, Heather | 2026-11-12 |
| OI-33 | Can the device's speech engine, or a paid speech service, read at every speed from 0.5x to 2x on both iOS and Android? If not, what should the app do? | Decides extension 6b of `UC-TTS-voice-speed` (`SI-device-speech`, `DE-device-tts`). | Team to test on a first build | 2026-11-13 |
| OI-34 | Is a step of 0.1x right for the voice speed slider and number box? | Sets the validation rule for `voiceSpeed` in `UC-TTS-voice-speed`. | Team | 2026-11-13 |
| OI-36 | Which voice should the app prefer when the engine returns several for the selected language, and which Spanish (for example US or Mexican) fits a Texas audience? | Decides extensions 4b and 4c of `UC-TTS-play-in-selected-language`. | Team (test on devices), then Heather | 2026-11-16 |
| OI-37 | What should the "voice not available" message say, in each language, and should it tell the visitor how to get a voice once `OI-26` is decided? | Extension 4a of `UC-TTS-play-in-selected-language`. | Team | 2026-11-16 |
| OI-38 | A 3D model can't be read by a screen reader. Does every model need a text description, who writes it, and what must it cover? | `UC-DAT-view-3d-model` must meet `USE-screen-reader`; without a description, screen reader users get nothing from the model. | Heather, Dr. Mayne | 2026-11-15 |
| OI-39 | Favorites are saved only on the device for release 1.0. Should a later release keep them across devices or after a reinstall, which needs a back end? | `UC-DAT-view-favorites` assumes device-only storage (`DI-no-personal-data`). A back end adds hosting cost (`BR-monnig-funds-costs`) and may need visitor accounts (`FR-CONTENT-no-visitor-account`). | Heather; team | 2026-11-15 |
| OI-40 | What is the default for each preference (language, text size, color mode, voice speed, captions) that a reset returns to? | POST-1 of `UC-PREF-reset-preferences`, the first-launch setup, and 2a of `UC-PREF-customize-visual-preferences` depend on it. Reset returns every preference, captions included, to its default (team decision, 2026-11-20); captions default to off. Color mode is light (`OI-18`); the rest are not decided. | Team, Heather | 2026-11-15 |
| OI-43 | Do the gallery's display labels show the Monnig # or another number a visitor could type into the app to find a meteorite? | If so, `UC-DAT-search-database` should match that number as well as the name. | Heather | 2026-11-15 |
| OI-45 | How do administrators sign in to the admin portal: with their TCU accounts through TCU's sign-in, or with accounts the portal manages itself? Who adds and removes administrators, and how is a forgotten password reset? | Decides the sign-in service in `UC-ADM-log-in` and `SEC-admin-authenticated`, and what the maintainer must run (`OI-5`). | Heather, Dr. Mayne, Asa (TCU IT) | 2026-11-15 |
| OI-46 | How long may an administrator's portal session stay idle, and how many failed sign-ins lock an account, and for how long? Does TCU IT have a policy we must follow? | Values for `UC-ADM-log-in` 4b and session expiry; the team should not invent them. | Asa (TCU IT), then team | 2026-11-15 |
| OI-47 | What is a gallery section, and how does it differ from a room, a display, and an exhibit? Which areas of the gallery are sections and which are rooms (e.g. "all Texas" is described as a room)? | `UC-TOUR-browse-gallery-section` depends on it; "Section" is not in the glossary or the SRS domain model (§7.1). | Heather, Dr. Mayne | 2026-11-16 |
| OI-49 | Is `UC-PREF-retake-setup-survey` worth keeping, given that Settings (`UC-PREF-customize-visual-preferences`) can already change all three preferences? | Decides whether the retake use case is built at all; left for the team to decide in the PR #23 review. | Team | 2026-11-12 |
| OI-50 | If a visitor already has large text set on their device (iOS Dynamic Type or Android font scale), does the app's Small, Medium, and Large text size scale on top of it or replace it? | Affects `USE-text-scaling`, accessibility, and the text size in `UC-PREF-first-launch-survey` and `UC-PREF-customize-visual-preferences` (raised in the PR #20 review). | Team | 2026-11-12 |
| OI-51 | Where are the gallery's hours kept, so they stay current in the app when they change? | `UC-TOUR-view-visitor-info` and `FR-PLAN-visitor-info` show the hours; if they live in the app, someone must update them (`MNT-content-update`). Previously cited as `OI-11`, which is the admin portal question. | Heather, Team | 2026-11-20 |
| OI-52 | When the selected language is Spanish and a description has fallen back to English (`FR-LANG-content-fallback`), can that English text be read aloud, and so captioned? | `UC-TTS-listen-to-content` 2a currently does not read it; `UC-PREF-toggle-captions` follows whatever is read. Not decided at the 2026-11-20 meeting. | Team, Heather | 2026-11-20 |
| OI-53 | Should voice speed have a sample voice the visitor can listen to before saving? | The confirm-step half of `OI-35` was decided on 2026-11-20; this half was not. Affects `UC-TTS-voice-speed`. | Team | 2026-11-20 |



## Resolved

| ID | Question | Answer | Answered by | Date | Filed in |
|---|---|---|---|---|---|
| OI-0 | _[Example row, delete it]_ | _[What we were told]_ | _[Name]_ | _[YYYY-MM-DD]_ | _[`BO-grading-time`, or the glossary term, or the section]_ |
| OI-18 | Is the default color mode Light or Dark? | Light for now. A future version may default to the device's own light or dark setting. | Team (Cody Pinkston) | 2026-11-11 | `UC-PREF-first-launch-survey` step 4 and Associated Information |
| OI-25 | Is browsing gallery sections in release 1.0, given that `FEAT-section-screens` is listed as out of MVP scope? | Yes, it is in scope for 1.0. The vision and scope (§4.3) and SRS §1 still list `FEAT-section-screens` as out of scope and need updating. | Team | 2026-11-16 | `UC-TOUR-browse-gallery-section` |
| OI-31 | What should a room screen list: sections, displays, meteorites, or all three? | Sections only. Home → Gallery Map → room → sections in the room → displays and meteorites in the section. On-display meteorites have their own use case. | Team | 2026-11-20 | `UC-TOUR-view-gallery-map`, `UC-TOUR-browse-gallery-section` |
| OI-35 | Should voice speed apply as soon as it is set or only after a confirm step? | After a confirm step. Settings has a Save button at the bottom; every Settings value, voice speed included, applies after the visitor confirms. The sample-voice part is now `OI-53`. | Team | 2026-11-20 | `UC-PREF-customize-visual-preferences`, `UC-TTS-voice-speed`, `UC-PREF-toggle-captions` |
| OI-41 | Does resetting preferences also clear saved favorites? | No. Reset only returns preferences and settings to their defaults; favorites are untouched. | Team | 2026-11-20 | `UC-PREF-reset-preferences`, `UC-DAT-save-favorite`, `UC-DAT-view-favorites` |
| OI-42 | Is highlighting the sentence being read what the gallery means by captions, should captions be on by default, and will videos come with caption files? | Yes, captions are highlighting the sentence being read, and the visitor can toggle them. Off by default. Probably not in 1.0 (1.1 to 1.3). Narration videos will not ship with their own caption files. Whether English fallback text can be read aloud is now `OI-52`. | Team | 2026-11-20 | `UC-PREF-toggle-captions` |
| OI-44 | Where does "on display" come from, and who keeps it current? | A field in the database (`onDisplay`). When an administrator assigns a meteorite to a display in a section or room, it is on display by default; gallery administrators keep the field current. | Team | 2026-11-20 | `UC-ADM-update-content`, `UC-DAT-view-on-display-items`, `UC-DAT-filter-database` |
| OI-48 | Team discussion: the browse flow Rooms → Sections → Displays → View, and what it changes in the other TOUR use cases. | Agreed. The map and room screen lead to a section; meteorites and exhibits open only from the section screen. The self-guided tour uses the same room, section, display flow, with no "stops". | Team | 2026-11-20 | `UC-TOUR-view-gallery-map`, `UC-TOUR-browse-gallery-section`, `UC-TOUR-view-exhibit`, `UC-TOUR-take-self-guided-tour`, `UC-DAT-view-meteorite` |
