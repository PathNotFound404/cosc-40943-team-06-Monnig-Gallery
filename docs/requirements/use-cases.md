# Use Cases

**Project:** Monnig Meteorite Gallery Tour App
**Team:** _[Team NN]_
**Client:** _[Client name and organization]_
**Version:** 0.1

---

_**How to use this template.** Instructions appear in italic square brackets. Fill in underneath them and leave them in place until the document is stable._

_**What a use case is.** One goal a user can accomplish with your system, written as the dialogue between the actor and the system, including what happens when it goes wrong. It is the unit of work in this course: one use case becomes one issue, one branch, one pull request, and one set of tests._

_**Why the use case and not the user story.** You will meet user stories in industry, and they are a good planning tool: "As a student, I want to submit my report so that I get credit." A story is deliberately under-specified, because it is a **placeholder for a conversation** that happens later, between people. That is exactly the wrong property when the thing building your code is an agent that will implement precisely what the specification says and never ask what you meant. Use stories to plan and prioritize. Build against use cases._

_The difference that matters is the parts a story does not have: preconditions, the step-by-step flow, and above all the **extensions**, which is where the failure paths live. Most defects your team ships this semester will be in a path nobody wrote down._

## Identifiers

_Use cases are identified as `UC-<AREA>-<slug>`, where the area code groups related functionality and the slug is coined from the goal: `UC-RUB-create-rubric`, `UC-WAR-manage-activities`, `UC-STU-invite-students`._

_Pick your own area codes from your project's feature areas, three or four letters each, and list them at the top of the Use Case List. Areas correspond to the `FEAT-*` entries in your [vision and scope](vision-and-scope.md), which is where use cases come from._

_**Never renumber, rename, or repoint an identifier.** Moving a use case between areas would change its identifier, so put it in the right area the first time, and if you get it wrong, leave it. An identifier is an address, not a description._

_Within one use case, `PRE-1`, `POST-1`, and the step numbers are local and may be renumbered freely, because nothing outside the use case cites them._

## Revision History

| Date | Version | Description | Author |
|---|---|---|---|
| 10/08/21 | 1.0 | Defined Use Case 1, 2, 3 | Kendric D’Spain |
| 10/17/21 | 1.1 | Set Use Case Priorities and added Language Preference Case | Kendric D’Spain |
| 11/3/26 | 2.0 | Redefining Use Cases | Bradley Helmholz |
| 11/18/26 | 2.1 | Draft use cases for PREF, TTS, DAT, TOUR, and ADM | Cody Pinkston, Tanner Temple, Bradley Helmholz, Edwin Rodriguez, Koen Dolezar, Turner DeMott |
| 11/18/26 | 2.2 | Add `UC-TTS-play-in-selected-language`, missed in the 2.1 merge | Bradley Helmholz, Cody Pinkston |

---

## 1. Introduction

### 1.1 Purpose

_[One paragraph: this document specifies the goals users can accomplish with the system, in enough detail that a developer knows what to build and a tester knows what to check.]_

### 1.2 Scope

_[Which feature areas from the vision and scope are covered here. Name the `FEAT-*` entries. If a feature has no use cases yet, say so rather than leaving the reader to notice.]_

---

## 2. Use Case Template

_[The field definitions. Every use case below uses exactly these fields, in this order.]_

**UC ID and Name.** _The identifier plus a concise name stating the value this use case provides to a user. Begin with an action verb, followed by an object: "Create a rubric", not "Rubric creation" and not "Rubric management", which is a feature, not a goal._

**Created By** and **Date Created.** _Who wrote it, and when._

**Primary and Secondary Actors.** _An actor is a person or other entity outside the system that interacts with it. The primary actor initiates this use case; secondary actors participate in completing it. Actors usually correspond to the user classes you identified in the vision and scope._

**Trigger.** _The business event, system event, or user action that starts the use case. The trigger tells the system to begin testing the preconditions._

**Description.** _A brief statement of the reason for and the outcome of this use case._

**Preconditions.** _What must already be true before this use case can start. **The system must be able to test each precondition**, which is what separates a precondition from a hope. Label them `PRE-1`, `PRE-2`. Example: PRE-1. The user's identity has been authenticated._

**Postconditions.** _The state of the system at successful conclusion. Label them `POST-1`, `POST-2`. Example: POST-1. The price of the item in the database has been updated with the new value._

**Main Success Scenario.** _The actor's actions and the system's responses under normal, expected conditions, as a numbered list that alternates between the two and ends by accomplishing the goal in the name. Write "The system validates..." not "The system will validate..."; use cases are written in the present tense._

**Extensions.** _Where the real work is. Two kinds, both numbered relative to the step they branch from:_

- _**Alternative flows**, other ways the use case can still succeed. Number them `4a`, `4b` for branches from step 4, with their own sub-steps `4a1`, `4a2`. Say where the flow branches off and, if it does, where it rejoins._
- _**Exceptions**, anticipated error conditions and how the system responds. Numbered the same way._

_**A use case with no extensions is not finished.** For every step, ask: what if the input is invalid, the thing is not found, the user cancels, the user is not allowed, or the external system is down? An agent building from a flow with no failure paths will invent the error handling, and you will not find out until a demo._

**Priority.** _Relative priority of implementing this. Use the same scheme across all your use cases._

**Frequency of Use.** _Roughly how often this is performed, per an appropriate unit of time. An early indicator of load, concurrency, and transaction volume, and it is the field that tells your architecture which use cases matter._

**Business Rules.** _The `BR-*` identifiers that govern this use case. **Identifiers only, never the rule's text**, so the rule has one home in [business-rules.md](business-rules.md) and cannot go stale here._

**Associated Information.** _Everything a developer needs that is not a step: the data fields and their validation rules, quality attributes that apply, display and sort strategies, and what happens if execution fails for a systemic reason such as a network timeout. If the use case makes a durable change, say whether a failure rolls it back, completes it, or leaves it partially done._

_Data fields are specified as a table:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| _[field]_ | _[type]_ | _[required, format, range]_ | _[who may see or set it]_ | _[term]_ |

**Related Use Cases.** _Other use cases this one invokes or is invoked by, by identifier and name._

**Assumptions.** _Anything assumed about this use case or how it executes._

**Open Issues.** _What you do not know yet. Mirror it into [OPEN-ISSUES.md](OPEN-ISSUES.md) so it is visible in one place._

---

## 3. Use Case List

_[Your area codes, then a table of every use case by area. Write this list first, before specifying any single use case in detail. It is the cheapest thing to review with your client, and finding out you missed a whole area costs minutes here rather than a week later.]_

| Area code | Feature area | Use cases |
|---|---|---|
| PREF | User preferences | `UC-PREF-first-launch-survey`: Set Up Preferences on First Launch<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage<br>`UC-PREF-retake-setup-survey`: Retake the Setup Survey<br>`UC-PREF-reset-preferences`: Reset Preferences<br>`UC-PREF-toggle-captions`: Turn Captions On or Off |
| TTS | Text-to-speech | `UC-TTS-control-playback`: Control Text-to-Speech Playback<br>`UC-TTS-listen-to-content`: Listen to Content<br>`UC-TTS-voice-speed`: Change Voice Speed<br>`UC-TTS-narrate-activities`: Narrate an Activity<br>`UC-TTS-play-in-selected-language`: Play in Selected Language |
| DAT | Meteorite catalog | `UC-DAT-browse-database`: Browse the Meteorite Database<br>`UC-DAT-search-database`: Search the Meteorite Database<br>`UC-DAT-filter-database`: Filter the Meteorite Database<br>`UC-DAT-view-meteorite`: View a Meteorite<br>`UC-DAT-save-favorite`: Save a Favorite Meteorite<br>`UC-DAT-view-3d-model`: View a Meteorite's 3D Model<br>`UC-DAT-view-favorites`: View Favorite Meteorites<br>`UC-DAT-view-similar-meteorites`: View Similar Meteorites<br>`UC-DAT-view-on-display-items`: View Meteorites on Display |
| TOUR | Gallery tour | `UC-TOUR-browse-gallery-section`: Browse a Gallery Section<br>`UC-TOUR-view-gallery-map`: View Gallery Map<br>`UC-TOUR-take-self-guided-tour`: Take a Self-Guided Tour<br>`UC-TOUR-view-exhibit`: View an Exhibit<br>`UC-TOUR-view-visitor-info`: View Visitor Information |
| ADM | Content administration | `UC-ADM-log-in`: Log In as an Administrator<br>`UC-ADM-update-content`: Update Meteorite Content |

---

## 4. Use Cases

_[One `###` heading per use case, grouped under a `##` heading per area. Worked example below, taken from Project Pulse. Delete it and write your own.]_

## PREF: User preferences

### UC-PREF-first-launch-survey: Set Up Preferences on First Launch

**UC ID and Name:** `UC-PREF-first-launch-survey`: Set Up Preferences on First Launch

**Created By:** Cody Pinkston

**Date Created:** November 11, 2026

**Primary Actor:** Visitor or Remote Visitor (including child visitors with an adult's help)

**Secondary Actors:** None

**Trigger:** The visitor opens the app on a device where no setup survey has been completed.

**Description:** The first time the app opens on a device, it walks the visitor through a short two-screen setup survey: language on the first screen, then text size and light or dark mode together on the second. Every answer is previewed on the survey screens as soon as it is chosen, so the visitor sees the result before moving on. When the visitor finishes or skips, the app saves the answers on the device as their preferences, applies them to the rest of the app, and opens the Home screen. The survey does not run again on later launches. The visitor can change these preferences later in Settings (`UC-PREF-customize-visual-preferences`). This use case replaces the earlier `UC-PREF-identify-language-preference` (minutes 2026-10-21, 2026-11-02, 2026-11-09).

**Preconditions:**

- PRE-1. The app is installed and has been opened.
- PRE-2. The device has no record of a completed setup survey (first launch, or the record was cleared by `UC-PREF-reset-preferences`).

**Postconditions:**

- POST-1. The visitor's language, text size, and color mode are saved on the device.
- POST-2. The device records that the setup survey is complete. On later launches the app skips the survey and restores the saved preferences (`FR-PREF-persist`).
- POST-3. Every screen, including the Home screen and any screen opened afterward, shows the saved preferences (`FR-PREF-apply-everywhere`).
- POST-4. No personal information was collected (`DI-no-personal-data`).

**Main Success Scenario:**

1. The visitor opens the app.
2. The system checks that no setup survey has been completed on this device and shows the language screen. This screen holds only the language choice: English and Spanish, with English preselected.
3. The visitor selects a language and continues.
4. The system switches all survey text to that language and shows the preferences screen. This one screen holds the remaining options:
    - Text size: Small, Medium, and Large, with Medium preselected.
    - Color mode: Light and Dark, with Light preselected.

    Each choice is shown on the survey screens as soon as it is selected, so the screens themselves are the preview. The preferences apply to the rest of the app only at step 6.
5. The visitor selects a text size and a color mode, in either order, and confirms.
6. The system saves the preferences on the device, records the survey as complete, and opens the Home screen with the preferences applied.
7. Use case ends.

**Extensions:**

- **2a. A completed setup survey is already recorded on this device.**
    - 2a1. The system skips the survey, applies the saved preferences, and opens the Home screen.
    - 2a2. Use case ends.
- **2b. A survey-complete record exists, but the saved preferences cannot be read (missing or corrupt).**
    - 2b1. The system discards the unreadable preferences and the survey-complete record.
    - 2b2. Flow rejoins at step 2 as a first launch.
- **3a. The visitor continues without changing the preselected language.**
    - 3a1. The system keeps English.
    - 3a2. Flow continues at step 4.
- **5a. The visitor confirms without changing one or both preselected options.**
    - 5a1. The system keeps the preselected value for each unchanged option (Medium or Light).
    - 5a2. Flow continues at step 6.
- **5b. The visitor goes back from the preferences screen to the language screen.**
    - 5b1. The system shows the language screen with the current language still selected. It keeps the text size and color mode already chosen.
    - 5b2. Flow rejoins at step 3.
- **\*a. On either screen (steps 2 to 5), the visitor chooses Skip.**
    - \*a1. The system keeps every answer already given and uses the defaults for the rest.
    - \*a2. Flow rejoins at step 6.
- **\*b. The app is closed or killed by the operating system before step 6.**
    - \*b1. The system saves nothing. Choices that were only shown on screen are discarded.
    - \*b2. On the next launch the flow restarts at step 2.
    - _If the app is only sent to the background and then resumed, the survey continues on the same screen with its selections intact._
- **6a. Saving the preferences fails (for example, the device storage is full).**
    - 6a1. The system applies the chosen preferences for the current session and opens the Home screen.
    - 6a2. The system shows a non-blocking message in the selected language saying the preferences could not be saved and may be asked again next time.
    - 6a3. The survey is not recorded as complete, so it runs again on the next launch.
    - 6a4. Use case ends.
- **\*c. The device has no network connection.**
    - \*c1. No change. The survey needs no network, and both screens work offline (`ROB-offline`).

**Priority:** High

**Frequency of Use:** Once per installation, on each visitor's own device. It runs again only after a reset (`UC-PREF-reset-preferences`) or a retake (`UC-PREF-retake-setup-survey`). If the gallery provides shared tablets (`OI-7`), staff reset each tablet between visitors with `UC-PREF-reset-preferences`, so it runs once per visitor. Every run stays on the device, so it adds no load to any server.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-branding`

**Associated Information:**

_Data fields (stored on the device only; no account, no server):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `language` | enum | Required; one of English, Spanish (`FR-LANG-supported-languages`). Default English. | Device-local; not personal data | — |
| `textSize` | enum | Required; one of Small, Medium, Large (minutes 2026-11-09). Default Medium. | Device-local; not personal data | Font |
| `colorMode` | enum | Required; one of Light, Dark. Default Light (`OI-18`, resolved). | Device-local; not personal data | — |
| `setupSurveyCompleted` | boolean | Required; default `false`. Set to `true` only at step 6, after the three preferences are saved. | Device-local | — |

- **Atomic save.** Step 6 writes all three preferences and the completion flag together, or writes none of them. A failure never leaves the survey marked complete without preferences (see 6a).
- **Live preview.** Each answer is shown on the survey screens as soon as it is chosen. Choosing Spanish at step 3 shows the preferences screen in Spanish, and text size and color mode change that screen as they are selected. The rest of the app takes the preferences only at step 6 (`FR-PREF-apply-everywhere`, "when a visitor confirms"), so leaving the survey early never leaves the app half-changed. `UC-PREF-retake-setup-survey` relies on this so that cancelling a retake has nothing to undo.
- **Language labels.** Each language is named in its own language, so a visitor who reads only Spanish can find theirs.
- **Layout.** The survey has no overlapping or cut-off text at any text size in either language (`USE-text-scaling`). Its screens use Monnig branding, not TCU branding (`BR-monnig-branding`).
- **Accessibility.** Every control must work with the device's screen reader (`USE-screen-reader`), since visually impaired visitors set their preferences here before anything else. The required standard depends on `BR-accessibility-standard` (`OI-3`).
- **Default color mode.** Light (`OI-18`, resolved 2026-11-11). A future version may preselect the device's own light or dark setting instead.
- **Out of scope.** Font style is not asked (dropped unless an accessibility standard requires it, minutes 2026-11-09). The grant's visitor-demographics questions (`BR-visitor-survey-data`, `FR-SURVEY-optional`) are not part of this use case (`OI-10`, `OI-16`).

**Related Use Cases:**

- `UC-PREF-customize-visual-preferences`: Changes the same preferences later, from Settings.
- `UC-PREF-retake-setup-survey`: Runs this survey again from Settings, starting at step 2 with the current preferences preselected. Leaving it before step 6 keeps the existing preferences.
- `UC-PREF-reset-preferences`: Clears the preferences and the survey-complete record, so this use case runs on the next launch (PRE-2).

**Assumptions:**

- The visitor completes or skips the survey before reaching the Home screen. Nothing else in the app is reachable during the survey.
- Preferences belong to the device, not to a person (SRS §7.1, `VisitorPreferences`).
- An adult helps a child visitor who cannot read the survey yet.

**Open Issues:**

- `OI-19`: Will the accessibility standard (`OI-3`) require more questions at setup, such as font style, high contrast, or turning text-to-speech on?


### UC-PREF-customize-visual-preferences: Customize Visual Preferences

**UC ID and Name:** `UC-PREF-customize-visual-preferences`: Customize Visual Preferences

**Created By:** Koen Dolezar (rewrite of Bradley Helmholz's November 3, 2026 draft)

**Date Created:** November 15, 2026

**Primary Actor:** Visitor (including child visitors with an adult's help)

**Secondary Actors:** Gallery staff (on a gallery tablet, if the gallery provides tablets, `OI-7`)

**Trigger:** The visitor selects Settings on the Home screen.

**Description:** After setup, the visitor changes their display preferences one at a time in Settings: language, text size, and light or dark mode. Each change applies to every screen as soon as it is selected and is saved on the device, so there is no separate confirm step. The Settings screen also holds the controls that belong to other use cases: voice speed, captions, retaking the setup survey, and resetting preferences. This use case keeps its original identifier and name, but its content replaces the earlier draft to match later team decisions: Settings is a screen reached from Home, not a popup on every screen (minutes 2026-11-06, 2026-11-09); font style is not offered (minutes 2026-11-09); and text size has three choices.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device (`UC-PREF-first-launch-survey` POST-2), so the Home screen is reachable.
- PRE-2. The visitor is on the Home screen.

**Postconditions:**

- POST-1. The language, text size, and color mode saved on the device are the values last selected in Settings.
- POST-2. Every screen, including screens opened afterward, shows the saved preferences, without restarting the app (`FR-PREF-apply-everywhere`).
- POST-3. On later launches the app restores these preferences (`FR-PREF-persist`, `DI-preferences-on-device`).
- POST-4. No personal information was collected (`DI-no-personal-data`), and no content changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Settings on the Home screen.
2. The system opens the Settings screen, with each control showing the current saved value:
    - Language: English or Spanish, each named in its own language.
    - Text size: Small, Medium, or Large.
    - Color mode: Light or Dark.
    - Voice speed (`UC-TTS-voice-speed`), Captions (`UC-PREF-toggle-captions`), Retake setup survey (`UC-PREF-retake-setup-survey`), and Reset preferences (`UC-PREF-reset-preferences`).
3. The visitor selects a new value for one preference.
4. The system applies the new value at once to the Settings screen and to every other screen, and saves it on the device.
5. The visitor repeats steps 3 and 4 for any other preference, in any order.
6. The visitor selects Home.
7. The system shows the Home screen with the saved preferences applied.
8. Use case ends.

**Extensions:**

- **2a. The saved preferences cannot be read (missing or corrupt).**
    - 2a1. The system shows the default for each preference that cannot be read (English, Medium, Light) and applies those defaults.
    - 2a2. Flow continues at step 3. The defaults are saved only for a preference the visitor then changes.
- **3a. The visitor selects the value that is already selected.**
    - 3a1. Nothing changes and nothing is saved.
    - 3a2. Flow rejoins at step 3.
- **3b. The visitor selects a different language.**
    - 3b1. The system switches all interface text, including the Settings screen itself, to the new language (`FR-LANG-interface-text`). Keyboard and screen-reader focus stay on the language control, so a screen-reader user is not sent back to the top of the screen.
    - 3b2. Meteorite content with no translation in the new language shows in English, marked as not translated (`FR-LANG-content-fallback`).
    - 3b3. Text-to-speech uses the new language the next time anything is read (`UC-TTS-play-in-selected-language`).
    - 3b4. Flow continues at step 4.
- **3c. The visitor selects a voice speed, captions, Retake setup survey, or Reset preferences.**
    - 3c1. The matching use case handles it (`UC-TTS-voice-speed`, `UC-PREF-toggle-captions`, `UC-PREF-retake-setup-survey`, `UC-PREF-reset-preferences`).
    - 3c2. If that use case returns the visitor to Settings, flow rejoins at step 3.
- **4a. Saving the preference fails (for example, the device storage is full).**
    - 4a1. The system keeps the new value applied for as long as the app stays open.
    - 4a2. The system shows a non-blocking message, in the selected language, saying the change could not be saved and will be lost when the app closes.
    - 4a3. The value saved on the device stays as it was.
    - 4a4. Flow rejoins at step 3.
- **6a. The visitor leaves Settings without changing anything.**
    - 6a1. Nothing is saved, and the app looks as it did before.
    - 6a2. Flow continues at step 7.
- **6b. The visitor uses the device's Back action instead of Home.**
    - 6b1. Flow continues at step 7. Every change made in steps 3 to 5 is already saved, so leaving by any route keeps it.
- **\*a. The app is closed or killed by the operating system while Settings is open.**
    - \*a1. Every change already selected was saved at step 4 (except under 4a). On the next launch the app restores the saved preferences and opens at Home.
- **\*b. Text-to-speech was reading on the screen the visitor left to reach Home and Settings.**
    - \*b1. Reading has already stopped, because leaving a screen stops it (`FR-TTS-stop-on-leave`). It does not restart when the visitor returns.
- **\*c. The device has no network connection.**
    - \*c1. No change. Settings needs no network (`ROB-offline`).

**Priority:** High

**Frequency of Use:** Occasional. Most visitors set their preferences once in the first-launch survey; a visitor opens Settings only to change one, perhaps once or twice per visit. Proposed by two team members (minutes 2026-11-09). Every change stays on the device, so it adds no load to any server.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-branding`

**Associated Information:**

_Data fields:_ this use case writes the same stored fields as `UC-PREF-first-launch-survey` (`language`, `textSize`, `colorMode`), under the same validation rules and defaults; they are defined there and not repeated here. It does not write `setupSurveyCompleted`. Voice speed and captions are stored by their own use cases.

- **No confirm step.** Each change applies and saves as soon as it is selected (step 4). This matches voice speed (`UC-TTS-voice-speed`), so every control on the Settings screen behaves the same way. The visitor undoes a change by selecting the old value again. This is the author's decision; the earlier draft's confirm step (its POST-1 and step 9) is dropped.
- **One save per change.** Each preference is saved on its own. A failure saving one never changes another (4a).
- **Live preview.** The Settings screen is itself the preview: it redraws in the new language, text size, or color mode as soon as each is selected.
- **Reaching Settings.** Settings is reached from the Home screen, and Home is reachable from every screen (decision, minutes 2026-11-09). `FR-PREF-settings-reachable` in the SRS still says "one tap from every main screen" and is due to be reworded to match.
- **Layout.** No text on the Settings screen is cut off or overlaps, at every text size in both languages (`USE-text-scaling`). Each control has a screen-reader label that includes its current value, such as "Text size, Medium" (`USE-screen-reader`). The screen follows `CO-monnig-branding`.
- **Out of scope.** Font style is not offered unless an accessibility standard requires it (minutes 2026-11-09, `OI-19`). The first-launch language screen is not shown again; Retake setup survey does that.
- **Systemic failure.** Settings only touches the device, so a network or server failure cannot affect it.

**Related Use Cases:** `UC-PREF-first-launch-survey`

- `UC-PREF-first-launch-survey` _(in review)_: Sets the same three preferences the first time the app opens.
- `UC-PREF-retake-setup-survey` _(in review)_: Runs the setup survey again from this screen.
- `UC-PREF-reset-preferences` _(in review)_: Returns every preference to its default from this screen.
- `UC-PREF-toggle-captions` _(in review)_: Turns captions on or off from this screen.
- `UC-TTS-voice-speed` _(in review)_: Sets the voice speed from this screen.
- `UC-TTS-play-in-selected-language`: Uses the language chosen here for reading aloud.

**Assumptions:**

- Preferences belong to the device, not to a person (SRS §7.1, `VisitorPreferences`).
- The defaults are those of `UC-PREF-first-launch-survey` (English, Medium, Light). If `OI-40` settles different defaults, 2a uses them.
- An adult helps a child visitor who cannot read the Settings screen yet.

**Open Issues:**

- `OI-8`: The SRS and the use cases disagree on whether preferences persist. This use case follows the 2026-11-02 decision that they persist (`FR-PREF-persist`).
- `OI-19`: Whether the accessibility standard requires more settings, such as font style or high contrast.
- `OI-40`: The defaults a preference falls back to when it cannot be read (2a).


### UC-PREF-retake-setup-survey: Retake the Setup Survey

**UC ID and Name:** `UC-PREF-retake-setup-survey`: Retake the Setup Survey

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor (including child visitors with an adult's help)

**Secondary Actors:** None

**Trigger:** The visitor selects "Retake setup survey" in Settings.

**Description:** A visitor who has already finished or skipped the setup survey runs it again on purpose, from Settings. The retake uses the same two screens and the same questions as `UC-PREF-first-launch-survey`, but every question starts with the visitor's current preference selected instead of the default. Each answer is previewed on the survey screens as soon as it is chosen, so the visitor sees the result before moving on, but the rest of the app keeps the current preferences until the visitor finishes. Finishing saves the answers and applies them to every screen; cancelling before then saves nothing and leaves the app as it was. This use case is not Change settings, which edits one preference at a time in Settings, and not `UC-PREF-reset-preferences`, which goes back to the defaults.

**Preconditions:**

- PRE-1. The device has a record of a completed setup survey (`UC-PREF-first-launch-survey` POST-2).
- PRE-2. The visitor is on the Settings screen.

**Postconditions:**

- POST-1. The language, text size, and color mode saved on the device are the values that were selected when the visitor finished, replacing the previous values.
- POST-2. The survey-complete record is still set, so the first-launch survey does not run on the next launch.
- POST-3. Every screen, including screens opened afterward, shows the saved preferences (`FR-PREF-apply-everywhere`).
- POST-4. No personal information was collected (`DI-no-personal-data`).

**Main Success Scenario:**

1. The visitor selects "Retake setup survey" in Settings.
2. The system shows the language screen with the current language selected.
3. The visitor selects a language and continues.
4. The system switches all survey text to that language and shows the preferences screen, with the current text size and current color mode selected. Each choice is shown on the survey screens as soon as it is selected, so the screens themselves are the preview. The rest of the app does not change yet.
5. The visitor selects a text size and a color mode, in either order, and confirms.
6. The system saves the three preferences on the device in place of the previous ones, applies them to every screen (`FR-PREF-apply-everywhere`), and returns the visitor to Settings.
7. Use case ends.

**Extensions:**

- **3a. The visitor continues without changing the selected language.**
    - 3a1. The system keeps the current language.
    - 3a2. Flow continues at step 4.
- **5a. The visitor confirms without changing one or both selected options.**
    - 5a1. The system keeps the current value for each unchanged option.
    - 5a2. Flow continues at step 6.
- **5b. The visitor goes back from the preferences screen to the language screen.**
    - 5b1. The system shows the language screen with the language most recently chosen still selected. It keeps the text size and color mode already chosen.
    - 5b2. Flow rejoins at step 3.
- **\*a. The visitor cancels the retake before step 6, by choosing Cancel on either screen or by going back from the language screen (the on-screen Back control or the device's Back action).**
    - \*a1. The system closes the survey and discards the choices shown on it. Nothing is saved, and the rest of the app was never changed.
    - \*a2. The system returns the visitor to Settings.
    - \*a3. Use case ends.
- **\*b. The app is closed or killed by the operating system before step 6.**
    - \*b1. The system saves nothing. Choices that were only shown on screen are discarded.
    - \*b2. On the next launch, the system restores the previously saved preferences. The survey-complete record is unchanged, so the first-launch survey does not run.
    - _If the app is only sent to the background and then resumed, the retake continues on the same screen with its selections intact._
- **6a. Saving the preferences fails (for example, the device storage is full).**
    - 6a1. The system keeps the new preferences applied for the current session and returns the visitor to Settings.
    - 6a2. The system shows a non-blocking message in the selected language saying the preferences could not be saved and the previous ones will return the next time the app opens.
    - 6a3. The preferences saved on the device stay as they were before the retake.
    - 6a4. Use case ends.
- **\*c. The device has no network connection.**
    - \*c1. No change. The retake needs no network, and both screens work offline (`ROB-offline`).

**Priority:** Low

**Frequency of Use:** Rare. Expected only when a visitor wants to go through every setup question again rather than change one setting; most changes go through Settings. Every run stays on the device, so it adds no load to any server.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-branding`

**Associated Information:**

_Data fields:_ this use case writes the same stored fields as `UC-PREF-first-launch-survey` (`language`, `textSize`, `colorMode`, and the survey-complete record `setupSurveyCompleted`), under the same validation rules; they are defined there and not repeated here. The retake adds no fields of its own.

- **Atomic save.** Step 6 writes all three preferences together, or writes none of them. A failure never leaves a mix of old and new values saved (see 6a). `setupSurveyCompleted` is not written, because it is already `true` (PRE-1).
- **Same screens.** The survey screens, their language labels, the layout rule at every text size (`USE-text-scaling`), and the screen-reader requirement (`USE-screen-reader`) are those of `UC-PREF-first-launch-survey`, with one difference: each screen has a Cancel control (\*a) in place of the first-launch survey's Skip. Any question added to that survey (`OI-19`) appears in the retake as well.
- **Preview stays on the survey.** Choices change only the survey screens until step 6, so cancelling has nothing to undo. Whatever was in effect before the retake, including session-only values after an earlier failed save, stays in effect.
- **Where the visitor ends up.** Settings, because that is where the retake started. The first-launch survey ends on Home instead.

**Related Use Cases:**

- `UC-PREF-first-launch-survey`: Owns the survey screens and questions that this use case runs again.
- `UC-PREF-customize-visual-preferences` (Change settings): Changes one preference at a time in Settings, without the survey.
- `UC-PREF-reset-preferences` _(not yet written)_: Clears the preferences and the survey-complete record, so the first-launch survey runs with defaults on the next launch. The retake keeps the record and starts from the current values.

**Assumptions:**

- Settings is reached from the Home screen (minutes, 2026-11-09), and the "Retake setup survey" control is in Settings. It starts the retake with no confirmation prompt, because nothing is lost until step 6.
- "Current value" means the preference in effect when the retake starts. This is normally the saved value, or a session-only value after a failed save.
- The ID `UC-PREF-reset-preferences` is the one `UC-PREF-first-launch-survey` already uses for a use case not yet written.

**Open Issues:**

- `OI-19`: If the accessibility standard adds setup questions, the retake asks them too.


### UC-PREF-reset-preferences: Reset Preferences

**UC ID and Name:** `UC-PREF-reset-preferences`: Reset Preferences

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum Staff (on gallery-owned devices)

**Trigger:** The user chooses to reset the app in Settings.

**Description:** The user returns every preference on the device to its default, so the next person starts fresh. This is the one general reset agreed on 11/4 and 11/9; it also covers "reset for new visitor" on gallery tablets.

**Preconditions:**

- PRE-1. The user is in Settings, reached from the home screen (`FR-PREF-settings-reachable`).

**Postconditions:**

- POST-1. Language, text size, and light/dark mode are back to their defaults.
- POST-2. The app shows the first-launch setup (`UC-PREF-first-launch-survey`).

**Main Success Scenario:**

1. The user chooses to reset the app.
2. The system asks the user to confirm, and says what will be cleared.
3. The user confirms.
4. The system stops any text-to-speech playback.
5. The system clears all stored preferences on the device.
6. The system shows the first-launch setup.
7. Use case ends.

**Extensions:**

- **3a. The user cancels.**
    - 3a1. The system changes nothing and returns to Settings.
    - 3a2. Use case ends.
- **5a. The system cannot clear the stored preferences.**
    - 5a1. The system keeps the preferences exactly as they were (no partial reset).
    - 5a2. The system tells the user the reset did not complete and to try again.
    - 5a3. Use case ends.

**Priority:** Medium (High if the gallery provides tablets, `OI-7`)

**Frequency of Use:** Rare on a personal phone; once per visitor or group on a gallery tablet.

**Business Rules:**

**Associated Information:** Preferences are stored on the device only (`DI-preferences-on-device`). Nothing is stored on a server, so there is nothing to clear there.

**Related Use Cases:** `UC-PREF-first-launch-survey`, `UC-PREF-customize-visual-preferences`, `UC-DAT-view-favorites`

**Assumptions:** A visitor on their own phone may also reset; the confirmation in step 2 prevents doing it by accident.

**Open Issues:**

- Does reset also clear saved favorites (`UC-DAT-view-favorites`)? On a shared tablet it probably should; on a personal phone it may surprise the user (`OI-41`).
- What are the default settings that reset returns to (`OI-40`)?
- Should the reset on gallery tablets be protected so a visitor cannot trigger it mid-tour? Depends on `OI-7`.


### UC-PREF-toggle-captions: Turn Captions On or Off

**UC ID and Name:** `UC-PREF-toggle-captions`: Turn Captions On or Off

**Created By:** Koen Dolezar

**Date Created:** November 15, 2026

**Primary Actor:** Visitor, especially a visitor who is deaf or hard of hearing, or who is in a noisy group

**Secondary Actors:** None

**Trigger:** The visitor selects the Captions switch in Settings.

**Description:** The visitor turns captions on or off for everything the app plays aloud. The setting is saved on the device and applies to every screen. In release 1.0 the only audio the app plays is text-to-speech, so with captions on, the system highlights the sentence being read on screen and keeps it in view, so the visitor can follow along without hearing it. When the app later plays gallery videos or recorded narration (`FEAT-videos-games`, the audio tour idea in minutes 2026-11-04), the same switch shows their captions. Captions are off by default. Proposed by two team members as a new idea (minutes 2026-11-09).

**Preconditions:**

- PRE-1. The visitor is on the Settings screen (`UC-PREF-customize-visual-preferences` step 2).

**Postconditions:**

- POST-1. The captions setting saved on the device is the value the visitor selected.
- POST-2. Anything read aloud or played afterward, on any screen, follows that setting (`FR-PREF-apply-everywhere`).
- POST-3. On later launches the app restores the setting (`FR-PREF-persist`, `DI-preferences-on-device`).

**Main Success Scenario:**

1. The system shows the Captions switch on the Settings screen with its current value (Off on a new device).
2. The visitor turns captions on.
3. The system saves the setting on the device and updates the switch.
4. The visitor later has content read aloud on another screen (`UC-TTS-listen-to-content`).
5. While reading, the system highlights the sentence being read.
6. Reading ends or stops.
7. The system removes the highlight.
8. Use case ends.

**Extensions:**

- **2a. The visitor turns captions off.**
    - 2a1. The system saves the setting. Text that is read aloud is no longer highlighted.
    - 2a2. Use case ends.
- **3a. Saving the setting fails (for example, the device storage is full).**
    - 3a1. The system keeps the new setting for as long as the app stays open.
    - 3a2. The system shows a non-blocking message, in the selected language, saying the setting could not be saved and will be lost when the app closes.
    - 3a3. Flow continues at step 4.
- **3b. The saved setting cannot be read when the app opens.**
    - 3b1. The system treats captions as Off and shows the switch off.
    - 3b2. Flow rejoins at step 1.
- **5a. The visitor pauses, replays, or skips (`UC-TTS-control-playback`).**
    - 5a1. On pause, the highlight stays on the sentence where reading paused. On replay or skip, the highlight moves with the reading.
    - 5a2. Flow continues at step 5.
- **5b. The speech engine does not report which sentence it is reading.**
    - 5b1. The system highlights the whole passage being read, and still removes the highlight when reading ends.
    - 5b2. Flow continues at step 6.
- **\*a. Media with no captions is played (a later release, when videos or recorded narration exist).**
    - \*a1. The system plays it and shows, once, in the selected language, that captions are not available for it.
- **\*b. The device has no network connection.**
    - \*b1. No change. The setting and the highlighting need no network (`ROB-offline`).

**Priority:** Low

**Frequency of Use:** Rare to change; most visitors who want captions turn them on once. Highlighting runs every time content is read aloud while captions are on. Everything stays on the device, so it adds no load to any server.

**Business Rules:** `BR-accessibility-standard`

**Associated Information:**

_Data fields (stored on the device only; no account, no server):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `captionsOn` | boolean | Required. Default `false`. | Device-local; not personal data | — |

- **Default.** Off, because in release 1.0 the text being read is already on screen. This is the author's decision; the reviewer or the accessibility standard may change it (`OI-42`).
- **Not in the setup survey.** Captions is not asked at first launch (`UC-PREF-first-launch-survey` asks only language, text size, and color mode). If the accessibility standard requires asking, that is `OI-19`.
- **Reset.** `UC-PREF-reset-preferences` returns this setting to Off along with the other preferences.
- **Highlight style.** The highlight must not rely on color alone and must stay readable in light and dark mode at every text size (`USE-text-scaling`); its exact look is left to the design.
- **Screen readers.** The switch's screen-reader label says its state, such as "Captions, off" (`USE-screen-reader`). Highlighting must not move screen-reader focus while the visitor's screen reader is speaking.
- **Language.** Captions are in the language being read, which is the selected language unless the content fell back to English (`FR-LANG-content-fallback`).
- **SRS.** `VisitorPreferences` in SRS §7.2 has no captions field yet; add `captionsOn` when this use case is accepted.

**Related Use Cases:**

- `UC-PREF-customize-visual-preferences`: Customize Visual Preferences. The Captions switch is on its screen.
- `UC-TTS-listen-to-content` _(in review)_: Reads content aloud. Highlighting runs while it reads.
- `UC-TTS-control-playback` _(in review)_: Pause, replay, and skip move the highlight (5b).
- `UC-PREF-reset-preferences` _(in review)_: Returns captions to Off.

**Assumptions:**

- Release 1.0 has no videos and no recorded audio; text-to-speech is the only thing the app plays aloud (SRS §1.2, `FEAT-videos-games` out of MVP).
- The device's speech engine can report its progress through the text on both iOS and Android. Where it cannot, 5c applies.

**Open Issues:**

- `OI-42`: Is highlighting the sentence being read what the gallery means by captions for release 1.0, and should captions default to on? When gallery videos or recorded narration are added, will they come with caption files?
- `OI-3`: Which accessibility standard applies; it may require captions for any future video.


## TTS: Text-to-speech

### UC-TTS-control-playback: Control Text-to-Speech Playback

**UC ID and Name:** `UC-TTS-control-playback`: Control Text-to-Speech Playback

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The device's text-to-speech engine, or a paid speech service (`SI-device-speech`, `DE-device-tts`)

**Trigger:** While text-to-speech is reading aloud or paused on the current screen, the visitor selects Pause, Resume, Replay, Skip forward, or Skip back.

**Description:** Once Listen to content or Narrate an activity has started reading a piece of text aloud, the visitor can pause and resume it, replay it from the beginning, or skip forward or back one paragraph at a time. The controls appear on the screen that is reading, for as long as reading is active, paused, or finished on that screen. There is no Stop control; leaving the screen is what ends reading (`FR-TTS-stop-on-leave`). Starting reading, choosing the voice language, and changing the speed belong to other use cases.

**Preconditions:**

- PRE-1. Text-to-speech, started by `UC-TTS-listen-to-content` or `UC-TTS-narrate-activities`, is reading or paused on the screen the visitor is viewing.
- PRE-2. The text being read has been split into one or more paragraphs.

**Postconditions:**

- POST-1. Reading is in the state the visitor last chose: reading from the start of the chosen paragraph, paused where it stopped, or finished.
- POST-2. Nothing is saved. The reading position is not kept after the visitor leaves the screen or the app closes.

**Main Success Scenario:**

_The visitor may use the controls in any order, any number of times. The steps below use each one once._

1. While the system is reading, the visitor selects Pause.
2. The system pauses reading where it is and shows Resume in place of Pause.
3. The visitor selects Resume.
4. The system continues reading from where it paused and shows Pause again.
5. The visitor selects Skip forward.
6. The system stops reading the current paragraph and starts reading the next paragraph from its beginning.
7. The visitor selects Skip back.
8. The system stops reading the current paragraph and starts reading the previous paragraph from its beginning.
9. The visitor selects Replay.
10. The system starts reading the whole text again from the beginning of the first paragraph.
11. The system reads to the end of the last paragraph, then shows that reading has finished, with Replay still available.
12. Use case ends.

**Extensions:**

- **5a. The visitor selects Skip forward or Skip back while reading is paused.**
    - 5a1. The system moves to the next or previous paragraph and stays paused at its beginning.
    - 5a2. Flow rejoins at step 3; Resume starts reading from that paragraph.
- **5b. The visitor selects Skip forward while reading is paused on the last paragraph.**
    - 5b1. The system shows that reading has finished, as in step 11.
    - 5b2. Use case ends, or rejoins at step 9 if the visitor selects Replay.
- **6a. The current paragraph is the last one.**
    - 6a1. The system stops reading and shows that reading has finished, as in step 11.
    - 6a2. Use case ends, or rejoins at step 9 if the visitor selects Replay.
- **8a. The current paragraph is the first one.**
    - 8a1. The system starts reading the first paragraph again from its beginning.
    - 8a2. Flow continues at step 9.
- **9a. The visitor selects Replay while reading is paused or finished.**
    - 9a1. Flow continues at step 10. Reading starts, whatever state it was in.
- **11a. Reading has finished.**
    - 11a1. The system shows only Replay. Pause, Resume, and the skip controls are not available until reading starts again.
- **\*a. The visitor leaves the screen (Home, Back, or opening another screen).**
    - \*a1. The system stops reading and removes the controls (`FR-TTS-stop-on-leave`). The reading position is not kept.
    - \*a2. Use case ends.
- **\*b. While reading, the app is interrupted: it goes to the background, the device screen locks, a phone call or another app's audio starts, or the audio output is disconnected (wired headphones unplugged, or Bluetooth headphones disconnect).**
    - \*b1. The system pauses reading where it is, as in step 2, so it does not keep reading in the background or continue unexpectedly through the device's speaker.
    - \*b2. When the interruption ends, reading stays paused with Resume shown. It never resumes by itself.
    - \*b3. Flow rejoins at step 3.
- **\*c. The device's volume is muted or turned all the way down.**
    - \*c1. No change. The system keeps reading and does not detect or change the device volume. The visitor raises the volume with the device's own controls.
- **\*d. The speech engine fails while resuming, skipping, or replaying (an engine error, or the voice for the selected language is no longer available).**
    - \*d1. The system stops reading and shows a message in the selected language saying reading could not continue. It does not read in a different language (`SI-device-speech`).
    - \*d2. The system keeps Replay available, and the rest of the screen stays usable.
    - \*d3. If the visitor selects Replay and the engine works, flow rejoins at step 10. Otherwise use case ends.

**Priority:** High

**Frequency of Use:** Several times each time Listen to content is used, for visitors who use text-to-speech, in the gallery or remotely. With the device's built-in speech engine it adds no network load. With a paid speech service (`DE-device-tts`), each Replay or skip may be a new request to that service.

**Business Rules:** `BR-accessibility-standard`

**Associated Information:**

_Data fields (held in memory on the device for the screen that is reading; never saved):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `playbackState` | enum | Required; one of Reading, Paused, Finished. Set by `UC-TTS-listen-to-content` when reading starts, then by this use case. | Memory only | — |
| `paragraphs` | ordered list of text | Required; at least one item. Split from the text at its paragraph breaks; text with no breaks is a single paragraph (`OI-21`). | Memory only | — |
| `currentParagraph` | integer | Required; from 0 to the number of paragraphs minus 1. | Memory only | — |
| `pausedAt` | position within the current paragraph | Set at Pause; cleared by any skip or Replay. | Memory only | — |

- **Controls.** Pause and Resume share one place on screen, and only one shows at a time. Every control has a label that the device's screen reader reads (`USE-screen-reader`), is labeled in the selected language (`FR-LANG-interface-text`), and stays usable at every text size (`USE-text-scaling`). Placement is left to the design.
- **Other settings.** Changes from Voice speed and Play in selected language apply to whatever is read after a skip or Replay. This use case does not change them.
- **Resume position.** Resume continues from `pausedAt`. Whether every platform's speech engine can resume mid-paragraph is open (`OI-22`).
- **Screen reader.** The device's screen reader (VoiceOver, TalkBack) and the app's text-to-speech can both speak. What the accessibility standard requires when they overlap is open (`OI-20`).
- **Systemic failure.** This use case makes no durable change, so a failure leaves nothing to roll back (see \*d).

**Related Use Cases:**

- `UC-TTS-listen-to-content`: Listen to Content. Starts reading aloud. This use case controls reading that it started (PRE-1).
- `UC-TTS-narrate-activities`: Narrate an Activity. Reads an activity's instructions and prompts aloud. This use case controls that narration too (PRE-1).
- `UC-TTS-voice-speed`: Change Voice Speed. Changes the reading speed.
- `UC-TTS-play-in-selected-language`: Play in Selected Language. Picks the voice for the selected language.

**Assumptions:**

- There is no separate Stop control (`UC-TTS-listen-to-content`). Pause meets the requirement that the visitor can stop reading (`FR-TTS-read-description`), and leaving the screen ends reading (\*a). This use case covers Pause, Resume, Replay, and Skip.
- Skip back always goes to the start of the previous paragraph, even in the middle of the current one; it does not first restart the current paragraph.
- Skipping while paused keeps reading paused (5a).
- The item's name is not part of the text this use case controls. Listen to content reads only the description; reading the name aloud is its own use case, not yet written.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-3`: Which accessibility standard applies.
- `OI-20`: Does the accessibility standard require more from these controls?
- `OI-21`: Does the text being read come with paragraph breaks?
- `OI-22`: Is resuming from the start of the paragraph acceptable where a speech engine cannot resume mid-paragraph?


### UC-TTS-listen-to-content: Listen to Content

**UC ID and Name:** `UC-TTS-listen-to-content`: Listen to Content

**Created By:** Cody Pinkston

**Date Created:** November 12, 2026

**Primary Actor:** Visitor or Remote Visitor

**Secondary Actors:** The device's text-to-speech engine, or a paid speech service (`SI-device-speech`, `DE-device-tts`)

**Trigger:** On a screen that shows a meteorite, a gallery section, or an exhibit, the visitor selects Listen.

**Description:** A visitor who cannot or would rather not read the screen has the app read the content aloud. The app reads the item's description, in the selected language, from start to finish. Once reading starts, the visitor can pause, resume, replay, or skip by paragraph (`UC-TTS-control-playback`). There is no separate Stop control: Pause silences reading, and leaving the screen ends it (`FR-TTS-stop-on-leave`). Changing the reading speed belongs to `UC-TTS-voice-speed`. The voice always uses the language selected in preferences.

**Preconditions:**

- PRE-1. The visitor is viewing a meteorite view (`UC-DAT-view-meteorite`), a gallery section screen (`UC-TOUR-browse-gallery-section`), or an exhibit screen (`UC-TOUR-view-exhibit`), and its content has loaded.
- PRE-2. The content shown has a description. It is not missing or shown as "[NOT INDICATED]".
- PRE-3. Text-to-speech is not already reading or paused on this screen.

**Postconditions:**

- POST-1. Text-to-speech has read the item's description aloud in the selected language, and shows that reading has finished with Replay available. If the visitor paused it, it stays paused until they resume it or leave the screen. If the visitor left the screen, reading has ended.
- POST-2. Nothing is saved. The reading position is not kept after the visitor leaves the screen or the app closes.
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Listen.
2. The system checks that the description is available in the selected language.
3. The system prepares the text to read: the description, split into paragraphs at its paragraph breaks.
4. The system checks that the speech engine has a voice for the selected language.
5. The system starts reading the first paragraph from its beginning, at the current voice speed. It replaces Listen with the playback controls (`UC-TTS-control-playback`).
6. The system reads each paragraph in order, to the end of the last paragraph.
7. The system shows that reading has finished, with Replay available, as in `UC-TTS-control-playback` step 11.
8. Use case ends.

**Extensions:**

- **2a. The description has no translation in the selected language (the screen shows the English text marked as not translated, `FR-LANG-content-fallback`).**
    - 2a1. The system does not read. It shows a message in the selected language saying this description is not available in that language, so it cannot be read aloud. It does not read the English text (`SI-device-speech`).
    - 2a2. Listen stays available, and the rest of the screen stays usable.
    - 2a3. Use case ends.
- **3a. The description has no paragraph breaks.**
    - 3a1. The system treats the whole description as one paragraph (`OI-21`).
    - 3a2. Flow continues at step 4.
- **4a. The speech engine has no voice for the selected language.**
    - 4a1. The system does not read. It shows a message in the selected language saying a voice for this language is not available on this device. It does not read in a different language (`SI-device-speech`).
    - 4a2. Listen stays available, and the rest of the screen stays usable.
    - 4a3. Use case ends.
- **5a. The speech engine fails to start (an engine error, or a paid speech service cannot be reached, `DE-device-tts`).**
    - 5a1. The system shows a message in the selected language saying reading could not start. No playback controls are shown.
    - 5a2. Listen stays available, and the rest of the screen stays usable.
    - 5a3. If the visitor selects Listen again, flow rejoins at step 2. Otherwise use case ends.
- **6a. The visitor uses the playback controls (Pause, Resume, Replay, Skip forward, Skip back).**
    - 6a1. `UC-TTS-control-playback` handles them.
    - 6a2. Flow continues at step 6 from wherever that use case leaves reading, or at step 7 if it finished.
- **7a. After reading has finished, the visitor selects Replay.**
    - 7a1. `UC-TTS-control-playback` step 10 handles it, and flow rejoins at step 6.
- **\*a. The visitor leaves the screen (Home, Back, closing the meteorite detail, opening Settings, or opening another screen).**
    - \*a1. The system stops reading and removes the playback controls (`FR-TTS-stop-on-leave`). The reading position is not kept.
    - \*a2. Use case ends. On returning to the screen, Listen is shown and reading starts from the beginning if selected.
- **\*b. While reading, the app goes to the background, the screen locks, a call or another app's audio interrupts, the headphones disconnect, or the speech engine fails.**
    - \*b1. `UC-TTS-control-playback` \*b and \*d handle it. Reading pauses or stops as that use case says, and never resumes by itself.
- **\*c. The device's volume is muted or turned all the way down.**
    - \*c1. No change. The system reads anyway and does not detect or change the device volume, as in `UC-TTS-control-playback` \*c.
- **\*d. The device's screen reader (VoiceOver, TalkBack) is on.**
    - \*d1. No change. Listen is a labeled control that the screen reader can activate (`USE-screen-reader`). The system does not silence the screen reader. What the accessibility standard requires when both speak is open (`OI-20`).

**Priority:** High

**Frequency of Use:** For visitors who use text-to-speech, once for most items they open, in the gallery or remotely, so many times per visit. A visit runs about 30 to 60 minutes. With the device's built-in speech engine it adds no network load. With a paid speech service (`DE-device-tts`), each Listen is at least one request to that service.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-funds-costs`

**Associated Information:**

_Data fields (held in memory on the device for the screen that is reading; never saved). They exist only from step 5 until the visitor leaves the screen; before Listen is selected there is no reading state at all. `UC-TTS-control-playback` uses the same fields:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `paragraphs` | ordered list of text | Required; at least one item. The description split at its paragraph breaks (3a). Built at step 3 from the text in the selected language only (2a). | Memory only | — |
| `playbackState` | enum | One of Reading, Paused, Finished. Reading at step 5; Finished at step 7. `UC-TTS-control-playback` sets Paused and Reading. | Memory only | — |
| `currentParagraph` | integer | Required; from 0 to the number of paragraphs minus 1. Set to 0 at step 5. | Memory only | — |

_Content read (read-only to visitors, from the screen's own use case):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `description` | long text, per language | Required (PRE-2); must exist in the selected language (2a) | Read-only to visitors | — |

- **Where Listen appears.** One Listen control on each meteorite detail, gallery section, and exhibit screen, shown only when PRE-2 holds. While reading is active, paused, or finished, the playback controls take its place (`UC-TTS-control-playback`). Listen returns only when the visitor leaves the screen and comes back. Placement is left to the design.
- **Controls.** Listen has a label that the device's screen reader reads (`USE-screen-reader`), is labeled in the selected language (`FR-LANG-interface-text`), and stays usable at every text size (`USE-text-scaling`). Messages in 2a, 4a, and 5a are also in the selected language and can be read by the screen reader.
- **Language.** The voice is always the selected language. Text with no translation in the selected language is never read, even though the screen shows it in English (2a).
- **Speed.** Reading uses the voice speed in effect when step 5 starts (`UC-TTS-voice-speed`). This use case does not change it.
- **One reader at a time.** Only the screen the visitor is viewing can be reading, because leaving a screen stops reading (\*a).
- **Systemic failure.** This use case makes no durable change, so a failure leaves nothing to roll back (see 4a, 5a, \*b).

**Related Use Cases:**

- `UC-TTS-control-playback`: Control Text-to-Speech Playback. Pause, Resume, Replay, and Skip for the reading this use case starts (6a, 7a, \*b).
- `UC-DAT-view-meteorite`: View a Meteorite. One of the screens Listen appears on.
- `UC-TOUR-browse-gallery-section`: Browse a Gallery Section. The gallery section screen, one of the screens Listen appears on.
- `UC-TOUR-view-exhibit`: View an Exhibit. The exhibit screen, one of the screens Listen appears on.
- `UC-TTS-voice-speed`: Change Voice Speed. Sets the speed this use case reads at.
- `UC-TTS-play-in-selected-language`: Play in Selected Language. Picks the voice for the selected language (step 4, 4a).

**Assumptions:**

- This use case replaces the empty legacy entry `UC-TTS-read-display-contents`, which has been removed from the Use Case List.
- Only the item's description is read (minutes 2026-11-09: "Reads exhibit and meteorite descriptions aloud"). The name and other fields on a meteorite detail screen (type, location found, date found) are not read; visitors who need them use the device's screen reader.
- There is no Stop control. Pause meets the requirement that the visitor can stop reading (`FR-TTS-read-description`); Replay starts over; leaving the screen discards the reading position (\*a).
- After reading finishes, Replay replaces Listen until the visitor leaves the screen, matching `UC-TTS-control-playback` 11a.
- Other text in the app (Home, Settings, lists, activities) is not read by this use case. What else must be readable depends on the accessibility standard (`OI-3`).

**Open Issues:**

- `OI-3`: Which accessibility standard applies, and what else it requires to be readable.
- `OI-20`: What the accessibility standard requires when the screen reader and the app's text-to-speech both speak.
- `OI-21`: Does the text being read come with paragraph breaks?
- `OI-25`: Is the gallery section screen in release 1.0? If not, Listen appears only on the meteorite detail screen (and the exhibit screen, if that is in 1.0).
- `OI-26`: Do visitors' devices reliably have a Spanish voice installed, and if not, should the app tell them how to add one?


### UC-TTS-voice-speed: Change Voice Speed

**UC ID and Name:** `UC-TTS-voice-speed`: Change Voice Speed

**Created By:** Bradley Helmholz

**Date Created:** November 12, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The device's text-to-speech engine, or a paid speech service (`SI-device-speech`, `DE-device-tts`)

**Trigger:** The visitor opens Settings and changes the voice speed.

**Description:** The visitor sets how fast text-to-speech reads aloud, from half speed (0.5x) to double speed (2x), with a slider or by typing a number. The slider and the number box always show the same value. The new speed is used the next time anything is read aloud, and is kept on the device. Starting and controlling reading (`UC-TTS-listen-to-content`, `UC-TTS-control-playback`) and choosing the voice language belong to other use cases.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so Settings is reachable (`FR-PREF-settings-reachable`).

**Postconditions:**

- POST-1. The voice speed is the value the visitor set, between 0.5x and 2x, or it is unchanged if the visitor did not set one.
- POST-2. The speed is saved on the device and used for all later reading, until the visitor changes it (`FR-PREF-persist`, `DI-preferences-on-device`).
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor opens Settings.
2. The system shows the text-to-speech section with the current voice speed on a slider and in a number box. A new device starts at 1x.
3. The visitor moves the slider to a new speed.
4. The system updates the number box to match and saves the new speed.
5. The visitor leaves Settings.
6. Use case ends. The next reading, started by Listen, uses the new speed.

**Extensions:**

- **3a. The visitor types a speed in the number box instead.**
    - 3a1. The system checks that the value is a number from 0.5 to 2 and, if so, moves the slider to match.
    - 3a2. Flow continues at step 4.
- **3b. The typed value is not a number, or is outside 0.5 to 2.**
    - 3b1. The system keeps the last valid speed, puts it back in the number box, and shows a message in the selected language saying the speed must be between 0.5x and 2x (`FR-LANG-interface-text`).
    - 3b2. Flow rejoins at step 3.
- **3c. The visitor clears the number box and leaves it empty.**
    - 3c1. The system treats it as 3b.
- **3d. The visitor sets the speed back to 1x.**
    - 3d1. Flow continues at step 4. The system saves 1x like any other value.
- **4a. The speed cannot be saved on the device.**
    - 4a1. The system keeps the new speed for as long as the app stays open and shows a message saying it could not be saved. It will not be there after the app closes.
    - 4a2. Flow continues at step 5.
- **4b. The speech engine cannot read at the chosen speed.**
    - 4b1. The system uses the closest speed the engine supports when it next reads, and keeps the visitor's chosen value on screen (`OI-33`).
    - 4b2. Flow continues at step 5.
- **\*a. The visitor opens Settings while text-to-speech is reading.**
    - \*a1. Reading has already stopped, because leaving the screen stops it (`FR-TTS-stop-on-leave`). Flow continues at step 1. Reading is not restarted when the visitor goes back.

**Priority:** Medium

**Frequency of Use:** Rarely. A visitor who uses text-to-speech sets it about once, then may adjust it a few times if the pace is too fast or too slow. The setting is kept between visits on the same device.

**Business Rules:** `BR-accessibility-standard`

**Associated Information:**

_Data field (saved on the visitor's device only):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `voiceSpeed` | decimal number, in multiples of normal speed | Required; from 0.5 to 2.0, in steps of 0.1 (`OI-34`). User can only manually input 3 characters maximum. Invalid numbers are rejected and leave the field as blank. Default 1.0. Slider and number box show the same value. | Stored on the device only; no personal data (`DI-preferences-on-device`, `DI-no-personal-data`) | — |

- **Controls.** The slider and the number box each have a label the device's screen reader reads, including the current value (`USE-screen-reader`), are labeled in the selected language (`FR-LANG-interface-text`), and stay usable at every text size (`USE-text-scaling`). Placement within Settings is left to the design.
- **When it applies.** The speed is read by Listen when reading starts, so a change takes effect on the next reading, not on one in progress (`UC-TTS-listen-to-content` step 5). Skip and Replay in `UC-TTS-control-playback` also use the current speed.
- **Systemic failure.** The only change is one saved number, so a failure leaves the old speed (see 4a).

**Related Use Cases:**

- `UC-TTS-listen-to-content`: Listen to Content. Starts reading at the speed set here (step 5).
- `UC-TTS-control-playback`: Control Text-to-Speech Playback. Skip and Replay use the current speed.
- `UC-PREF-customize-visual-preferences`: Customize Visual Preferences. The other part of Settings; whether the two share a confirm step is open (`OI-35`).
- `UC-TTS-play-in-selected-language`: Play in Selected Language. Picks the voice for the selected language.

**Assumptions:**

- The range is 0.5x to 2x, from the 11-09 minutes ("about 0.5x to 2x") and the team's choice of a slider and a typed value.
- 1x is normal speed, and is the default.
- The speed is saved the moment it is set, with no separate confirm step (`OI-35`).
- The speed applies to every voice and language the same way.
- There is no sample or "test voice" button; the visitor hears the speed the next time they use Listen.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.
- `UC-TTS-voice-speed` is the ID the `UC-TTS-listen-to-content` and `UC-TTS-control-playback` drafts already use for this use case. Those two are on unmerged branches, and this draft was written against them as they stand there.

**Open Issues:**

- `OI-33`: Can the device's speech engine, or a paid speech service (`DE-device-tts`), read at every speed from 0.5x to 2x? If not, what should the app do?
- `OI-34`: Is a step of 0.1x right for the slider and the number box?
- `OI-35`: Should the voice speed apply as soon as it is set, or only after a confirm step like `UC-PREF-customize-visual-preferences`, and should it also have a sample to listen to?


### UC-TTS-narrate-activities: Narrate an Activity

**UC ID and Name:** `UC-TTS-narrate-activities`: Narrate an Activity

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor (especially child visitors and pre-readers)

**Secondary Actors:** Museum Staff, teachers and chaperones

**Trigger:** The user starts an interactive activity (for example a scavenger hunt or quiz) with narration turned on.

**Description:** The system reads each step of an activity aloud, in the selected language, so visitors who cannot read yet, or who prefer listening, can take part. The client said pre-readers (Kinder to 2nd) need picture- and sound-based activities (interview, §5).

**Preconditions:**

- PRE-1. The user has opened an interactive activity.
- PRE-2. Narration is turned on for the user.

**Postconditions:**

- POST-1. Every instruction and prompt in the activity has been read aloud to the user, or the user chose to stop narration.

**Main Success Scenario:**

1. The user starts the activity.
2. The system reads the activity's instructions aloud in the selected language.
3. The system reads the first step's prompt aloud.
4. The user completes the step.
5. The system reads the result of the step and the next step's prompt aloud.
6. Steps 4 and 5 repeat until the last step.
7. The system reads the activity's closing message aloud.
8. Use case ends.

**Extensions:**

- **2a. The device has no voice for the selected language.**
    - 2a1. The system tells the user that narration is not available in that language.
    - 2a2. The activity continues with text only.
    - 2a3. Use case ends.
- **3a. The user asks to hear the prompt again.**
    - 3a1. The system reads the current prompt again.
    - 3a2. Rejoin at step 4.
- **4a. The user turns narration off.**
    - 4a1. The system stops reading and the activity continues with text only.
    - 4a2. Use case ends.
- **\*a. The user leaves the activity at any step.**
    - \*a1. The system stops reading (`FR-TTS-stop-on-leave`).
    - \*a2. Use case ends.

**Priority:** Low for release 1.0; interactive features come after the core app (`FEAT-scavenger-hunt`, `FEAT-quizzes` are out of MVP scope).

**Frequency of Use:** Every time a narrated activity is played.

**Business Rules:** `BR-accessibility-standard`

**Associated Information:** Uses the text-to-speech engine in `SI-device-speech` (`DE-device-tts`). Pause, replay, and speed are covered by `UC-TTS-control-playback` and `UC-TTS-voice-speed`.

**Related Use Cases:** `UC-TTS-listen-to-content`, `UC-TTS-control-playback`

**Assumptions:** Interactive activities exist in a later release; this use case is written now so it is ready when they do (minutes, 2026-11-02, versioned use cases).

**Open Issues:**

- Which activities will exist, and is narration on by default for them?
- Does every piece of activity text need narration, or only instructions and prompts? Depends on the accessibility standard (`OI-3`).


### UC-TTS-play-in-selected-language: Play in Selected Language

**UC ID and Name:** `UC-TTS-play-in-selected-language`: Play in Selected Language

**Created By:** Bradley Helmholz

**Date Created:** November 13, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The text-to-speech engine (`SI-device-speech`, `DE-device-tts`)

**Trigger:** The visitor starts text-to-speech reading, for example by selecting Listen (`UC-TTS-listen-to-content`).

**Description:** Text-to-speech always reads in the language the visitor chose for the app, English or Spanish (`FR-LANG-supported-languages`). There is no separate voice language setting. When reading starts, the system finds a voice for the selected language and reads in it. If there is no voice for that language, the system does not read in a different language (`SI-device-speech`). It tells the visitor that a voice is not available. Where the voices come from is not decided (`DE-device-tts`, `OI-26`), so this use case says only that the text-to-speech engine supplies them. Checking that the text exists in the selected language, starting and controlling playback, and changing the speed belong to other use cases.

**Preconditions:**

- PRE-1. A language is selected, either chosen in the setup survey or the English default (`UC-PREF-first-launch-survey`).
- PRE-2. A use case that reads aloud is starting reading, and has already checked that the text to read exists in the selected language (`UC-TTS-listen-to-content` step 2).

**Postconditions:**

- POST-1. Reading has started in a voice for the selected language, or has not started and the visitor has been told why.
- POST-2. Text is never read in a language other than the selected one.
- POST-3. Nothing is saved. The voice chosen is not kept after the visitor leaves the screen (`FR-TTS-stop-on-leave`).

**Main Success Scenario:**

1. The visitor starts reading aloud.
2. The system reads the selected language from the visitor's preferences.
3. The system asks the text-to-speech engine for its voices for that language.
4. The engine returns one or more voices.
5. The system picks a voice and starts reading in it.
6. Use case ends. Reading continues as `UC-TTS-listen-to-content` and `UC-TTS-control-playback` describe.

**Extensions:**

- **3a. The engine cannot supply its voices (an engine error, or the engine cannot be reached).**
    - 3a1. The system does not read. It shows a message in the selected language saying reading could not start (`FR-DATA-load-failure`). The rest of the screen stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2. Otherwise use case ends.
- **4a. The engine has no voice for the selected language.**
    - 4a1. The system does not read, and does not read in a different language (`SI-device-speech`). It shows a message in the selected language saying a voice for this language is not available (`OI-26`, `OI-37`).
    - 4a2. The reading control stays available, and the rest of the screen stays usable.
    - 4a3. If the visitor tries again, flow rejoins at step 2. Otherwise use case ends.
- **4b. The engine returns more than one voice.**
    - 4b1. The system picks the voice the engine marks as its default for that language. If none is marked, it picks the first voice returned (`OI-36`).
    - 4b2. Flow continues at step 5.
- **4c. The only voice is a regional variant of the selected language, such as Spanish for Spain.**
    - 4c1. The system uses it. It is still the selected language (`OI-36`).
    - 4c2. Flow continues at step 5.
- **5a. The voice cannot start, for example it became unavailable after step 4.**
    - 5a1. Flow continues at 4a1.
- **\*a. The visitor changes the app language in Settings.**
    - \*a1. Reading has already stopped, because opening Settings leaves the screen (`FR-TTS-stop-on-leave`). Nothing from the old language carries over.
    - \*a2. The next reading starts at step 1 and uses the new language. Reading is not restarted for the visitor.

**Priority:** High

**Frequency of Use:** Every time reading starts, so for visitors who use text-to-speech, many times a visit, in the gallery or remotely. Spanish-speaking visitors depend on it to hear any Spanish content aloud.

**Business Rules:** `BR-accessibility-standard`

**Associated Information:**

_Data fields (held in memory on the device only; never saved):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `language` | enum | Defined in `UC-PREF-first-launch-survey`. Read from the visitor's preferences; this use case never changes it. | Stored on the device only (`DI-preferences-on-device`) | — |
| `availableVoices` | list of voices, each with a name and a language | Returned by the engine at step 4; may be empty (see 4a) | Memory only | — |
| `chosenVoice` | one voice | Required to read; its language matches `language` | Memory only | — |

- **Language.** The voice language and the text language are both the selected language. A missing translation is handled before this use case runs (`UC-TTS-listen-to-content` 2a), so the voice is never asked to read English text in a Spanish voice, or the reverse.
- **Messages.** The messages in 3a and 4a are in the selected language (`FR-LANG-interface-text`), can be read by the device's screen reader (`USE-screen-reader`), and stay readable at every text size (`USE-text-scaling`).
- **Systemic failure.** Nothing is saved, so a failure leaves nothing to undo (see 3a, 4a).

**Related Use Cases:**

- `UC-TTS-listen-to-content`: Listen to Content. Starts the reading this use case finds a voice for. Its 2a and 4a are the failure cases this use case matches.
- `UC-TTS-narrate-activities`: Narrate an Activity. Also starts reading, and needs a voice the same way.
- `UC-TTS-control-playback`: Control Text-to-Speech Playback. Skip and Replay use the voice chosen here.
- `UC-TTS-voice-speed`: Change Voice Speed. The speed the chosen voice reads at.
- `UC-PREF-first-launch-survey` and `UC-PREF-customize-visual-preferences`: where the visitor sets the language this use case follows.

**Assumptions:**

- There is no separate voice language setting. The voice follows the app language (decision for this draft; the other TTS drafts assume the same).
- English and Spanish are the only languages in release 1.0 (`FR-LANG-supported-languages`).
- Where the engine and its voices come from, whether the device's own or a paid service, is not decided (`DE-device-tts`, `OI-26`). Nothing here depends on the answer.
- Names in the text, such as a meteorite's name, are read by the selected language's voice as it pronounces them.
- Listen's 4a and this use case's 4a describe the same case. This draft keeps them the same so they cannot disagree, and the two authors can merge them.

**Open Issues:**

- `OI-26`: Do visitors' devices reliably have a Spanish voice, and if not, what should the app do?
- `OI-36`: Which voice should the app prefer when the engine returns several for the selected language, and which Spanish (for example US or Mexican) fits a Texas audience?
- `OI-37`: What should the "voice not available" message say, in each language, and should it tell the visitor how to get a voice once `OI-26` is decided?


## DAT: Meteorite database

### UC-DAT-browse-database: Browse the Meteorite Database

**UC ID and Name:** `UC-DAT-browse-database`: Browse the Meteorite Database

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects the Meteorite Database on the Home screen.

**Description:** The visitor opens the list of every meteorite in the Monnig collection, on display or not, and scrolls through it in alphabetical order by name. The list loads in batches as the visitor scrolls, so the first meteorites appear without waiting for the whole collection of about 3,000 to load (`SCA-full-collection`). Selecting a meteorite opens it in View meteorite. Searching, filtering, and showing only items on display are separate use cases. This use case replaces `UC-DAT-display-database`, which has been removed.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the Home screen is reachable.

**Postconditions:**

- POST-1. The list shows the meteorites loaded so far, sorted A to Z by name.
- POST-2. If the visitor selected a meteorite, View meteorite has opened with that meteorite's `monnigNumber`.
- POST-3. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`, `DI-catalog-source-of-truth`).

**Main Success Scenario:**

1. The visitor selects the Meteorite Database on the Home screen.
2. The system opens the Meteorite Database screen, shows that the list is loading, and requests the first batch of meteorites from the catalog, sorted A to Z by name.
3. The catalog returns the batch.
4. The system shows the list. Each item shows the meteorite's name and its first image, or a placeholder image if it has none.
5. The visitor scrolls down the list.
6. As the visitor nears the end of the loaded items, the system requests the next batch from the catalog and adds it to the end of the list without moving the visitor's place. Steps 5 and 6 repeat as the visitor keeps scrolling.
7. The visitor selects a meteorite.
8. The system opens the selected meteorite in View meteorite.
9. Use case ends.

**Extensions:**

- **2a. The device has no network connection, and the app has loaded catalog data before (`ROB-offline`).**
    - 2a1. The system shows the meteorites it already has, in the same order, with a notice that the list may be incomplete while offline.
    - 2a2. Flow continues at step 4. When the visitor reaches the end of those meteorites, step 6 fails as in 6a.
- **3a. The catalog cannot be reached (including when the device is offline and has no meteorites loaded yet), returns an error, or returns only part of the first batch.**
    - 3a1. The system shows a message saying the meteorites could not be loaded, with a way to try again (`FR-DATA-load-failure`). The rest of the app, including Home and Settings, stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2.
    - 3a3. Otherwise the visitor leaves the screen, and use case ends.
- **3b. The catalog returns no meteorites at all.**
    - 3b1. The system shows a message saying there are no meteorites to show, instead of an empty list.
    - 3b2. Use case ends.
- **3c. A returned record is missing a field the list shows, or is malformed.**
    - 3c1. A record with no name shows "[NOT INDICATED]" as its name and can still be selected (`FR-DATA-missing-field`).
    - 3c2. A record that cannot be read at all is left out, and the rest of the batch is shown. The app does not crash (`ROB-no-crash-on-bad-data`).
    - 3c3. Flow continues at step 4.
- **4a. A meteorite's image fails to load, or is still loading.**
    - 4a1. The system shows the placeholder image in its place. The item can still be selected.
    - 4a2. Flow continues at step 5.
- **6a. The next batch cannot be loaded.**
    - 6a1. The system keeps every meteorite already shown, and shows at the end of the list that more could not be loaded, with a way to try again (`FR-DATA-load-failure`).
    - 6a2. If the visitor tries again, flow rejoins at step 6. The visitor can still select any meteorite already shown (step 7).
- **6b. Every meteorite has been loaded.**
    - 6b1. The system makes no more requests, and the list ends after the last meteorite.
    - 6b2. Flow continues at step 7.
- **8a. The visitor comes back from View meteorite.**
    - 8a1. The system shows the list at the same place, without reloading the meteorites already loaded.
    - 8a2. Flow rejoins at step 5.
- **\*a. The visitor chooses to search or filter the list.**
    - \*a1. The system hands off to Search database or Filter database.
    - \*a2. Use case ends.
- **\*b. The visitor leaves the Meteorite Database screen for Home.**
    - \*b1. Use case ends. The next time the visitor opens the list, it starts again at the top.

**Priority:** High

**Frequency of Use:** Expected at least once in most visits, in the gallery or remotely (`OE-remote-use`). Each open requests one batch, plus one more for each batch the visitor scrolls into. In the gallery, up to about 30 visitors in one group may do this at the same time (`SCA-group-concurrency`).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields (read from the catalog; visitors cannot change them). Definitions are in the SRS §7.2 data dictionary; this table says how this use case uses them:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `monnigNumber` | text | Required and unique (SRS §7.2). Not shown in the list. It identifies the meteorite handed to View meteorite and breaks ties in the sort order. | Read-only to visitors | Monnig # |
| `meteoriteName` | text | Required (SRS §7.2). Shown, and is the sort key. If missing, it shows "[NOT INDICATED]" (`FR-DATA-missing-field`). | Read-only to visitors | Meteorite Name |
| `images` | list of Image | Optional. The list shows only the first image, or a placeholder if there are none. | Read-only to visitors; image rights are open (`OI-15`) | — |

- **Sort order.** A to Z by `meteoriteName`, ignoring upper and lower case. Meteorites with the same name are ordered by `monnigNumber`. Meteorites with no name come last. Names are not translated (SRS §10), so the order is the same in English and Spanish.
- **Batches.** The batch size is left to the design. It must let the first screen of results meet `PER-database-list` (threshold TBD, `OI-13`).
- **Scale.** The list covers the whole collection, not only items on display (`SCA-full-collection`, `BO-display-collection`).
- **Accessibility.** Each item's screen-reader label is the meteorite's name (`USE-screen-reader`). Every item stays readable at every text size (`USE-text-scaling`).
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), steps 2, 3, and 6 read from that copy, and 3a and 6a happen only when the copy cannot be read or refreshed.
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-view-meteorite` _(in review)_: View a Meteorite. Opens the meteorite selected at step 7.
- `UC-DAT-search-database` _(in review)_: Search the Meteorite Database. Reached from this list (\*a).
- `UC-DAT-filter-database` _(in review)_: Filter the Meteorite Database. Reached from this list (\*a).
- `UC-DAT-view-on-display-items` _(in review)_: View Meteorites on Display. Lists only the meteorites on display.
- `UC-DAT-save-favorite` _(in review)_: Save a Favorite Meteorite. Saving a favorite happens there, not from this list.
- `UC-DAT-display-database`: Replaced by this use case and removed.

**Assumptions:**

- The list has one item per catalog record. If the catalog holds several samples of the same meteorite, its name appears more than once (see `OI-4` on meteorite versus sample).
- List items have no favorite control. Favoriting belongs to Save favorite.
- The list keeps its place only while the visitor goes to View meteorite and comes back (8a). Leaving for Home resets it (\*b).

**Open Issues:**

- `OI-4`: Where the meteorite data comes from, and whether the catalog distinguishes a meteorite from its samples.
- `OI-12`: Whether the full list must be readable offline. Today only data already loaded is promised (`ROB-offline`).
- `OI-13`: The load-time threshold for `PER-database-list`.


### UC-DAT-search-database: Search the Meteorite Database

**UC ID and Name:** `UC-DAT-search-database`: Search the Meteorite Database

**Created By:** Koen Dolezar

**Date Created:** November 15, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects the search box at the top of the Meteorite Database screen.

**Description:** The visitor types part of a meteorite's name to find it in the full collection of about 3,000 meteorites, on display or not (`SCA-full-collection`). Results update as the visitor types, and selecting one opens it in View meteorite. Search works together with any active filters (`UC-DAT-filter-database`): the list shows only meteorites that match both. Clearing the search returns the visitor to the full list.

**Preconditions:**

- PRE-1. The visitor is on the Meteorite Database screen (`UC-DAT-browse-database`) or the On Display screen (`UC-DAT-view-on-display-items`).

**Postconditions:**

- POST-1. The list shows the meteorites whose names match the search text and the active filters, or a no-results message.
- POST-2. If the visitor selected a meteorite, View meteorite has opened with that meteorite's `monnigNumber`.
- POST-3. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`, `DI-catalog-source-of-truth`).

**Main Success Scenario:**

1. The visitor selects the search box.
2. The system shows the keyboard and keeps the current list on screen.
3. The visitor types part of a meteorite's name.
4. When the visitor pauses typing, the system requests from the catalog the meteorites whose names match the text and the active filters, and shows that results are loading.
5. The catalog returns the matches.
6. The system replaces the list with the matches, sorted as described under Associated Information, and shows how many were found. Each item shows the meteorite's name and its first image, as in the Meteorite Database list.
7. The visitor selects a meteorite.
8. The system opens the selected meteorite in View meteorite.
9. Use case ends.

**Extensions:**

- **3a. The visitor keeps typing or deletes characters.**
    - 3a1. The system cancels any request still waiting for the older text, so results for old text never replace newer ones.
    - 3a2. Flow rejoins at step 4.
- **3b. The visitor clears the search box, or selects the clear control.**
    - 3b1. The system shows the list as it was before the search, with any active filters still applied.
    - 3b2. Use case ends.
- **3c. The search text is only spaces.**
    - 3c1. The system treats it as empty, as in 3b.
- **3d. The visitor types more than 100 characters.**
    - 3d1. The system accepts no more characters.
    - 3d2. Flow continues at step 4.
- **4a. The device has no network connection, and the app has catalog data loaded already (`ROB-offline`).**
    - 4a1. The system searches only the meteorites it already has and shows a notice that results may be incomplete while offline.
    - 4a2. Flow continues at step 6.
- **5a. The catalog cannot be reached, returns an error, or returns only part of the results.**
    - 5a1. The system shows a message saying the search could not be completed, with a way to try again (`FR-DATA-load-failure`). The search text stays in the box.
    - 5a2. If the visitor tries again, flow rejoins at step 4.
    - 5a3. Otherwise, the visitor can change the text (3a) or clear it (3b).
- **5b. No meteorite matches.**
    - 5b1. The system shows a message, in the selected language, saying no meteorites match the search. If filters are active, the message says so and offers to clear them (`FR-DATA-no-results`).
    - 5b2. The visitor changes the text (3a), clears it (3b), or clears the filters, after which flow rejoins at step 4.
- **5c. A matching record has no name or cannot be read.**
    - 5c1. As `UC-DAT-browse-database` 3c: a record with no name cannot match a name search; a record that cannot be read is left out, and the app does not crash (`ROB-no-crash-on-bad-data`).
- **6a. There are more matches than fit in one batch.**
    - 6a1. The system loads them in batches as the visitor scrolls, as `UC-DAT-browse-database` steps 5 and 6 describe.
    - 6a2. Flow continues at step 7.
- **6b. A result's image fails to load, or is still loading.**
    - 6b1. The system shows the placeholder image in its place. The item can still be selected.
- **6c. The visitor opens or changes filters while a search is active.**
    - 6c1. `UC-DAT-filter-database` handles it, keeping the search text. Flow rejoins at step 4 with the new filters.
- **8a. The visitor comes back from View meteorite.**
    - 8a1. The system shows the same search text and results, at the same place in the list, without searching again.
    - 8a2. Flow rejoins at step 7.
- **\*a. The visitor leaves the screen for Home.**
    - \*a1. The search text is cleared. The next time the visitor opens the list, it starts without a search.
    - \*a2. Use case ends.

**Priority:** High

**Frequency of Use:** Several times per visit for most visitors who use the collection, in the gallery or remotely (`OE-remote-use`). Proposed by two team members (minutes 2026-11-09). Each pause in typing sends at most one request. In the gallery, up to about 30 visitors in one group may search at the same time (`SCA-group-concurrency`).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `searchText` | text | Optional. Up to 100 characters. Leading and trailing spaces are ignored. Not stored after the visitor leaves the screen. | Never sent anywhere except the catalog request; not logged | — |
| `meteoriteName` | text | Read from the catalog (SRS §7.2). The only field matched. | Read-only to visitors | Meteorite Name |
| `monnigNumber` | text | Read from the catalog. Not matched or shown; identifies the meteorite handed to View meteorite. | Read-only to visitors | Monnig # |

- **What matches.** A meteorite matches if its name contains the search text anywhere, ignoring upper and lower case, accents, spaces, and hyphens. "sikhote alin" matches "Sikhote-Alin", and "gibeon" matches "Gibeon". Only the name is searched in release 1.0 (author's decision); searching by Monnig # depends on `OI-43`.
- **Sort order.** Names that start with the search text come first, then names that contain it elsewhere. Within each group, A to Z by name, then by `monnigNumber`, as in `UC-DAT-browse-database`.
- **When it searches.** After the visitor stops typing for a short pause (the length is left to the design) or presses the keyboard's search key. The first character starts a search; there is no minimum length.
- **Names are not translated** (SRS §10), so the same text finds the same meteorites in English and Spanish.
- **Accessibility.** The search box has a screen-reader label, and the result count is announced when results change (`USE-screen-reader`). The box and results stay readable at every text size (`USE-text-scaling`).
- **Performance.** Results must appear within `PER-filter-response` (threshold TBD, `OI-13`), which applies to search as well as filters.
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), search runs on that copy, and 5a happens only when the copy cannot be read.
- **Privacy.** The search text is not saved or used for anything else (`DI-no-personal-data`).
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-browse-database` _(in review)_: Browse the Meteorite Database. The search box is on its screen.
- `UC-DAT-filter-database`: Filter the Meteorite Database. Search and filters combine.
- `UC-DAT-view-on-display-items` _(in review)_: View on-display items. The same search box searches only items on display there.
- `UC-DAT-view-meteorite` _(in review)_: View a Meteorite. Opens the meteorite selected at step 7.

**Assumptions:**

- Visitors know, or can read off a display label, at least part of a meteorite's name.
- One list item per catalog record, as in `UC-DAT-browse-database`.

**Open Issues:**

- `OI-43`: Do the gallery's display labels show the Monnig # or another number a visitor could type to find a meteorite? If so, search should match it as well as the name.
- `OI-4`: Where the meteorite data comes from, which decides whether search runs on the catalog or on the app's own copy.
- `OI-13`: The response-time threshold for `PER-filter-response`.


### UC-DAT-filter-database: Filter the Meteorite Database

**UC ID and Name:** `UC-DAT-filter-database`: Filter the Meteorite Database

**Created By:** Koen Dolezar (rewrite of the 2022 draft by Asa Tuten and Bradley Helmholz)

**Date Created:** November 15, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects Filter at the top of the Meteorite Database screen.

**Description:** The visitor narrows the list of meteorites to those that match one or more filters: class, group, composition, country found, year found, and whether the meteorite is on display. Every filter starts at "All". The visitor sets filters in a panel and applies them together; the list then shows only meteorites that match every filter set, and any search text (`UC-DAT-search-database`). This use case keeps its identifier but replaces the 2022 draft, to match the current data dictionary (SRS §7.2), the browse and search use cases, and `FR-DATA-no-results`.

**Preconditions:**

- PRE-1. The visitor is on the Meteorite Database screen (`UC-DAT-browse-database`) or the On Display screen (`UC-DAT-view-on-display-items`).

**Postconditions:**

- POST-1. The applied filters are the ones the visitor applied, and the Filter control shows how many are active.
- POST-2. The list shows only meteorites that match every applied filter and the search text, or the no-results message (`FR-DATA-no-results`).
- POST-3. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`, `DI-catalog-source-of-truth`).

**Main Success Scenario:**

1. The visitor selects Filter.
2. The system opens the filter panel, showing each filter with its applied value ("All" if none):
    - Class: Iron, Stone, Stony-iron. Any number can be selected.
    - Group: Chondrite, Primitive achondrite, Achondrite. Any number can be selected.
    - Composition: the values the catalog holds (`OI-4`). Any number can be selected.
    - Country found: a list of the countries the catalog holds, which narrows as the visitor types. Any number can be selected.
    - Year found: a range from the earliest to the latest year in the catalog, set with a two-handle slider or by typing the two years.
    - On display only: a switch, off by default.
3. The visitor changes one or more filters, in any order.
4. The visitor selects Apply.
5. The system closes the panel, requests from the catalog the meteorites that match the applied filters and any search text, and shows that the list is loading.
6. The catalog returns the matches.
7. The system shows the matching meteorites, sorted A to Z by name, with the number found, and shows the number of active filters on the Filter control.
8. The visitor selects a meteorite.
9. The system opens it in View meteorite.
10. Use case ends.

**Extensions:**

- **2a. The list of composition or country values cannot be loaded.**
    - 2a1. The system shows that filter as unavailable, with a way to try again. The other filters still work.
    - 2a2. Flow continues at step 3.
- **3a. The visitor types a year range where the first year is after the second, or a year outside the catalog's range or in the future.**
    - 3a1. The system shows a message, in the selected language, beside the year fields saying what is allowed, and disables Apply until the range is valid.
    - 3a2. Flow rejoins at step 3.
- **3b. The visitor types in the country list and no country matches.**
    - 3b1. The system shows that no country matches. Nothing is selected.
    - 3b2. Flow rejoins at step 3.
- **3c. The visitor selects Clear all.**
    - 3c1. The system sets every filter in the panel back to "All". Nothing changes in the list until the visitor applies.
    - 3c2. Flow rejoins at step 3.
- **4a. The visitor closes the panel without applying.**
    - 4a1. The system discards the changes made in the panel. The filters that were applied before stay applied, and the list does not change.
    - 4a2. Use case ends.
- **4b. The visitor applies with every filter at "All".**
    - 4b1. The system removes all filters, and the list shows every meteorite (with any search text still applied). The Filter control shows no count.
    - 4b2. Flow continues at step 5.
- **5a. The device has no network connection, and the app has catalog data loaded already (`ROB-offline`).**
    - 5a1. The system filters only the meteorites it already has and shows a notice that the results may be incomplete while offline.
    - 5a2. Flow continues at step 7.
- **6a. The catalog cannot be reached, returns an error, or returns only part of the results.**
    - 6a1. The system shows a message saying the meteorites could not be loaded, with a way to try again (`FR-DATA-load-failure`). The applied filters are kept.
    - 6a2. If the visitor tries again, flow rejoins at step 5. Otherwise the visitor can change the filters (step 1) or leave.
- **6b. No meteorite matches every applied filter.**
    - 6b1. The system shows "No meteorites match current filters." in place of the list (`FR-DATA-no-results`), with a control to clear all filters.
    - 6b2. If the visitor clears them, flow continues at step 5 with no filters. Otherwise the visitor can change the filters (step 1).
- **6c. A meteorite has no value for a field that a filter is set on.**
    - 6c1. It does not match that filter, because the catalog does not say. It still appears when that filter is at "All".
- **7a. There are more matches than fit in one batch.**
    - 7a1. The system loads them in batches as the visitor scrolls, as `UC-DAT-browse-database` steps 5 and 6 describe.
- **9a. The visitor comes back from View meteorite.**
    - 9a1. The system shows the same filtered list at the same place, without loading it again.
    - 9a2. Flow rejoins at step 8.
- **\*a. The visitor leaves the screen for Home.**
    - \*a1. The system clears the filters. The next time the visitor opens the list, it starts with every filter at "All", the same as search (`UC-DAT-search-database` \*a).
    - \*a2. Use case ends.

**Priority:** Medium

**Frequency of Use:** Less often than browsing or searching; a few times per visit by visitors who want one kind of meteorite. Proposed by two team members (minutes 2026-11-09). Each Apply sends one request. In the gallery, up to about 30 visitors in one group may filter at the same time (`SCA-group-concurrency`).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields (read from the catalog; visitors cannot change them). Definitions are in the SRS §7.2 data dictionary; this table says how this use case filters on them:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `class` | enum | Filter: any of Iron, Stone, Stony-iron. Labels shown in the selected language. | Read-only to visitors | Class |
| `group` | enum | Filter: any of Chondrite, Primitive achondrite, Achondrite (list to confirm, SRS §7.2). Labels shown in the selected language. | Read-only to visitors | Group |
| `composition` | text | Filter: any of the values the catalog holds. Allowed values TBD (`OI-4`). Shown as stored. | Read-only to visitors | — |
| `country` | text | Filter: any of the countries the catalog holds. Shown as stored. | Read-only to visitors | Country |
| `dateFound` | date or year | Filter: by year only, from and to inclusive. From is not after To; neither is in the future. Precision TBD (`OI-4`). | Read-only to visitors | — |
| `onDisplay` | boolean | Filter: when the switch is on, only `true`. | Read-only to visitors | — |

- **How filters combine.** Within one filter, selected values are joined by OR (Iron or Stony-iron). Across filters, and with the search text, they are joined by AND.
- **Changes from the 2022 draft.** Location filters by country only; `locationFound` is free text and too varied to filter, but it is still shown in View meteorite. Closing the panel without applying keeps the filters already applied, rather than resetting them all (old 7a). The old 2a is covered by 4a.
- **Values come from the data.** The composition and country lists, and the ends of the year range, come from the catalog, not from a list kept in the app, so new finds appear without an app update (`MNT-content-update`).
- **Accessibility.** Every filter control has a screen-reader label that says its current value, and the year range can be set by typing as well as by dragging, so it works with a screen reader (`USE-screen-reader`). The panel stays readable at every text size (`USE-text-scaling`).
- **Performance.** The filtered list must appear within `PER-filter-response` (threshold TBD, `OI-13`) over the full collection (`SCA-full-collection`).
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), filtering runs on that copy, and 6a happens only when the copy cannot be read.
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-browse-database` _(in review)_: Browse the Meteorite Database. The Filter control is on its screen. It supersedes `UC-DAT-display-database`.
- `UC-DAT-search-database` _(in review)_: Search the Meteorite Database. Search and filters combine.
- `UC-DAT-view-on-display-items` _(in review)_: View on-display items. Filters there work the same, with On display only fixed on.
- `UC-DAT-view-meteorite` _(in review)_: View a Meteorite. Opens the meteorite selected at step 8.

**Assumptions:**

- The catalog holds class, group, composition, country, year found, and on-display values for most meteorites (`AS-catalog-data-sufficient`). A filter whose field the catalog lacks entirely is left out of the panel until it does.
- One list item per catalog record, as in `UC-DAT-browse-database`.

**Open Issues:**

- `OI-4`: Which fields the catalog holds, the allowed composition values, and how precise the find dates are.
- `OI-13`: The response-time threshold for `PER-filter-response`.
- `OI-44`: Where "on display" comes from and who keeps it current (shared with `UC-DAT-view-on-display-items`).


### UC-DAT-view-meteorite: View a Meteorite

**UC ID and Name:** `UC-DAT-view-meteorite`: View a Meteorite

**Created By:** Cody Pinkston

**Date Created:** November 12, 2026

**Primary Actor:** Visitor or Remote Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects a meteorite in any list that shows meteorites: the Meteorite Database list, search or filter results, favorites, on-display items, an exhibit, or similar meteorites.

**Description:** The visitor opens one meteorite to see what the gallery knows about it: its name, its classification (class, group, composition), where and when it was found and whether its fall was observed, its description, and its pictures. If the gallery has a 3D scan of the meteorite, the 3D model takes the place of the main picture. The visitor can swipe through the photos and open any of them full screen. From this view the visitor can also have the description read aloud, save the meteorite as a favorite, open similar meteorites, or turn the 3D model; each of those is its own use case. Whether the view is a full screen or a popup over the list is left to the design. This use case replaces `UC-DAT-display-meteorite`, which has been removed.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the app's main screens are reachable.
- PRE-2. The visitor is on a screen that lists meteorites (see Trigger), and the list shows at least one meteorite.
- PRE-3. The selected meteorite has a `monnigNumber`.

**Postconditions:**

- POST-1. The view has shown the selected meteorite's details, images, and actions, for the `monnigNumber` the visitor selected.
- POST-2. When the visitor closes the view, they are back on the screen they came from, at the same place in its list.
- POST-3. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`, `DI-catalog-source-of-truth`). Saving a favorite, if the visitor did, is stored as `UC-DAT-save-favorite` says.

**Main Success Scenario:**

1. The visitor selects a meteorite.
2. The system opens the meteorite view, shows the meteorite's name and that its details are loading, and requests the meteorite's record from the catalog by its `monnigNumber`.
3. The catalog returns the record.
4. The system shows the meteorite:
    - the hero: the 3D model if the meteorite has a 3D scan, otherwise its first photo;
    - its name;
    - its classification: class, group, and composition;
    - its find details: country, location found, date found, and whether its fall was observed;
    - its description;
    - a swipeable gallery of its photos, starting with the hero;
    - the Listen, Save favorite, and View similar controls.
5. The visitor swipes through the photos.
6. The system shows the next or previous photo, and indicates which photo of how many is showing.
7. The visitor closes the meteorite view.
8. The system returns to the screen the visitor came from, at the same place, without reloading it.
9. Use case ends.

**Extensions:**

- **2a. The device has no network connection, and the app already has this meteorite's record (`ROB-offline`).**
    - 2a1. The system shows the record it has, with a notice that the details may be out of date while offline. Photos and the 3D model it does not already have are handled as in 4b and 4c.
    - 2a2. Flow continues at step 4.
- **2b. The device has no network connection, and the app does not have this meteorite's record.**
    - 2b1. As in 3a.
- **3a. The catalog cannot be reached, returns an error, or returns only part of the record.**
    - 3a1. The system shows, in the view, a message saying the meteorite's details could not be loaded, with a way to try again (`FR-DATA-load-failure`). The view can still be closed, and the rest of the app stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2.
    - 3a3. Otherwise flow continues at step 7.
- **3b. The catalog has no record for this `monnigNumber` (for example, it was removed after the list was loaded).**
    - 3b1. The system shows a message saying this meteorite is no longer available, instead of the details.
    - 3b2. Flow continues at step 7.
- **3c. The record is missing a field the view shows, or a field cannot be read.**
    - 3c1. The system shows "[NOT INDICATED]" in place of that field's value and shows every field that has a value (`FR-DATA-missing-field`). A field that cannot be read is treated as missing, and the app does not crash (`ROB-no-crash-on-bad-data`).
    - 3c2. If the name is missing, "[NOT INDICATED]" is shown as the name.
    - 3c3. If the description is missing, "[NOT INDICATED]" is shown in its place, and Listen is not shown (`UC-TTS-listen-to-content` PRE-2).
    - 3c4. Flow continues at step 4.
- **4a. The meteorite has no photos and no 3D scan.**
    - 4a1. The system shows a placeholder image as the hero, and no photo gallery.
    - 4a2. Flow continues at step 7.
- **4b. The meteorite has a 3D scan, but the 3D model fails to load or is still loading.**
    - 4b1. The system shows the first photo as the hero in its place, or the placeholder image if there are no photos. The rest of the view stays usable.
    - 4b2. When the 3D model finishes loading, the system replaces the hero with it without moving the visitor's place in the view.
    - 4b3. Flow continues at step 5.
- **4c. A photo fails to load, or is still loading.**
    - 4c1. The system shows the placeholder image in that photo's place. The other photos can still be swiped to.
    - 4c2. Flow continues at step 5.
- **4d. The description has no translation in the selected language.**
    - 4d1. The system shows the English description marked as not translated (`FR-LANG-content-fallback`, `OI-9`). All labels stay in the selected language (`FR-LANG-interface-text`).
    - 4d2. Flow continues at step 5.
- **5a. The meteorite has only one photo, or only a 3D model.**
    - 5a1. The system shows no gallery controls. Flow continues at step 7.
- **5b. The visitor selects a photo.**
    - 5b1. The system shows the photo full screen, using the framework's default image view (Flutter's default). No custom zoom or pan is required.
    - 5b2. The visitor closes the full-screen photo.
    - 5b3. Flow rejoins at step 5.
- **5c. The visitor turns or zooms the 3D model.**
    - 5c1. `UC-DAT-view-3d-model` handles it.
    - 5c2. Flow rejoins at step 5.
- **5d. The visitor selects Listen.**
    - 5d1. `UC-TTS-listen-to-content` handles it. Reading stops when the visitor closes the view (`FR-TTS-stop-on-leave`).
    - 5d2. Flow rejoins at step 5.
- **5e. The visitor selects Save favorite.**
    - 5e1. `UC-DAT-save-favorite` handles it.
    - 5e2. Flow rejoins at step 5.
- **5f. The visitor selects View similar.**
    - 5f1. `UC-DAT-view-similar-meteorites` handles it. If the visitor selects a similar meteorite there, this use case starts again for that meteorite.
    - 5f2. When the visitor comes back, the system shows this meteorite again without reloading it, and flow rejoins at step 5.
- **\*a. The visitor closes the view while its details are still loading.**
    - \*a1. The system stops waiting for the record and returns to the screen the visitor came from, as in step 8.
    - \*a2. Use case ends.
- **\*b. The visitor goes to Home or Settings instead of closing the view.**
    - \*b1. Use case ends. Any reading aloud stops (`FR-TTS-stop-on-leave`). Preference changes made in Settings apply to every screen afterward (`FR-PREF-apply-everywhere`).

**Priority:** High

**Frequency of Use:** Many times per visit, in the gallery or remotely (`OE-remote-use`); it is the most-proposed Data use case (minutes, 2026-11-09). Each open is one request for the record, plus the photos and 3D model. In the gallery, up to about 30 visitors in one group may do this at the same time (`SCA-group-concurrency`).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields (read from the catalog; visitors cannot change them). Definitions are in the SRS §7.2 data dictionary; this table says how this use case uses them:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `monnigNumber` | text | Required and unique (SRS §7.2). Not shown. It identifies the record requested at step 2. | Read-only to visitors | Monnig # |
| `meteoriteName` | text | Required (SRS §7.2). Shown at step 2 from the list, then from the record. Not translated (SRS §10). | Read-only to visitors | Meteorite Name |
| `class` | enum | Optional. Iron, Stone, or Stony-iron, shown in the selected language. | Read-only to visitors | Class |
| `group` | enum | Optional. Chondrite, Primitive achondrite, or Achondrite (list to confirm, SRS §7.2), shown in the selected language. | Read-only to visitors | Group |
| `composition` | text | Optional. Allowed values TBD (`OI-4`). Shown as stored. | Read-only to visitors | — |
| `country` | text | Optional. Shown as stored. | Read-only to visitors | Country |
| `locationFound` | text | Optional. Shown as stored. | Read-only to visitors | — |
| `dateFound` | date or year | Optional. Shown only to the precision the catalog holds (a year alone if that is all it has), in the date format of the selected language (SRS §10). Precision TBD (`OI-4`). | Read-only to visitors | — |
| `fall` | boolean | Optional. Shown as whether the fall was observed; the wording is left to the design. | Read-only to visitors | Fall |
| `description` | long text, per language | Optional. Shown in the selected language, or per 4d. | Read-only to visitors | — |
| `images` | list of Image | Optional. In the order the catalog gives. The first is the hero unless there is a 3D model. | Read-only to visitors; image rights are open (`OI-15`) | — |
| `model3D` | 3D scan | Optional. When present, it is the hero. Format and source TBD (`OI-27`). Not yet in SRS §7.2. | Read-only to visitors | — |

- **Not shown.** The Monnig # and whether the meteorite is on display are not shown in this view (author's decision, 2026-11-12).
- **Missing values.** How "[NOT INDICATED]" is styled is left to the design. It must not rely on color alone (`USE-accessibility-standard`).
- **Hero.** The 3D model, when there is one, replaces the main picture; it does not add a second hero. Turning and zooming the model belong to `UC-DAT-view-3d-model`.
- **Photo gallery.** Swipeable, starting at the hero, with an indicator of which photo of how many is showing. Selecting a photo shows it full screen in the platform's default image view (5b).
- **Accessibility.** Every photo, the 3D model, and every control has a screen-reader label (`USE-screen-reader`); a photo with no caption is labeled with the meteorite's name and its position, such as "photo 2 of 4". Every field stays readable at every text size, in both languages (`USE-text-scaling`). Swiping has a non-gesture alternative, such as next and previous buttons, so it works with a screen reader.
- **Performance.** The details must be complete within `PER-detail-load` (threshold TBD, `OI-13`). The name and text fields should not wait for photos or the 3D model to load (4b, 4c).
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), steps 2 and 3 read from that copy, and 3a happens only when the copy cannot be read.
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-browse-database`: Browse the Meteorite Database. Opens a meteorite here at its step 7.
- `UC-DAT-search-database`: Search database. Its results open a meteorite here.
- `UC-DAT-filter-database`: Organize Meteorite Catalog Based on Filters. Its results open a meteorite here.
- `UC-DAT-view-favorites`: View favorites. Opens a saved meteorite here.
- `UC-DAT-view-on-display-items`: View on-display items. Opens a meteorite here.
- `UC-TOUR-view-exhibit`: View exhibit. Opens a meteorite in the display here.
- `UC-DAT-view-similar-meteorites`: View similar meteorites. Reached from this view (5f), and opens a meteorite here.
- `UC-DAT-save-favorite`: Save favorite. Reached from this view (5e).
- `UC-DAT-view-3d-model`: View 3D model. Turning and zooming the hero 3D model (5c).
- `UC-TTS-listen-to-content`: Listen to Content. Reads the description aloud (5d).
- `UC-DAT-display-meteorite`: Replaced by this use case and removed.

**Assumptions:**

- One view per catalog record. If the catalog holds several samples of the same meteorite, each opens its own view (see `OI-4` on meteorite versus sample).
- Class, group, and the fall value are a fixed list, so they are shown in the selected language. Free-text values (composition, country, location found) are shown as the catalog stores them, untranslated.
- Opening a meteorite from a meteorite view (5f) stacks views: closing returns to the previous meteorite, not to the original list.
- If a 3D model cannot load, the first photo takes its place (4b). The visitor is not told a 3D model exists until it loads.

**Open Issues:**

- `OI-4`: Where the meteorite data comes from, which fields it has (composition values, date precision), and whether it distinguishes a meteorite from its samples.
- `OI-9`: Whether machine translation of descriptions is acceptable, and who reviews it.
- `OI-12`: Whether a meteorite's details must be readable offline. Today only data already loaded is promised (`ROB-offline`).
- `OI-13`: The load-time threshold for `PER-detail-load`.
- `OI-15`: Who owns the meteorite photos, and what credit they need.
- `OI-27`: Which meteorites have 3D scans, in what file format, who owns them, and where they will be hosted for the app?
- `OI-28`: Which meteorites will have a written description in release 1.0, and who writes and approves them? The catalog may not hold descriptions (SRS §7.4).


### UC-DAT-save-favorite: Save a Favorite Meteorite

**UC ID and Name:** `UC-DAT-save-favorite`: Save a Favorite Meteorite

**Created By:** Cody Pinkston

**Date Created:** November 13, 2026

**Primary Actor:** Visitor or Remote Visitor

**Secondary Actors:** None. Favorites are stored only on the visitor's device.

**Trigger:** In the meteorite view, the visitor selects the Save favorite control (`UC-DAT-view-meteorite` 5e).

**Description:** While looking at a meteorite, the visitor marks it as a favorite so they can find it again later in View favorites. The control is a toggle: it saves the meteorite if it is not a favorite and removes it if it is. Favorites are stored on the device by `monnigNumber`, with no account, and are kept across app launches. The meteorite view is the only place a favorite can be saved. Shared favorites or leaderboards need a back end and come later (minutes, 2026-11-09).

**Preconditions:**

- PRE-1. The meteorite view is showing a meteorite's details (`UC-DAT-view-meteorite` step 4), so the Save favorite control is on screen.

**Postconditions:**

- POST-1. If the meteorite was not a favorite, its `monnigNumber` is now in the device's favorites list. If it was a favorite, its `monnigNumber` is no longer in the list.
- POST-2. The Save favorite control shows the meteorite's new state (saved or not saved).
- POST-3. The change is kept on the device across app launches until the visitor changes it again or the app is uninstalled.
- POST-4. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Save favorite in the meteorite view.
2. The system checks the device's favorites list and finds that this meteorite's `monnigNumber` is not in it.
3. The system adds the `monnigNumber` to the favorites list and saves the list on the device.
4. The system changes the control to a filled star. No text is shown on screen. The screen reader announces that the meteorite was saved to favorites.
5. The visitor stays in the meteorite view, at the same place. Flow returns to `UC-DAT-view-meteorite` step 5.
6. Use case ends.

**Extensions:**

- **2a. The meteorite is already in the favorites list.**
    - 2a1. The system removes the `monnigNumber` from the favorites list and saves the list on the device.
    - 2a2. The system changes the control to an outlined (unfilled) star. No text is shown on screen. The screen reader announces that the meteorite was removed from favorites.
    - 2a3. Flow continues at step 5.
- **\*a. The favorites list cannot be read or saved (for example, the device storage is full).**
    - \*a1. The system shows a message, in the selected language, saying the favorite could not be saved or removed. The message does not cover the star.
    - \*a2. The favorites list on the device stays as it was, and the control keeps its previous state.
    - \*a3. Flow continues at step 5.
- **\*b. The device has no network connection.**
    - \*b1. No change. Favorites are stored only on the device, so saving and removing work offline (`ROB-offline`).

**Priority:** Low. It is among the lowest-priority use cases and can be left off if time runs out (minutes, 2026-11-11).

**Frequency of Use:** Occasional. Visitors who use favorites select it a few times per visit, in the gallery or remotely (`OE-remote-use`). Every save stays on the device, so it adds no load to any server.

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields (stored on the device only; no account, no server):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `favorites` | list of `monnigNumber` | Starts empty. Each `monnigNumber` appears at most once. No limit on the number of favorites (author's decision, 2026-11-13). Only the `monnigNumber` is stored; anything View favorites shows about a meteorite comes from the catalog (author's decision, 2026-11-13). | Device-local. Never sent off the device (`DI-no-personal-data`). | Monnig # |

- **Persistence.** Favorites are kept across app launches. In v1.0, only uninstalling the app clears them; the one general reset (`UC-PREF-reset-preferences`, minutes 2026-11-09) does not, since v1.0 assumes visitors' own phones (`AS-visitor-own-device`). Whether the reset should clear favorites on shared gallery tablets is open (`OI-7`, `OI-41`). `DI-preferences-on-device` mentions only preferences, so the SRS needs to add favorites to it.
- **Control.** The Save favorite control is a star icon with no visible text on or around it: filled when the meteorite is a favorite, outlined when it is not (author's decision, 2026-11-15). The filled-versus-outlined shape shows the state without relying on color alone (`USE-accessibility-standard`). The star has a screen-reader label that is never shown on screen, "Save favorite" or "Remove favorite" in the selected language (`USE-screen-reader`, `FR-LANG-interface-text`). Its placement is left to the design.

**Related Use Cases:**

- `UC-DAT-view-meteorite`: View a Meteorite. Holds the Save favorite control and invokes this use case at 5e.
- `UC-DAT-view-favorites`: View Favorite Meteorites. Lists the saved meteorites, opens each in `UC-DAT-view-meteorite`, and can remove a favorite from the same device list (its 5a).
- `UC-DAT-browse-database`: Browse the Meteorite Database. Its list items have no favorite control.
- `UC-PREF-reset-preferences`: Reset preferences. Does not clear favorites in v1.0 (`OI-41`).

**Assumptions:**

- Favorites belong to the device, not to a person, like `VisitorPreferences` (SRS §7.1).
- One favorite per catalog record (`monnigNumber`). If the catalog holds several samples of one meteorite, each is favorited separately (`OI-4`).

**Open Issues:**

- `OI-7`: Whether the gallery provides shared tablets.
- `OI-41`: Whether the reset clears favorites, for example on shared tablets.
- `OI-4`: Whether the catalog distinguishes a meteorite from its samples, which decides what one favorite refers to.


### UC-DAT-view-3d-model: View a Meteorite's 3D Model

**UC ID and Name:** `UC-DAT-view-3d-model`: View a Meteorite's 3D Model

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** None

**Trigger:** While viewing a meteorite, the user chooses to view its 3D model.

**Description:** The user turns and zooms a 3D model of a meteorite to see it from every side, including meteorites that are not on display. Depends on 3D scans of meteorites being made (minutes, 2026-11-04).

**Preconditions:**

- PRE-1. The user is viewing a single meteorite (`UC-DAT-view-meteorite`).
- PRE-2. That meteorite has a 3D model. If it has none, the option is not offered.

**Postconditions:**

- POST-1. The user has viewed the model and is returned to the meteorite's details.

**Main Success Scenario:**

1. The user chooses to view the 3D model.
2. The system loads the model.
3. The system shows the model in its default position.
4. The user rotates the model.
5. The system turns the model to match.
6. The user zooms in or out.
7. The system zooms the model, within set limits.
8. The user closes the model.
9. The system returns to the meteorite's details.
10. Use case ends.

**Extensions:**

- **2a. The model cannot be loaded.**
    - 2a1. The system shows a message and offers to try again (`FR-DATA-load-failure`).
    - 2a2. The meteorite's details stay available.
    - 2a3. Use case ends.
- **3a. The device cannot display 3D models.**
    - 3a1. The system says so and shows the meteorite's photos instead.
    - 3a2. Use case ends.
- **7a. The user asks to reset the view.**
    - 7a1. The system returns the model to its default position.
    - 7a2. Rejoin at step 4.

**Priority:** Low (depends on 3D scans existing)

**Frequency of Use:** Occasionally, for meteorites that have a model.

**Business Rules:**

**Associated Information:** A 3D model cannot be read by a screen reader, so every model needs a text description as well (`USE-screen-reader`). Models may be large; loading over cellular data in the gallery affects `PER-detail-load`.

**Related Use Cases:** `UC-DAT-view-meteorite`

**Assumptions:** Someone produces 3D scans and the gallery approves their use.

**Open Issues:**

- Which meteorites have 3D scans, in what format, who owns them, and where are they hosted (`OI-27`)?
- What is the largest acceptable model file to download over cellular data?
- Who writes the text description for each model, since a screen reader can't read the model itself (`OI-38`)?


### UC-DAT-view-favorites: View Favorite Meteorites

**UC ID and Name:** `UC-DAT-view-favorites`: View Favorite Meteorites

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** None

**Trigger:** The user chooses to view their favorites.

**Description:** The user sees the list of meteorites they saved as favorites on this device, and can open or remove any of them. Favorites are saved on the device only for now (minutes, 2026-11-09).

**Preconditions:**

- PRE-1. The user has opened the application and passed the home screen.

**Postconditions:**

- POST-1. The system shows every meteorite the user saved as a favorite on this device.

**Main Success Scenario:**

1. The user chooses to view favorites.
2. The system reads the saved favorites from the device.
3. The system retrieves the current information for each favorite from the database.
4. The system shows the favorites, each with its name and picture if one exists.
5. The user selects a favorite to see it in detail (`UC-DAT-view-meteorite`).
6. Use case ends.

**Extensions:**

- **2a. The user has no saved favorites.**
    - 2a1. The system says there are no favorites yet and explains how to save one.
    - 2a2. Use case ends.
- **3a. The system cannot reach the database.**
    - 3a1. The system shows the saved names it already has on the device and a message that details could not be loaded (`FR-DATA-load-failure`, `ROB-offline`).
    - 3a2. Use case ends.
- **3b. A saved favorite no longer exists in the database.**
    - 3b1. The system shows that favorite as no longer available and offers to remove it.
    - 3b2. Rejoin at step 4.
- **5a. The user removes a favorite.**
    - 5a1. The system removes it from the device and updates the list.
    - 5a2. Rejoin at step 4.

**Priority:** Medium

**Frequency of Use:** A few times per visit, for visitors who save favorites.

**Business Rules:**

**Associated Information:**

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| Monnig number | text | Required; must match a meteorite in the database when saved | Stored on the device only | Monnig # |
| Meteorite name | text | Required; kept so the list can show without a network | Stored on the device only | Meteorite Name |

No personal data is stored (`DI-no-personal-data`).

**Related Use Cases:** `UC-DAT-view-meteorite`, `UC-PREF-reset-preferences`, the "Save favorite" use case (another pair)

**Assumptions:** Saving a favorite is a separate use case. Favorites are not shared between devices; that needs a back end and is a later feature.

**Open Issues:**

- Does `UC-PREF-reset-preferences` clear favorites (`OI-41`)?
- Is there a maximum number of favorites?
- Favorites are saved on the device only for now. Keeping them across devices needs a back end and is a later issue (`OI-39`).


### UC-DAT-view-similar-meteorites: View Similar Meteorites

**UC ID and Name:** `UC-DAT-view-similar-meteorites`: View Similar Meteorites

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** None

**Trigger:** While viewing a meteorite, the user chooses to see similar meteorites.

**Description:** Like "related products" when shopping, the system suggests other meteorites in the collection that share key traits with the one being viewed, so the user can keep exploring (minutes, 2026-11-09).

**Preconditions:**

- PRE-1. The user is viewing a single meteorite (`UC-DAT-view-meteorite`).

**Postconditions:**

- POST-1. The system shows meteorites similar to the one viewed, and what makes each one similar.

**Main Success Scenario:**

1. The user chooses to see similar meteorites.
2. The system finds meteorites in the database that share traits with the current one, using the similarity rule.
3. The system shows the similar meteorites, each with its name, picture if one exists, and the trait it shares (for example, the same class).
4. The user selects one.
5. The system shows that meteorite in detail (`UC-DAT-view-meteorite`).
6. Use case ends.

**Extensions:**

- **2a. The system cannot reach the database.**
    - 2a1. The system shows a message and offers to try again (`FR-DATA-load-failure`).
    - 2a2. Use case ends.
- **2b. The current meteorite is missing the traits the rule uses.**
    - 2b1. The system uses the traits it has; if none are left, continue at 2c.
- **2c. No other meteorite is similar.**
    - 2c1. The system says no similar meteorites were found.
    - 2c2. Use case ends.

**Priority:** Low

**Frequency of Use:** Occasionally, after viewing a meteorite.

**Business Rules:**

**Associated Information:** The current meteorite is never listed as similar to itself. The number shown and their order are TBD.

**Related Use Cases:** `UC-DAT-view-meteorite`, `UC-DAT-browse-database`

**Assumptions:** The database has enough fields (class, group, location found) to compare meteorites (`AS-catalog-data-sufficient`).

**Open Issues:**

- What makes two meteorites "similar"? This is a scientific judgment, so the rule should come from Dr. Mayne, not the team (`OI-4` for which fields exist).


### UC-DAT-view-on-display-items: View Meteorites on Display

**UC ID and Name:** `UC-DAT-view-on-display-items`: View Meteorites on Display

**Created By:** Koen Dolezar

**Date Created:** November 15, 2026

**Primary Actor:** Visitor, usually in the gallery

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects On Display on the Home screen.

**Description:** Most of the roughly 3,000 meteorites in the collection are not on view. A visitor standing in the gallery usually wants only the ones they can see. This use case opens a list of only the meteorites currently on display, sorted A to Z by name, where the visitor can search and filter as in the full database and open any meteorite. It is a shortcut to the full list with "On display only" fixed on, so it shares its behavior with `UC-DAT-browse-database`. Finding a meteorite by room or display case belongs to the Tour use cases.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the Home screen is reachable.

**Postconditions:**

- POST-1. The list shows only meteorites whose `onDisplay` is `true`, sorted A to Z by name.
- POST-2. If the visitor selected a meteorite, View meteorite has opened with that meteorite's `monnigNumber`.
- POST-3. Nothing in the catalog has changed (`FR-CONTENT-visitor-read-only`, `DI-catalog-source-of-truth`).

**Main Success Scenario:**

1. The visitor selects On Display on the Home screen.
2. The system opens the On Display screen, titled so the visitor knows it lists only meteorites on display, shows that the list is loading, and requests from the catalog the first batch of meteorites on display, sorted A to Z by name.
3. The catalog returns the batch.
4. The system shows the list and the total number of meteorites on display. Each item shows the meteorite's name and its first image, or a placeholder image if it has none.
5. The visitor scrolls, and the system loads more batches as needed, as in `UC-DAT-browse-database` steps 5 and 6.
6. The visitor selects a meteorite.
7. The system opens the selected meteorite in View meteorite.
8. Use case ends.

**Extensions:**

- **2a. The device has no network connection, and the app has loaded catalog data before (`ROB-offline`).**
    - 2a1. The system shows the meteorites on display that it already has, with a notice that the list may be incomplete while offline.
    - 2a2. Flow continues at step 4.
- **3a. The catalog cannot be reached, returns an error, or returns only part of the first batch.**
    - 3a1. The system shows a message saying the meteorites could not be loaded, with a way to try again (`FR-DATA-load-failure`). The rest of the app stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2. Otherwise the visitor leaves, and use case ends.
- **3b. The catalog reports no meteorites on display.**
    - 3b1. The system shows a message saying no meteorites are listed as on display, with a link to the full Meteorite Database (`UC-DAT-browse-database`), instead of an empty list.
    - 3b2. Use case ends.
- **3c. A returned record is missing a field the list shows, or is malformed.**
    - 3c1. As `UC-DAT-browse-database` 3c.
- **4a. A meteorite's image fails to load, or is still loading.**
    - 4a1. The system shows the placeholder image in its place. The item can still be selected.
- **5a. The visitor searches the list.**
    - 5a1. `UC-DAT-search-database` handles it, searching only meteorites on display.
    - 5a2. Flow rejoins at step 6.
- **5b. The visitor filters the list.**
    - 5b1. `UC-DAT-filter-database` handles it. The panel shows "On display only" switched on and locked, because this screen lists nothing else.
    - 5b2. Flow rejoins at step 6.
- **5c. The next batch cannot be loaded.**
    - 5c1. As `UC-DAT-browse-database` 6a.
- **7a. The visitor comes back from View meteorite.**
    - 7a1. The system shows the list at the same place, without loading it again.
    - 7a2. Flow rejoins at step 5.
- **7b. The meteorite was taken off display after the list loaded.**
    - 7b1. View meteorite still opens it; the list is not changed until it is next loaded.
- **\*a. The visitor leaves the screen for Home.**
    - \*a1. Use case ends. The next time the visitor opens On Display, the list starts again at the top with no search or filters.

**Priority:** Medium

**Frequency of Use:** Once or more in most in-gallery visits; less often for remote visitors (`OE-remote-use`). Proposed by one team member (minutes 2026-11-09). Each open requests one batch, plus one for each batch scrolled into. In the gallery, up to about 30 visitors in one group may do this at the same time (`SCA-group-concurrency`).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-permanent-exhibit`, `BR-accessibility-standard`

**Associated Information:**

_Data fields (read from the catalog; visitors cannot change them). Definitions are in the SRS §7.2 data dictionary:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `onDisplay` | boolean | Required, default `false` (SRS §7.2). Only `true` records are listed. Not shown on each item, since every item is on display. | Read-only to visitors; set only by an administrator (`UC-ADM-update-content`) | Display |
| `monnigNumber` | text | Required and unique. Not shown. Identifies the meteorite handed to View meteorite and breaks ties in the sort. | Read-only to visitors | Monnig # |
| `meteoriteName` | text | Required. Shown, and is the sort key. If missing, "[NOT INDICATED]" (`FR-DATA-missing-field`). | Read-only to visitors | Meteorite Name |
| `images` | list of Image | Optional. Only the first image is shown, or a placeholder. | Read-only to visitors; image rights are open (`OI-15`) | — |

- **Same list, one fixed filter.** Sorting, batching, missing-data handling, and accessibility are those of `UC-DAT-browse-database`. This use case adds only the fixed `onDisplay = true` condition, the title, and the total count.
- **Why its own entry on Home.** Visitors in the gallery mostly look for what is in front of them, and the full list of about 3,000 is mostly items not on view (`SCA-full-collection`). The author chose a Home entry over relying on the filter alone; the reviewer may prefer to drop this screen and use the filter instead.
- **Freshness.** What is on display changes rarely (`BR-permanent-exhibit`), but the Texas map changes with each new find. The list is only as current as the `onDisplay` values (`OI-44`, `MNT-content-update`).
- **Not by room.** Grouping by room or display case is left to the Tour use cases (`UC-TOUR-view-gallery-map`, `UC-TOUR-browse-gallery-section`), which need location data this use case does not.
- **Accessibility.** The screen title and the total count are read by the screen reader when the list loads (`USE-screen-reader`).
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), steps 2 and 3 read from that copy.
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-browse-database` _(in review)_: Browse the Meteorite Database. This screen is the same list with "On display only" fixed on.
- `UC-DAT-search-database` _(in review)_: Search, within this list (5a).
- `UC-DAT-filter-database`: Filter, within this list (5b).
- `UC-DAT-view-meteorite` _(in review)_: View a Meteorite. Opens the meteorite selected at step 6.
- `UC-ADM-update-content` _(not yet written; another pair)_: Where an administrator marks a meteorite on or off display.
- `UC-TOUR-view-gallery-map` _(in review)_, `UC-TOUR-browse-gallery-section` _(in review)_: Find meteorites by where they are in the gallery.

**Assumptions:**

- The catalog, or the app's own copy of it, records for each meteorite whether it is on display (`onDisplay`, SRS §7.2). If it does not, this use case cannot be built until `OI-44` is settled.
- One list item per catalog record. If two samples of the same meteorite are on display, its name appears twice (`OI-4`).

**Open Issues:**

- `OI-44`: Where does "on display" come from: a field in the catalog, or the gallery's separate list of items on display (interview §10)? Who keeps it current when a display changes?
- `OI-4`: Where the meteorite data comes from.
- `OI-13`: The load-time threshold for `PER-database-list`, which applies to this list as well.


## TOUR: Gallery tour

### UC-TOUR-browse-gallery-section: Browse a Gallery Section

**UC ID and Name:** `UC-TOUR-browse-gallery-section`: Browse a Gallery Section

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The source of gallery section content (`OI-24`)

**Trigger:** The visitor selects Gallery on the Home screen, or View gallery map hands off a room or a section the visitor chose.

**Description:** The gallery has three rooms, and each room holds sections. What exactly counts as a section is still open (see Open Issues). The visitor picks a room, sees the sections in it, and opens one to see its name, its description, and the displays in it. Displays are mostly meteorites but can be other things. Selecting a display opens it in View exhibit. The gallery map, a single exhibit's details, the self-guided tour, and visitor information are separate use cases.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the Home screen is reachable.

**Postconditions:**

- POST-1. The visitor has seen the rooms, the sections in the room they chose, and, if they chose a section, its details and displays.
- POST-2. If the visitor selected a display, View exhibit has opened with that display.
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Gallery on the Home screen.
2. The system requests the gallery's rooms and their sections.
3. The content source returns the rooms and sections.
4. The system shows the three rooms, in the order a visitor walks the gallery.
5. The visitor selects a room.
6. The system shows the sections in that room, in the order a visitor walks them.
7. The visitor selects a section.
8. The system requests the section's details.
9. The content source returns the section's details.
10. The system shows the section screen: the section's name, its room, its description, and the list of displays in it by name.
11. The visitor selects a display.
12. The system opens the selected display in View exhibit.
13. Use case ends.

**Extensions:**

- **1a. The visitor arrives from View gallery map with a room chosen.**
    - 1a1. The system requests the rooms and sections, as in steps 2 and 3.
    - 1a2. Flow continues at step 6 with the chosen room.
- **1b. The visitor arrives from View gallery map with a section chosen.**
    - 1b1. Flow continues at step 8.
- **2a. The device has no network connection (`ROB-offline`).**
    - 2a1. If the app has loaded the rooms and sections before, the system shows what it already has, and flow continues at step 4.
    - 2a2. If it has not, flow continues at 3a.
- **3a. The rooms and sections cannot be loaded.**
    - 3a1. The system shows a message saying the gallery could not be loaded, with a way to try again (`FR-DATA-load-failure`, applied here to any content). The rest of the app stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2. Otherwise use case ends.
- **3b. No sections are defined.**
    - 3b1. The system shows a message saying gallery sections are not available, instead of an empty list.
    - 3b2. Use case ends.
- **6a. The selected room has no sections.**
    - 6a1. The system shows a message saying no sections are listed for this room.
    - 6a2. The visitor goes back, and flow rejoins at step 4.
- **6b. The visitor goes back from the section list.**
    - 6b1. Flow rejoins at step 4.
- **9a. The section's details cannot be loaded.**
    - 9a1. The system shows a message on the section screen saying the section could not be loaded, with a way to try again (`FR-DATA-load-failure`, applied here to any content).
    - 9a2. If the visitor tries again, flow rejoins at step 8. If the visitor goes back, flow rejoins at step 6.
- **10a. The section has no description.**
    - 10a1. The system shows "[NOT INDICATED]" in its place (`FR-DATA-missing-field`, applied here to any content).
    - 10a2. Flow continues at step 11.
- **10b. The section has no displays.**
    - 10b1. The system shows the section's name, room, and description, with a message saying no displays are listed for this section.
    - 10b2. The visitor goes back, and flow rejoins at step 6.
- **10c. The visitor goes back from the section screen.**
    - 10c1. Flow rejoins at step 6, listing the sections in the same room.
- **\*a. The visitor leaves for the Home screen.**
    - \*a1. Use case ends.

**Priority:** Medium

**Frequency of Use:** Mostly by visitors in the gallery, a few times per visit as they move between rooms; remote visitors can use it too (`OE-remote-use`). The gallery's exhibits are mostly permanent (`BR-permanent-exhibit`), so section content rarely changes.

**Business Rules:** `BR-permanent-exhibit`, `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields. All are **Proposed**: the SRS domain model (§7.1) goes Gallery → Room → Display and has no Section yet, and where this content comes from is open (`OI-24`):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `sectionName` | text | Required | Read-only to visitors; set by administrators | _Section (not yet in the glossary)_ |
| `room` | reference to a Room | Required; one of the gallery's three rooms. Everything in the gallery is in a room. | Read-only to visitors | Room |
| `order` | integer | Required. The section's place in the order a visitor walks its room. | Read-only to visitors | — |
| `description` | long text | Optional; see 10a | Read-only to visitors | — |
| `displays` | ordered list of Display | Optional; may be empty (see 10b) | Read-only to visitors | Display |

- **Order.** Rooms and sections are shown in walking order (see Assumptions).
- **Language.** Interface text follows `FR-LANG-interface-text`. Translating section content is out of scope for this use case.
- **Accessibility.** Every section and display in the lists has a screen-reader label (`USE-screen-reader`) and stays readable at every text size (`USE-text-scaling`).
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-TOUR-view-gallery-map` _(not yet written)_: View gallery map. Can hand off a chosen room or section (1a, 1b).
- `UC-TOUR-view-exhibit` _(not yet written)_: View exhibit. Opens the display selected at step 11.
- `UC-TOUR-self-guided-tour` _(not yet written)_: Self-guided tour. Moves the visitor through the sections in order, including any next and previous section controls.
- `UC-TOUR-visitor-info` _(not yet written)_: Visitor info. Hours and location; not shown here.

**Assumptions:**

- Everything in the gallery is in a room. Each section is in exactly one room, and each display is in exactly one section.
- Rooms are shown in the order a visitor walks the gallery, and the sections in a room in the order a visitor walks that room. The actual order is part of `OI-23`.
- The rooms are shown as a simple list. A map graphic belongs to View gallery map.
- Displays are mostly meteorites but can be other things. The section screen lists them all the same way, and View exhibit shows what each one holds.
- Translating section names and descriptions is out of scope for this use case.
- "Gallery" is a working label for the Home screen entry. The design names it.
- Reading a section's description aloud is not part of this use case. `FR-TTS-read-description` covers meteorite descriptions only.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-23`: What are the gallery's sections, which room is each in, in what order, and which displays does each hold?
- `OI-24`: Where do section names, descriptions, and display lists come from, and who keeps them current?
- `OI-47`: What is a gallery section, and how does it differ from a room, a display, and an exhibit? Which areas of the gallery are sections?
- `OI-48`: For group discussion: the browse flow Rooms → Sections → Displays → View, and what it changes in `UC-TOUR-view-gallery-map`, `UC-TOUR-view-exhibit`, `UC-DAT-view-meteorite`, and `UC-TOUR-take-self-guided-tour`.


### UC-TOUR-view-gallery-map: View Gallery Map

**UC ID and Name:** `UC-TOUR-view-gallery-map`: View Gallery Map

**Created By:** Bradley Helmholz

**Date Created:** November 12, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The source of the gallery map and room content (`OI-29`)

**Trigger:** The visitor selects Gallery Map on the Home screen, or goes back to the map from a room screen.

**Description:** The visitor sees a graphic map of the gallery divided into its three rooms (`UI-room-selection`). They tap a room to open a detail screen for it: its name, a short description, the sections it holds, and the meteorites housed in it. From there the visitor can open a section in Browse a Gallery Section, or open a meteorite or display in View exhibit. This works the same for visitors in the gallery and remote visitors (`OE-remote-use`). When the app cannot load the map graphic, it instead falls back on a list of the room names, which can be selected to bring up the associated information with that room. The map does not show the visitor's position, because release 1.0 uses no Bluetooth, camera, or location services. A section's own details, a single exhibit's details, the guided order of a self-guided tour, and visitor information are separate use cases.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the Home screen is reachable.

**Postconditions:**

- POST-1. The visitor has seen the gallery map or room list and, if they chose one, a room's details.
- POST-2. If the visitor chose a section, a meteorite, or a display, the matching use case has opened with it.
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Gallery Map on the Home screen.
2. The system requests the gallery map and the list of rooms.
3. The content source returns them.
4. The system shows the map graphic with the three rooms drawn, each labeled with its name and tappable.
5. The visitor taps a room.
6. The system shows the room screen: the room's name, its description, the list of its sections, and the list of meteorites housed in it, each by name.
7. The visitor selects a section.
8. The system opens the selected section in Browse a Gallery Section.
9. Use case ends.

**Extensions:**

- **2a. The device has no network connection, and the app has loaded the map before (`ROB-offline`).**
    - 2a1. The system shows the map and rooms it already has.
    - 2a2. Flow continues at step 4.
- **3a. The map and rooms cannot be loaded.**
    - 3a1. The system shows a message saying the gallery map could not be loaded, with a way to try again (`FR-DATA-load-failure`). The rest of the app stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2. Otherwise use case ends.
- **3b. The map graphic is missing or cannot be shown, but the rooms were returned.**
    - 3b1. The system shows the rooms as a plain list in walking order, with a message saying the map could not be shown.
    - 3b2. Flow rejoins at step 5.
- **3c. No rooms are defined.**
    - 3c1. The system shows a message saying the gallery map is not available, instead of an empty map.
    - 3c2. Use case ends.
- **4a. The visitor uses a screen reader or a larger text size (`USE-screen-reader`, `USE-text-scaling`).**
    - 4a1. The system gives each room a spoken label with its name, and offers the same rooms as a list under the map, so the map is never the only way in (`BR-accessibility-standard`).
    - 4a2. Flow continues at step 5.
- **4b. The application cannot load the image graphic of the gallery rooms.**
    - 4b1. The system instead displays a list of the room names, displayed in walking order.
    - 4b2. Users can select the room name in the list as they would the corresponding section on the graphic map.
    - 4b3. Flow continues at step 5.
- **5a. The visitor taps part of the map that is not a room.**
    - 5a1. The system does nothing and keeps the map as it is.
    - 5a2. Flow rejoins at step 5.
- **6a. The room has no description, or no description in the selected language.**
    - 6a1. With no description at all, the system shows "[NOT INDICATED]" in its place (`FR-DATA-missing-field`).
    - 6a2. With an English description only, the system shows the English text, marked as not translated (`FR-LANG-content-fallback`, Proposed).
    - 6a3. Flow continues at step 7.
- **6b. The room has no sections, no meteorites, or neither.**
    - 6b1. The system shows the room's name and description, with a message saying nothing is listed for this room.
    - 6b2. The visitor goes back, and flow rejoins at step 5 (6d).
- **6c. The room's details cannot be loaded.**
    - 6c1. The system shows a message on the room screen saying the room could not be loaded, with a way to try again (`FR-DATA-load-failure`).
    - 6c2. If the visitor tries again, flow rejoins at step 6. Going back to the map still works (6d).
- **6d. The visitor goes back from the room screen.**
    - 6d1. The system shows the map as it was.
    - 6d2. Flow rejoins at step 5.
- **7a. The visitor selects a meteorite or display instead of a section.**
    - 7a1. The system opens it in View exhibit.
    - 7a2. Use case ends.
- **\*a. The visitor leaves for the Home screen.**
    - \*a1. Use case ends.

**Priority:** Medium

**Frequency of Use:** Mostly by visitors in the gallery, once or twice a visit as they decide where to go next; remote visitors can use it too (`OE-remote-use`). The gallery's exhibits are mostly permanent (`BR-permanent-exhibit`), so map and room content rarely change.

**Business Rules:** `BR-permanent-exhibit`, `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields. All are **Proposed**: the SRS domain model (§7.1) gives Room only a name, and has no map graphic or Section yet:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `mapGraphic` | image or vector drawing | Required; shows all three rooms. If missing, see 3b. | Read-only to visitors; set by administrators | _Gallery map (not yet in the glossary)_ |
| `roomName` | text, per language | Required | Read-only to visitors | Room |
| `roomRegion` | shape on the map graphic | Required; one per room; regions do not overlap | Read-only to visitors | Room |
| `order` | integer | Required; unique; the room's place in the order a visitor walks the gallery | Read-only to visitors | — |
| `roomDescription` | long text, per language | Optional; see 6a | Read-only to visitors | — |
| `sections` | ordered list of Section | Optional; may be empty (see 6b) | Read-only to visitors | _Section (not yet in the glossary)_ |
| `meteorites` | list of Sample or Display | Optional; may be empty (see 6b) | Read-only to visitors | Display, Sample |

- **Rooms.** There are three, as in the old app's room-selection view. The map is the existing gallery floor plan, not a new drawing (minutes 2026-11-04).
- **Language.** Room names and descriptions are shown in the selected language, falling back to English per `FR-LANG-content-fallback`. Interface text follows `FR-LANG-interface-text`.
- **Accessibility.** Every room has a screen-reader label and stays readable at every text size (see 4a).
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-TOUR-browse-gallery-section`: Browse a Gallery Section. Opens the section selected at step 7. It can also be reached from this map with a room chosen (its 1a, 1b).
- `UC-TOUR-view-exhibit` _(not yet written)_: View exhibit. Opens the meteorite or display selected at 7a.
- `UC-DAT-view-meteorite`: View a Meteorite. May be where a selected meteorite lands, depending on the View exhibit design.
- `UC-TOUR-self-guided-tour` _(not yet written)_: Self-guided tour. Walks the visitor through rooms in order; not shown here.
- `UC-TOUR-visitor-info` _(not yet written)_: Visitor info. Hours and location; not shown here.

**Assumptions:**

- The map is a picture with tappable room regions. Whether it also zooms or pans is open (`OI-30`).
- When the map picture graphic cannot be loaded a labeled room list will be displayed to the user to be interacted with in place of the graphic.
- Each section is in exactly one room, and each display is in exactly one section.
- "Gallery Map" is a working label for the Home screen entry. The design names it.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.
- Other teammates' use cases are on branches not yet merged. This draft was written against Browse a Gallery Section as it stands on its branch, and should be rechecked after that merges.

**Open Issues:**

- `OI-29`: Where does the map graphic come from, and who supplies it and the room outlines? The client interview (§ floor plan) requested a floor plan, and receipt is not recorded.
- `OI-30`: Is the map a fixed picture, or can the visitor zoom and pan? Are sections tappable on the map, or only rooms?
- `OI-31`: What should a room screen list: sections, displays, meteorites, or all three? `UI-room-selection` and Browse a Gallery Section overlap here.
- `OI-32`: Is this use case in release 1.0? `UI-room-selection` is Proposed, and `FEAT-section-screens` is out of MVP scope (see `OI-1`, `OI-25`).


### UC-TOUR-take-self-guided-tour: Take a Self-Guided Tour

**UC ID and Name:** `UC-TOUR-take-self-guided-tour`: Take a Self-Guided Tour

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum Staff

**Trigger:** The user chooses to start the self-guided tour from the home screen.

**Description:** The system walks the user through the gallery one stop at a time, in the order the gallery is laid out, so they can explore at their own pace without a guide. The client's order: asteroid belt, theater, history of meteorites, entry through the atmosphere, types of meteorites, collisions, terrestrial rocks, new acquisitions, and the Texas room (interview, §2).

**Preconditions:**

- PRE-1. The user has opened the application and passed the home screen.

**Postconditions:**

- POST-1. The user has reached the end of the tour, or left it.

**Main Success Scenario:**

1. The user chooses to start the tour.
2. The system shows the first stop: its name, the room it is in, and its description.
3. The user reads the stop, or listens to it (`UC-TTS-listen-to-content`).
4. The user moves to the next stop.
5. The system shows the next stop.
6. Steps 3 to 5 repeat until the last stop.
7. The system shows that the tour is complete and offers to return home.
8. Use case ends.

**Extensions:**

- **2a. The tour content cannot be loaded.**
    - 2a1. The system shows a message and offers to try again (`FR-DATA-load-failure`).
    - 2a2. Use case ends.
- **4a. The user goes back to the previous stop.**
    - 4a1. The system shows the previous stop.
    - 4a2. Rejoin at step 3.
- **4b. The user jumps to a different stop from the list of stops.**
    - 4b1. The system shows the chosen stop.
    - 4b2. Rejoin at step 3.
- **4c. The user selects an exhibit at the stop.**
    - 4c1. The system shows the exhibit (`UC-TOUR-view-exhibit`).
    - 4c2. When the user returns, rejoin at step 3.
- **\*a. The user leaves the tour.**
    - \*a1. The system remembers the last stop viewed during this session and offers to resume from it next time the tour is started.
    - \*a2. Use case ends.

**Priority:** High (`BO-tour`)

**Frequency of Use:** Once per visit for most visitors; tours take about 30 to 60 minutes.

**Business Rules:** `BR-permanent-exhibit`

**Associated Information:** No location detection is used; the user moves through the stops themselves (minutes, 2026-11-02). Gallery text is used word for word (minutes, 2026-11-09). The tour works the same for remote visitors (`OE-remote-use`).

**Related Use Cases:** `UC-TOUR-view-exhibit`, `UC-TTS-listen-to-content`

**Assumptions:** The gallery provides the list of stops and their text.

**Open Issues:**

- Who writes each stop's text, and is it the same as the gallery's wall text?
- Should the tour differ by age range (interview, §5)?


### UC-TOUR-view-exhibit: View an Exhibit

**UC ID and Name:** `UC-TOUR-view-exhibit`: View an Exhibit

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** None

**Trigger:** The user selects an exhibit, from a gallery room or a tour stop.

**Description:** The user sees one exhibit (a display, interactive sample, or audiovisual learning aid, per the glossary): what it is about, which room it is in, and the meteorites it holds.

**Preconditions:**

- PRE-1. The user is viewing a gallery section (`UC-TOUR-browse-gallery-section`) or a tour stop (`UC-TOUR-take-self-guided-tour`).

**Postconditions:**

- POST-1. The system shows the exhibit's name, room, description, and the meteorites in it.

**Main Success Scenario:**

1. The user selects an exhibit.
2. The system retrieves the exhibit's information.
3. The system shows the exhibit's name, the room it is in, and its description.
4. The system lists the meteorites in the exhibit, each with its name and picture if one exists.
5. The user selects a meteorite.
6. The system shows that meteorite in detail (`UC-DAT-view-meteorite`).
7. Use case ends.

**Extensions:**

- **2a. The exhibit's information cannot be loaded.**
    - 2a1. The system shows a message and offers to try again (`FR-DATA-load-failure`).
    - 2a2. Use case ends.
- **4a. The exhibit holds no meteorites (for example, the theater area).**
    - 4a1. The system shows the description only.
    - 4a2. Use case ends.
- **4b. A meteorite in the exhibit is not in the database.**
    - 4b1. The system lists it by name but does not offer its details.
    - 4b2. Rejoin at step 5.
- **5a. The user asks to hear the description.**
    - 5a1. The system reads it aloud (`UC-TTS-listen-to-content`).
    - 5a2. Rejoin at step 5.

**Priority:** High

**Frequency of Use:** Many times per visit.

**Business Rules:** `BR-permanent-exhibit`

**Associated Information:** Exhibit description is the gallery's text, used word for word. Fields missing from the data are shown per `FR-DATA-missing-field`.

**Related Use Cases:** `UC-TOUR-take-self-guided-tour`, `UC-DAT-view-meteorite`, `UC-TOUR-browse-gallery-section`, `UC-TOUR-view-gallery-map`

**Assumptions:** The gallery can provide which meteorites are in each exhibit.

**Open Issues:**

- Is the list of meteorites in each exhibit kept anywhere today, or does it need to be built (`OI-4`)?


### UC-TOUR-view-visitor-info: View Visitor Information

**UC ID and Name:** `UC-TOUR-view-visitor-info`: View Visitor Information

**Created By:** Edwin Rodriguez

**Date Created:** November 11, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** None

**Trigger:** The user chooses Visitor Info from the home screen.

**Description:** The user sees what they need to plan a visit: where the gallery is, when it is open, that admission is free, and how to contact the gallery. The client mentioned visitors wish the gallery were easier to find on campus (interview, §3).

**Preconditions:**

- PRE-1. The user has opened the application and passed the home screen.

**Postconditions:**

- POST-1. The system has shown the gallery's location, hours, admission, and contact link.

**Main Success Scenario:**

1. The user chooses Visitor Info.
2. The system shows the gallery's address and building, public hours, holiday closures, and admission.
3. The user chooses to plan a visit.
4. The system opens the gallery's contact page in the device's browser (`FR-PLAN-contact-link`, `SI-gallery-website`).
5. Use case ends.

**Extensions:**

- **2a. The device has no network connection.**
    - 2a1. The system shows the visitor information it already has, with a note that it may be out of date.
    - 2a2. Rejoin at step 3.
- **3a. The user chooses directions instead.**
    - 3a1. The system opens the gallery's address in the device's maps app.
    - 3a2. Use case ends.
- **4a. The browser cannot be opened.**
    - 4a1. The system shows the contact page address so the user can copy it.
    - 4a2. Use case ends.

**Priority:** High (`FR-PLAN-visitor-info`)

**Frequency of Use:** Once or twice per visitor, mostly before a visit.

**Business Rules:**

**Associated Information:** Booking a visit inside the app is not in release 1.0 (minutes, 2026-11-09). Opening a maps app is a new software interface and should be added to the SRS §8.3 if kept.

**Related Use Cases:** None

**Assumptions:** The gallery's hours are 1:00 to 4:00 p.m., Monday to Saturday, closed on university holidays, per its website; to be confirmed with the client (minutes, 2026-11-09).

**Open Issues:**

- Where are the hours kept so they stay current when they change (`OI-11`)?


## ADM: Content administration

### UC-ADM-log-in: Log In as an Administrator

**UC ID and Name:** `UC-ADM-log-in`: Log In as an Administrator

**Created By:** Koen Dolezar

**Date Created:** November 15, 2026

**Primary Actor:** Gallery administrator (the gallery staff the client designates; today Dr. Rhiannon Mayne and Heather Stepp, minutes 2026-11-09)

**Secondary Actors:** The sign-in service that checks administrators' credentials, either one built into the admin portal or TCU's own sign-in (`OI-45`)

**Trigger:** The administrator opens the admin portal's address in a web browser.

**Description:** Only gallery administrators may change the app's content (`BR-only-admin-can-edit-database`), and the team decided that they will do it in a browser-based admin portal, not in the visitor app (minutes 2026-11-06, 2026-11-09). Before the portal shows or changes anything, the administrator proves who they are. After signing in they reach the portal's content list, where `UC-ADM-update-content` begins. The visitor app has no sign-in at all (`FR-CONTENT-no-visitor-account`). This use case applies only if release 1.0 includes the admin portal (`OI-11`).

**Preconditions:**

- PRE-1. The admin portal is deployed and reachable over HTTPS (`SEC-https-only`).
- PRE-2. The person has an administrator account, created as `OI-45` decides.

**Postconditions:**

- POST-1. The portal has an authenticated session for this administrator, and every later request to change content in that session is checked against it (`SEC-admin-authenticated`).
- POST-2. The administrator sees the portal's content list.
- POST-3. No password or other secret was stored in the visitor app (`SEC-no-write-credentials`).

**Main Success Scenario:**

1. The administrator opens the admin portal in a web browser.
2. The system shows the sign-in page.
3. The administrator enters their username and password and selects Sign in.
4. The system checks the credentials with the sign-in service.
5. The sign-in service confirms them, and the system confirms that the account is an administrator.
6. The system starts a session and shows the content list, with the administrator's name and a Sign out control.
7. Use case ends.

**Extensions:**

- **1a. The administrator already has a session that has not expired.**
    - 1a1. The system skips the sign-in page and shows the content list.
    - 1a2. Use case ends.
- **1b. The administrator opens a page deeper in the portal (for example, a bookmarked meteorite) without a session.**
    - 1b1. Flow continues at step 2. After step 6 the system opens the page that was asked for instead of the content list.
- **3a. The administrator leaves a field empty.**
    - 3a1. The system says which field is missing and does not contact the sign-in service.
    - 3a2. Flow rejoins at step 3.
- **4a. The username or password is wrong.**
    - 4a1. The system shows one message saying the username or password is not correct, without saying which, and clears the password field.
    - 4a2. Flow rejoins at step 3.
- **4b. There have been too many failed attempts for this account in a short time.**
    - 4b1. The system refuses further attempts for a while and says to try again later or contact the person who manages accounts. The number of attempts and the wait are TBD (`OI-46`).
    - 4b2. Use case ends.
- **4c. The sign-in service cannot be reached or returns an error.**
    - 4c1. The system says sign-in is unavailable right now and to try again later. It does not start a session.
    - 4c2. Use case ends.
- **4d. The administrator has forgotten their password.**
    - 4d1. The administrator selects "Forgot password".
    - 4d2. The system sends them to the sign-in service's own reset process (`OI-45`).
    - 4d3. Use case ends. The administrator starts again at step 1 after resetting.
- **5a. The credentials are valid, but the account is not an administrator (for example, a TCU account of someone who is not on the administrator list).**
    - 5a1. The system says this account does not have access to the portal, and starts no session.
    - 5a2. Use case ends.
- **\*a. The session expires after a period with no activity (TBD, `OI-46`).**
    - \*a1. The next request the administrator makes is refused, and the system shows the sign-in page, saying the session expired.
    - \*a2. After the administrator signs in again, the system returns them to the page they were on. Unsaved edits on the page must not be lost; how is left to `UC-ADM-update-content`.
- **\*b. The administrator selects Sign out.**
    - \*b1. The system ends the session and shows the sign-in page. Using the browser's Back button afterward shows no portal data.
    - \*b2. Use case ends.
- **\*c. The administrator's access is removed while they have a session.**
    - \*c1. The next request to change content is refused, as in 5a (`SEC-admin-authenticated`).

**Priority:** Medium. Needed only if `UC-ADM-update-content` is in release 1.0 (`OI-11`).

**Frequency of Use:** Rare: a few times a year, when the exhibit changes or a meteorite's information is corrected (`BR-permanent-exhibit`). Two or three administrators at most. Proposed by one team member (minutes 2026-11-09).

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-monnig-branding`

**Associated Information:**

_Data fields:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `username` | text | Required. Its form (email address, TCU username) depends on `OI-45`. | Not shown to visitors | — |
| `password` | text | Required. Never shown, logged, or stored in plain text; rules for it come from the sign-in service (`OI-45`). | Sent only over HTTPS (`SEC-https-only`) | — |
| `isAdministrator` | boolean | Required. Set only by whoever manages accounts (`OI-45`). | Never settable from the portal's sign-in page | Staff |
| `session` | token | Created at step 6; ends at sign-out or after inactivity (`OI-46`). | Held only by the administrator's browser; not visible to scripts on the page | — |

- **Portal, not app.** There is no administrator sign-in in the visitor app, which holds no credential that can change content (`SEC-no-write-credentials`, minutes 2026-11-09: "credentials only for admin").
- **Who decides who is an administrator.** The client (`BR-only-admin-can-edit-database`). The portal only checks the list it is given.
- **Messages.** A failed sign-in never says whether the username exists (4a). Messages are in English; the portal is for staff and is not translated in release 1.0 (author's decision).
- **Accessibility.** The sign-in page works with a keyboard alone and with a screen reader (`USE-accessibility-standard`).
- **Branding.** The portal uses Monnig branding (`CO-monnig-branding`).
- **Systemic failure.** A failure during sign-in leaves no session; there is nothing partly done to undo.
- **Not invented here.** No password length, lockout count, or session length is set in this use case, because none came from the client or TCU; they are `OI-46`.

**Related Use Cases:**

- `UC-ADM-update-content` _(not yet written; another pair)_: Update Meteorite Content. Starts from the content list this use case ends on, and requires a session.

**Assumptions:**

- The admin portal is a separate web page, built and hosted as part of the app's back end. Whether that back end exists depends on `OI-4`.
- Administrators use a desktop or laptop browser.

**Open Issues:**

- `OI-11`: Whether release 1.0 includes an admin portal at all.
- `OI-45`: How do administrators sign in: with their TCU accounts through TCU's sign-in, or with accounts the portal manages itself? Who adds and removes administrators, and how is a forgotten password reset?
- `OI-46`: How long may an administrator's session stay idle, and how many failed sign-ins lock an account, and for how long? Does TCU IT have a policy?


### UC-ADM-update-content: Update Meteorite Content

**UC ID and Name:** `UC-ADM-update-content`: Update Meteorite Content

**Created By:** Cody Pinkston

**Date Created:** November 15, 2026

**Primary Actor:** Gallery administrator (Dr. Mayne or Heather Stepp, minutes 2026-11-09; SRS §2 user classes)

**Secondary Actors:** The content database: the database the admin portal writes to and the visitor app reads from (`OI-4`). The visitor app, which picks up the change.

**Trigger:** In the admin portal, the signed-in administrator chooses Add meteorite, or selects an existing meteorite in the portal's meteorite list to edit, hide, or restore it.

**Description:** A gallery administrator keeps the app's meteorite content current without a developer and without a new app-store release (`MNT-content-update`). From a browser-based admin portal (minutes, 2026-11-09), the administrator adds a new meteorite, edits an existing one, hides one so visitors no longer see it, or restores a hidden one. A meteorite's content is its record fields (SRS §7.2), its description in English and Spanish, its photos, and the gallery display it is in. Saved changes go live right away: visitors see them the next time their app loads content. Hiding keeps the record so it can be restored, which is how this use case "removes" a meteorite. Signing in is its own use case (`UC-ADM-log-in`).

**Preconditions:**

- PRE-1. The administrator is signed in to the admin portal (`UC-ADM-log-in`), and the session has not expired.

**Postconditions:**

- POST-1. **Added:** a new meteorite record exists in the content database with a `monnigNumber` no other record has, and it is visible to visitors.
- POST-2. **Edited:** the record holds the new values, photos, and placement.
- POST-3. **Hidden:** the record and its photos are still in the content database, marked hidden, and visitors cannot see it. **Restored:** the hidden mark is cleared, and visitors can see it again.
- POST-4. Visitors see the change the next time their app loads content, with no new app-store release (`MNT-content-update`).
- POST-5. The gallery's catalog at monnigcatalog.tcu.edu has not been changed (`DI-catalog-source-of-truth`).
- POST-6. If the use case ends without a successful save, nothing in the content database has changed.

**Main Success Scenario:** _(adding a meteorite)_

1. In the portal's meteorite list, the administrator chooses Add meteorite.
2. The system shows an empty meteorite form: the record fields, an English and a Spanish description, a photo area, and a display picker listing the gallery's existing displays grouped by room.
3. The administrator fills in the fields, writes the description, uploads photos (with optional captions, in the order they should appear), and optionally picks the display the meteorite is in.
4. The administrator saves.
5. The system checks that the session is still valid (`SEC-admin-authenticated`) and validates the form: required fields are present, the `monnigNumber` is not used by any other record (hidden ones included), and every field meets its rule in Associated Information.
6. The system saves the record and its photos together, and sets `onDisplay` from the placement (on display if a display was picked).
7. The system confirms that the meteorite was added and shows the meteorite list with the new meteorite in it.
8. Use case ends.

**Extensions:**

- **1a. The administrator selects an existing meteorite to edit.**
    - 1a1. The system loads the record and shows the form filled with its current values, photos, and display. The `monnigNumber` is shown but cannot be changed.
    - 1a2. The administrator changes any of the other fields, adds, removes, or reorders photos, edits captions, or changes or clears the display.
    - 1a3. Flow rejoins at step 4.
- **1a1a. The record cannot be loaded (the database cannot be reached, or the record no longer exists).**
    - 1a1a1. The system shows a message saying the meteorite could not be opened, and stays on the meteorite list.
    - 1a1a2. Use case ends.
- **1b. The administrator chooses Hide for a meteorite.**
    - 1b1. The system asks the administrator to confirm. The prompt names the meteorite and says that visitors will no longer see it, that visitors who saved it as a favorite will see it as no longer available, and that it can be restored later.
    - 1b2. The administrator confirms.
    - 1b3. The system checks the session (as in step 5) and marks the record hidden. The record and its photos are kept.
    - 1b4. The system confirms that the meteorite is hidden. In the meteorite list it is marked hidden and has a Restore control.
    - 1b5. Use case ends.
- **1b2a. The administrator cancels.**
    - 1b2a1. Nothing changes. Use case ends.
- **1c. The administrator chooses Restore for a hidden meteorite.**
    - 1c1. The system checks the session (as in step 5) and clears the hidden mark.
    - 1c2. The system confirms that the meteorite is visible to visitors again.
    - 1c3. Use case ends.
- **1b3a, 1c1a. The change cannot be saved.**
    - As in 6a, except the administrator is back on the meteorite list.
- **3a. An uploaded photo is not an accepted image type, or is larger than the size limit.**
    - 3a1. The system rejects that file, says why, and keeps everything else on the form. Accepted types and the size limit are left to the design.
    - 3a2. Flow continues at step 3.
- **5a. A required field is missing, or a field breaks its rule.**
    - 5a1. The system does not save. It marks each field with a problem and says what is wrong, and keeps everything the administrator entered.
    - 5a2. Flow rejoins at step 3.
- **5b. (Adding) The `monnigNumber` is already used by another record.**
    - 5b1. The system does not save, and says the number is already used by a named meteorite. If that meteorite is hidden, the system says so and offers to restore it (1c). Everything entered stays on the form.
    - 5b2. Flow rejoins at step 3.
- **5c. The session has expired or is no longer valid.**
    - 5c1. The system does not save, and refuses the change (`SEC-admin-authenticated`). It says the administrator must sign in again (`UC-ADM-log-in`).
    - 5c2. After the administrator signs in again, the system returns them to the form with their entries, and flow rejoins at step 4.
- **6a. The content database cannot be reached, or the save fails partway (for example, a photo fails to store).**
    - 6a1. The system saves nothing: the record and its photos are saved together or not at all. It says the change could not be saved and offers to try again. Everything entered stays on the form.
    - 6a2. If the administrator tries again, flow rejoins at step 5.
- **\*a. The administrator cancels, or leaves the form with unsaved changes.**
    - \*a1. The system asks whether to discard the unsaved changes.
    - \*a2. If the administrator discards them, nothing is saved, the system shows the meteorite list, and the use case ends. Otherwise flow continues where it was.

**Priority:** High. It is the most-proposed use case in the tally (4 votes, minutes 2026-11-09). Whether release 1.0 includes the admin portal is still `OI-11`.

**Frequency of Use:** Rare. Exhibits are mostly permanent (`BR-permanent-exhibit`), and there are two administrators. Changes come mostly when a new meteorite is acquired (such as a new Texas find); the client has not given a rate (interview, §7). With two administrators and rare changes, two people editing the same meteorite at once is unlikely; if it happens, the last save wins.

**Business Rules:** `BR-only-admin-can-edit-database`, `BR-permanent-exhibit`

**Associated Information:**

_Data fields (set by the administrator in the portal; visitors only read them, `FR-CONTENT-visitor-read-only`). Field definitions are in SRS §7.2; this table gives the rules the portal enforces:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `monnigNumber` | text | Required. Unique across all records, hidden ones included. Cannot be changed after the record is created (author's decision, 2026-11-15): favorites on visitors' devices are stored by it (`UC-DAT-save-favorite`). To fix a wrong number, hide the record and add a new one. | Set by an administrator only, at creation | Monnig # |
| `meteoriteName` | text | Required. Not translated (SRS §10). | Administrator only | Meteorite Name |
| `class` | enum | Optional. Iron, Stone, or Stony-iron. | Administrator only | Class |
| `group` | enum | Optional. Chondrite, Primitive achondrite, or Achondrite (list to confirm, SRS §7.2). | Administrator only | Group |
| `composition` | text | Optional. Allowed values TBD (`OI-4`). | Administrator only | — |
| `country` | text | Optional. | Administrator only | Country |
| `locationFound` | text | Optional. | Administrator only | — |
| `dateFound` | date or year | Optional. Not in the future. Precision TBD (`OI-4`). | Administrator only | — |
| `fall` | boolean | Optional. Whether the fall was observed. | Administrator only | Fall |
| `description` (English) | long text | Optional. | Administrator only | — |
| `description` (Spanish) | long text | Optional, even when the English one is filled in (author's decision, 2026-11-15). If it is empty, visitors using Spanish see the English text marked as not translated (`FR-LANG-content-fallback`). | Administrator only | — |
| `images` | list of Image | Optional. Each has an optional caption. The order set here is the order visitors see; the first is the hero in `UC-DAT-view-meteorite`. Accepted types and size limit are left to the design. | Administrator only. Image rights are open (`OI-15`). | — |
| `display` | reference to an existing Display | Optional. Chosen from the gallery's existing displays, grouped by room. The room comes from the display. This use case cannot add or rename displays or rooms (author's decision, 2026-11-15; `BR-permanent-exhibit`). | Administrator only | Display, Room |
| `onDisplay` | boolean | Not entered. Set by the system: true if a display is assigned, false if not, so the two never disagree (author's decision, 2026-11-15). | Set by the system | — |
| `hidden` | boolean | Default false. Set by Hide (1b) and Restore (1c), not by the form. | Administrator only. A hidden record is never sent to visitors. | — |

- **Going live.** A saved change is live right away, with no draft or approval step (author's decision, 2026-11-15). How and when the visitor app picks up changes (on launch, or more often; caching or not) is left to the design (minutes, 2026-11-06).
- **What visitors see of a hidden meteorite.** It does not appear in any list (browse, search, filter, favorites, exhibits, similar meteorites). If a visitor opens it from a favorite or from a list loaded before it was hidden, `UC-DAT-view-meteorite` 3b shows that it is no longer available.
- **Security.** Every save, hide, and restore is checked against the session on the server, not only in the browser (`SEC-admin-authenticated`). Every portal account is an administrator account, so a valid session is all the check needs; there are no roles or permission levels to check (author's decision, 2026-11-15). All traffic uses HTTPS (minutes, 2026-11-09).
- **Systemic failure.** Every change is all or nothing (6a). A record is never left saved without its photos, or with only some of its changes.
- **Not in this use case:** adding or renaming rooms and displays; 3D models (`OI-27`); visitor information such as hours (`UC-TOUR-view-visitor-info`); creating administrator accounts; loading the full collection at the start (`OI-4`).
- **SRS changes needed.** SRS §7.2 needs the `hidden` and `display` fields, and needs to show that `onDisplay` is derived from `display`. SRS §2 says it is open whether a back end exists at all (`OI-4`). This use case assumes one does.

**Related Use Cases:**

- `UC-ADM-log-in`: Log In as an Administrator. Signs the administrator in (PRE-1) and signs them back in at 5c.
- `UC-DAT-view-meteorite`: View a Meteorite. Shows what this use case saves. Its 3b covers a meteorite that has been hidden.
- `UC-DAT-browse-database`: Browse the Meteorite Database. Lists only meteorites that are not hidden.
- `UC-DAT-filter-database`: Organize Meteorite Catalog Based on Filters. Its on-display filter uses the `onDisplay` this use case sets.
- `UC-DAT-save-favorite`: Save a Favorite Meteorite. Stores the `monnigNumber`, which is why it is locked here.
- `UC-TOUR-view-exhibit` and `UC-TOUR-browse-gallery-section`: Show the meteorites placed in a display or room here.

**Assumptions:**

- The portal writes to the app's own content database, not to the gallery's catalog at monnigcatalog.tcu.edu. The catalog is never changed (`DI-catalog-source-of-truth`). Whether the content database starts as a copy of the catalog is `OI-4`.
- The portal is a browser-based tool, separate from the visitor app (minutes, 2026-11-09). Its layout is left to the design.
- The administrators are Dr. Mayne and Heather Stepp (minutes, 2026-11-09). Only administrators have portal accounts, and every account can do everything in this use case. Neither needs the other's approval.
- One record per `monnigNumber`, as in `UC-DAT-view-meteorite`. If the catalog separates a meteorite from its samples, this changes (`OI-4`).

**Open Issues:**

- `OI-11`: Whether the client wants an admin portal in release 1.0, or whether the team loads content. This use case assumes the portal.
- `OI-4`: Where the starting data comes from, which fields it has, and whether it separates a meteorite from its samples.
- `OI-5`: Who hosts and maintains the portal and content database after the team graduates.
- `OI-9`: Whether Spanish descriptions must be reviewed before they go live, and by whom. This use case has no review step.
- `OI-15`: Who owns the photos administrators upload, and what credit they need.
- `OI-27`: 3D models, which this use case does not manage.


---

## Working these with your agent

_[Delegate: drafting the main success scenario once you have the trigger and the goal; proposing extensions you have not thought of, which it is genuinely good at; turning a filled-in use case into a first set of test cases; checking that every `BR-*` you cite exists in [business-rules.md](business-rules.md).]_

_Keep human: whether this is one use case or three, what the priority is, and whether an extension the agent proposed is a real path in your client's business or a generic one it has seen elsewhere. "The system handles concurrent edits" is a real requirement for some projects and invented complexity for others, and only you have met the client._

_The verification that catches the most: read the main success scenario aloud to someone who has not read the document, and stop wherever they ask a question. Every question is a missing step or a missing extension._

_**Checklist for each use case:** Does the name start with a verb? Can the system test every precondition? Does every step alternate actor and system? Is there at least one extension per step that can fail? Does every business rule appear as an identifier only? Could a tester write test cases from this without asking you anything?_
