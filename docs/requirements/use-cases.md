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
| PREF | User preferences | `UC-PREF-identify-language-preference`: Identifies User Language Preference<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage<br>`UC-PREF-retake-setup-survey`: Retake the Setup Survey |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display<br>`UC-TTS-control-playback`: Control Text-to-Speech Playback |
| DAT | Meteorite catalog | `UC-DAT-display-database`: Display Meteorites in Catalog<br>`UC-DAT-filter-database`: Organize Meteorite Catalog Based on Specific Filters<br> `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite<br>`UC-DAT-browse-database`: Browse the Meteorite Database |
| TOUR | Gallery tour | `UC-TOUR-browse-gallery-section`: Browse a Gallery Section |

---

## 4. Use Cases

_[One `###` heading per use case, grouped under a `##` heading per area. Worked example below, taken from Project Pulse. Delete it and write your own.]_

## PREF: User preferences

### UC-PREF-identify-language-preference: Identifies User Language Preference

**UC ID and Name:** `UC-PREF-identify-language-preference`: Identifies User Language Preference

**Created By:** Kendric D’Spain, Bradley Helmholz

**Date Created:** October 16, 2021

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum volunteers

**Trigger:** A user starts an app for the first time the user tours the Monnig Meteorite Gallery.

**Description:** The user starts up the TCU MMG mobile app for the first time and prompts the user for their preferred language. The user is able to select their preferred language out of the two currently supported, English and Spanish


**Preconditions:**

**Postconditions:**

- POST-1. The user’s language preference is temporarily stored and the remaining session of the gallery should illustrate the displays in the preferred language.

**Main Success Scenario:**

1. The system requests the user to choose their preferred language, displayed to user with language name and appropriate country flag.
2. The user selects their preferred language.
3. The system applies the preference to the current session.
4. Use case ends.

**Extensions:**

- **1a. The User does not provide a language preference and tries to proceed**
    - 1a1. The system defaults language to English.
    - 1a2. Use case ends.

**Priority:** High

**Frequency of Use:** Everytime the MMG application is opened, and the user is ready to tour the Gallery.

**Business Rules:**

**Associated Information:**

1. The user is able to change their preferred language anytime throughout the gallery as well.

**Related Use Cases:**

**Assumptions:** Assume that the user must complete the language preference selection prior to starting his/her tour at TCU’s Monnig Meteorite Gallery.

**Open Issues:**


### UC-PREF-customize-visual-preferences ###

**UC ID and Name:** `UC-PREF-customize-visual-preferences`: Customize Visual Preferences

**Created By:** Bradley Helmholz

**Date Created:** November 3, 2026

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum Volunteers, Museum Staff

**Trigger:** User selects a UI element on the screen to edit their visual preferences

**Description:** The user presses a UI element on the app screen, which directs them to a page to set their visual preferences for the application, including previews for their selections

1. Font Size
2. Font Style
3. Change Language (with language name and country flag)
4. Dark mode vs Light mode


**Preconditions:** 

- PRE-1. The user has already opened the application and passed the home screen.

**Postconditions:**

- POST-1. The user's visual preference changes are previewed to them before they confirm changes.
- POST-2. The user's visual preferences are stored and persists for the remainder of the current instance of the application running.

**Main Success Scenario:**

1. The user interacts with a UI element to change their current visual preferences.
2. The system responds by opening a popup page centered on the screen listing the visual preference options, all of which can be selected and changed in any order.
3. The system requests the user to select their preferred font style, from a choice of four.
4. The system requests the user to select their prefrerred font size, from a choice of four.
5. The system requests the user to select their preferred language, with both language name and appropriate country flag presented to the user
6. The system presents a toggle between light mode and dark mode, which applies to the entire application
7. The user can select from any available options the system presents to the user for visual preferences.
8. All selections the user makes before confirming their choices are shown immediately througout the application
9. The user confirms their selections.
10. The system applies the selected changes from all preferences across the application to the current instance.
11. Use case ends.

**Extensions:**

- **7a. The user does not make any selections.**
    - 7a1. No changes are made to the applications UI.
    - 7a2. Use case ends.
- **9a. The user does not confirm their selections**
    - 9a1. No selected changes take hold in the current application's session.
    - 9a2. The UI returns to its settings prior to the user interacting with the visual preferences setting.
    - 9a3. Use case ends.

**Priority:** Medium

**Frequency of Use:** User can access settings to change visual preferences at any point in the application. The UI element is never hidden or hard to find.

**Business Rules:**

**Associated Information:**

**Related Use Cases:** `UC-PREF-identify-language-preference`

**Assumptions:** The UI element to open the visual preferences popup is always visible on the application.

**Open Issues:**


### UC-PREF-retake-setup-survey: Retake the Setup Survey

**UC ID and Name:** `UC-PREF-retake-setup-survey`: Retake the Setup Survey

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor (including child visitors with an adult's help)

**Secondary Actors:** None

**Trigger:** The visitor selects "Retake setup survey" in Settings.

**Description:** A visitor who has already finished or skipped the setup survey runs it again on purpose, from Settings. The retake uses the same two screens and the same questions as `UC-PREF-first-launch-survey`, but every question starts with the visitor's current preference selected instead of the default. Each answer takes effect as soon as it is chosen, so the visitor sees the result before moving on. Finishing saves the answers shown in place of the previous preferences; quitting before then puts the previous preferences back and saves nothing. This use case is not Change settings, which edits one preference at a time in Settings, and not `UC-PREF-reset-preferences`, which goes back to the defaults.

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
2. The system notes the preferences currently in effect as the restore point, and shows the language screen with the current language selected.
3. The visitor selects a language and continues.
4. The system switches all survey text to that language and shows the preferences screen, with the current text size and current color mode selected. Each choice takes effect on this screen as soon as it is selected, so the screen itself is the preview.
5. The visitor selects a text size and a color mode, in either order, and confirms.
6. The system saves the three preferences on the device in place of the previous ones, and returns the visitor to Settings with the new preferences applied.
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
- **\*a. On either screen (steps 2 to 5), the visitor chooses Skip.**
    - \*a1. The system keeps every selection now shown on the survey screens, and keeps the restore-point value, not the default, for any question the visitor has not reached.
    - \*a2. Flow rejoins at step 6.
- **\*b. The visitor quits the retake before step 6, by going back from the language screen (the on-screen Back control or the device's Back action).**
    - \*b1. The system applies the restore-point preferences to every screen again and saves nothing.
    - \*b2. The system returns the visitor to Settings.
    - \*b3. Use case ends.
- **\*c. The app is closed or killed by the operating system before step 6.**
    - \*c1. The system saves nothing. Choices that were only shown on screen are discarded.
    - \*c2. On the next launch, the system restores the previously saved preferences. The survey-complete record is unchanged, so the first-launch survey does not run.
    - _If the app is only sent to the background and then resumed, the retake continues on the same screen with its selections intact._
- **6a. Saving the preferences fails (for example, the device storage is full).**
    - 6a1. The system keeps the new preferences applied for the current session and returns the visitor to Settings.
    - 6a2. The system shows a non-blocking message in the selected language saying the preferences could not be saved and the previous ones will return the next time the app opens.
    - 6a3. The preferences saved on the device stay as they were before the retake.
    - 6a4. Use case ends.
- **\*d. The device has no network connection.**
    - \*d1. No change. The retake needs no network, and both screens work offline (`ROB-offline`).

**Priority:** Low

**Frequency of Use:** Rare. Expected only when a visitor wants to go through every setup question again rather than change one setting; most changes go through Settings. Every run stays on the device, so it adds no load to any server.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-branding`

**Associated Information:**

_Data fields:_ this use case writes the same stored fields as `UC-PREF-first-launch-survey` (`language`, `textSize`, `colorMode`, and the survey-complete record `setupSurveyCompleted`), under the same validation rules; they are defined there and not repeated here. One value exists only while the retake is open:

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `restorePoint` | record of `language`, `textSize`, `colorMode` | Required; set at step 2 from the preferences in effect. Discarded at step 6 or when the use case ends. | Held in memory only; never saved | — |

- **Atomic save.** Step 6 writes all three preferences together, or writes none of them. A failure never leaves a mix of old and new values saved (see 6a). `setupSurveyCompleted` is not written, because it is already `true` (PRE-1).
- **Same screens.** The survey screens, their language labels, the layout rule at every text size (`USE-text-scaling`), and the screen-reader requirement (`USE-screen-reader`) are those of `UC-PREF-first-launch-survey`. Any question added to that survey (`OI-19`) appears in the retake as well.
- **Why the restore point exists.** Choices take effect as soon as they are made, so quitting (\*b) has to undo them. The restore point is what the system goes back to.
- **Where the visitor ends up.** Settings, because that is where the retake started. The first-launch survey ends on Home instead.

**Related Use Cases:**

- `UC-PREF-first-launch-survey`: Owns the survey screens and questions that this use case runs again.
- `UC-PREF-customize-visual-preferences` (Change settings): Changes one preference at a time in Settings, without the survey.
- `UC-PREF-reset-preferences` _(not yet written)_: Clears the preferences and the survey-complete record, so the first-launch survey runs with defaults on the next launch. The retake keeps the record and starts from the current values.

**Assumptions:**

- Settings is reached from the Home screen (minutes, 2026-11-09), and the "Retake setup survey" control is in Settings. It starts the retake with no confirmation prompt, because nothing is lost until step 6.
- Quitting means going back from the language screen. The survey screens have no separate Cancel control.
- "Current value" means the preference in effect when the retake starts. This is normally the saved value, or a session-only value after a failed save.
- The ID `UC-PREF-reset-preferences` is the one `UC-PREF-first-launch-survey` already uses for a use case not yet written.

**Open Issues:**

- `OI-19`: If the accessibility standard adds setup questions, the retake asks them too.


## TTS: Text-to-speech

### UC-TTS-control-playback: Control Text-to-Speech Playback

**UC ID and Name:** `UC-TTS-control-playback`: Control Text-to-Speech Playback

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The device's text-to-speech engine, or a paid speech service (`SI-device-speech`, `DE-device-tts`)

**Trigger:** While text-to-speech is reading aloud or paused on the current screen, the visitor selects Pause, Resume, Replay, Skip forward, or Skip back.

**Description:** Once Listen to content has started reading a piece of text aloud, the visitor can pause and resume it, replay it from the beginning, or skip forward or back one paragraph at a time. The controls appear on the screen that is reading, for as long as reading is active, paused, or finished on that screen. Leaving the screen still stops reading (`FR-TTS-stop-on-leave`). Starting reading, stopping it, choosing the voice language, and changing the speed belong to other use cases.

**Preconditions:**

- PRE-1. Text-to-speech, started by `UC-TTS-listen-to-content`, is reading or paused on the screen the visitor is viewing.
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
- **\*b. While reading, the app goes to the background or the device screen locks.**
    - \*b1. The system pauses reading where it is, as in step 2.
    - \*b2. When the visitor returns, reading is still paused with Resume shown. It never resumes by itself.
    - \*b3. Flow rejoins at step 3.
- **\*c. While reading, a phone call or another app's audio interrupts.**
    - \*c1. The system pauses reading where it is, as in step 2.
    - \*c2. When the interruption ends, reading stays paused until the visitor selects Resume.
    - \*c3. Flow rejoins at step 3.
- **\*d. While reading, the audio output is disconnected (wired headphones unplugged, or Bluetooth headphones disconnect).**
    - \*d1. The system pauses reading where it is, as in step 2, so it does not continue unexpectedly through the device's speaker.
    - \*d2. Flow rejoins at step 3.
- **\*e. The device's volume is muted or turned all the way down.**
    - \*e1. No change. The system keeps reading and does not detect or change the device volume. The visitor raises the volume with the device's own controls.
- **\*f. The speech engine fails while resuming, skipping, or replaying (an engine error, or the voice for the selected language is no longer available).**
    - \*f1. The system stops reading and shows a message in the selected language saying reading could not continue. It does not read in a different language (`SI-device-speech`).
    - \*f2. The system keeps Replay available, and the rest of the screen stays usable.
    - \*f3. If the visitor selects Replay and the engine works, flow rejoins at step 10. Otherwise use case ends.

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
- **Systemic failure.** This use case makes no durable change, so a failure leaves nothing to roll back (see \*f).

**Related Use Cases:**

- `UC-TTS-listen-to-content` _(not yet written)_: Starts and stops reading aloud. This use case controls reading that it started (PRE-1).
- `UC-TTS-voice-speed` _(not yet written)_: Changes the reading speed.
- `UC-TTS-play-in-selected-language` _(not yet written)_: Chooses the language of the voice.

**Assumptions:**

- Stopping reading outright, as opposed to pausing it, belongs to `UC-TTS-listen-to-content` (`FR-TTS-read-description`). This use case covers Pause, Resume, Replay, and Skip.
- Skip back always goes to the start of the previous paragraph, even in the middle of the current one; it does not first restart the current paragraph.
- Skipping while paused keeps reading paused (5a).
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-3`: Which accessibility standard applies.
- `OI-20`: Does the accessibility standard require more from these controls?
- `OI-21`: Does the text being read come with paragraph breaks?
- `OI-22`: Is resuming from the start of the paragraph acceptable where a speech engine cannot resume mid-paragraph?


## DAT: Meteorite database

### UC-DAT-display-databse: Displays Meteorites in Catalog

**UC ID and Name:** `UC-DAT-display-database`: Displays Meteorites in Catalog

**Created By:** Aparajita Biswas, Bradley Helmholz

**Date Created:** November 03, 2021

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum Volunteers, Museum Staff

**Trigger:** The user selects "Meteorite Database" in the application.

**Description:** The user navigates to the section of the application that displays a list of all of the meteorites present in Monnig's meteorite collection database.

**Preconditions:**

- PRE-1. The user has already opened the application and passed the home screen.
- PRE-2. The application can query the database with all needed information regarding all available meteorites.

**Postconditions:**

- POST-1. The system displays a list of all meteorites in the Monnig database.
- POST-2. The user can scroll down the list of meteorites to select them (`UC-DAT-display-meteorite`), or further refine their search (`UC-DAT-filter-database`).

**Main Success Scenario:**

1. The user indicates to view the full meteorite catalog.
2. The system moves the user to a new page to display the list of meteorites.
3. The system queries the database to retrieve all meteorites according to active filters.
4. The database returns all queried meteorites.
5. The system displays all meteorites in small card form in a list that can be scrolled down to the user.
6. The card shows only the name/label of the meteorite as well as the picture of the meteorite if applicable.
6. User can select a meteorite (`UC-DAT-display-meteorite`) or further filter (`UC-DAT-filter-database`).
7. Use case ends.

**Extensions:**

- **3a. The system is unable to query the database.**
    - 3a1. The system reports the failure to retrieve all information from the database to the user.
    - 3a2. The page remains blank with an error message, prompting the user to try again later.
    - 3a3. User can try refreshing the page or leave.
    - 3a3. Use case ends.
- **4a. The database fails to return one or more queried meteorites.**
    - 4a1. The system reports the failture to retrieve all information from the database to the user.
    - 4a2. The page remains blank with an error message, prompting the user to try again later.
    - 4a3. User can try refreshing the page or leave.
    - 4a3. Use case ends.

**Priority:** High

**Frequency of Use:** For all times that the application is running, as the user can view the catalog at any time.

**Business Rules:**

**Associated Information:** The database for all relevant information is located at monnigcatalog.tcu.edu

**Related Use Cases:** `UC-DAT-filter-database`, `UC-DAT-display-meteorite`

**Assumptions:** Assumes user and application has internet access. Assumes the meteorites present in the database have been inputted correctly.

**Open Issues:**


### UC-DAT-filter-database: Organize Meteorite Catalog Based on Filters

**UC ID and Name:** `UC-DAT-filter-database`: Organize Meteorite Database Based on Filters

**Created By:** Asa Tuten, Bradley Helmholz

**Date Created:** 5/4/2022

**Primary Actor:** Monnig Visitor

**Secondary Actors:** Museum Volunteer, Museum Staff

**Trigger:** User selects the Filter button button at the top of the screen.

**Description:** The app is equipped with being able to query meteorites for visitors to look at, whether the meteorite is on display in the gallery or not. The user can filter out meteorites based a variety of categories. Prior to user selections all filters are defaultly set to ALL.

1. Type of meteorite
2. Composition of meteorite
2. Location of find
3. Time range of find
3. Whether or not the meteorite is on display

**Preconditions:**

- PRE-1. The user is in the "Meteorite Database" page of the application.
- PRE-2. The application is currently able to query information from the database.

**Postconditions:**

- POST-1. The selected filters become active
- POST-2. The page is automatically refreshed showing meteorites with updated filters.

**Main Success Scenario:**

1. User selects the "Filter" button located at the top of the Meteorite Database page.
2. System reveals the filter bar dropdown.
3. Filter bar lists filter options and categories.
4. User can select and change the filters
5. For the category pertaining to location, user can either select from an additional dropdown, or begin to type in their location, which will be automatically be text-matched from options present in the location dropdown.
6. The time range filter has both a two node sliding time range line, as well as manual numerical input.
7. The user indicates to apply current filters.
8. System queries Monnig database with new filters.
9. Database returns all meteorites that fit all filters.
10. System displays selected meteorites to user.
11. Use case ends.

**Extensions:**

- **2a. User wishes to collapse the filter bar.**
    - 2a1. The user indicates to collapse the filter bar through a UI button.
    - 2a2. The filter bar collapses back to how it was before it was opened.
    - 2a2. Use case ends.
- **7a. User does not indicate to apply current filters and collapses the filter bar.**
    - 7a1. No filters are applied, and all filter settings are reset to default.
    - 7a2. Use case ends.
- **8a. The system is unable to query the database.**
    - 8a1. The system reports the failure to retrieve all information from the database to the user.
    - 8a2. The page remains blank with an error message, prompting the user to try again later.
    - 8a3. User can try refreshing the page or leave.
    - 8a4. Use case ends.
- **9a. The database fails to return one or more queried meteorites.**
    - 9a1. The system reports the failture to retrieve all information from the database to the user.
    - 9a2. The page remains blank with an error message, prompting the user to try again later.
    - 9a3. User can try refreshing the page or leave.
    - 9a4. Use case ends.
- **9b. There are no meteorites that fit all applied filters**
    - 9b1. The database indicates to the system that there are no meteorites that fit the current filters.
    - 9b2. The system does not display a list of meteorites, instead showing a message stating "No meteorites match current filters."
    - 9b3. User is prompted to change their filters.
    - 9b4. Use case ends.

**Priority:** Medium

**Frequency of Use:** Any time a user wants to view a specific selection meteorites.

**Business Rules:**

**Associated Information:**

**Related Use Cases:** `UC-DAT-display-database`

**Assumptions:** Assumes user and application has internet access. Assumes the meteorites present in the database have been inputted correctly.

**Open Issues:**


### UC-DAT-display-meteorite: Display Information Regarding a Single Meteorite

**UC ID and Name:** `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite

**Created By:** Kendric D’Spain, Bradley Helmholz

**Date Created:** November 3, 2021

**Primary Actor:** Monnig Gallery Visitor

**Secondary Actors:** Museum Volunteers, Museum Staff

**Trigger:** The user selects a meteorite he/she wants to view in detail.

**Description:** A user visiting the Gallery wants to be able to view a specific meteorite on the application. In the Meteorite Database page they select a meteorite information card from the list, creating a large centered popup showing them information regarding the meteorite.


**Preconditions:** 

- PRE-1. The user has already opened the application and passed the home screen.
- PRE-2. The user is in the Meteorite Database page.
- PRE-3. The database has been properly queried and there are meteorite cards present on the page in a list to select.

**Postconditions:**

- POST-1. The user can view a specific meteorite from the Monnig collection.
- POST-2. The screen displays all relevant information pertaining to the meteorite, including and not limited to: name, type, origin, and date of discovery.

**Main Success Scenario:**

1. The user selects a specific meteorite to view in detail.
2. A large centered screen popup of the selected meteorite opens.
3. The system queries the database for the selected meteorite for all needed information.
4. The database returns requested information to the system.
5. The system displays all information for the selected meteorite to the viewer.
6. The user can close the popup by either clicking outisde of the popup or pressing the X button in the top right corner
7. Use case ends.

**Extensions:**

- **3a. The system is unable to query the database.**
    - 3a1. The system reports the failure to query information from the database to the user.
    - 3a2. The popup remains blank with an error message, prompting the user to try again later.
    - 3a3. User can try refreshing the page or leave.
    - 3a4. Use case ends.
- **4a. The database fails to return the queried meteorites.**
    - 4a1. The system reports the failture to retrieve the meteoirte from the database to the user.
    - 4a2. The page remains blank with an error message, prompting the user to try again later.
    - 4a3. User can try refreshing the page or leave.
    - 4a4. Use case ends.
- **4b. Certain information on the selected meteorite is not present in the database.**
    - 4b1. The database returns null for the specific pieces of information not present for the meteorite in the database
    - 4b2. When displaying missing/unknown information on the meteorite to the user, the system states [NOT INDICATED] in bold red text
    - 4b3. System displays all known information on the meteorite normally.
    - 4b4. Use case ends.


**Priority:** High

**Frequency of Use:** Every time the application is used, as many times as the user wants to.

**Business Rules:**

**Associated Information:**

**Related Use Cases:** `UC-DAT-display-database`

**Assumptions:** Assumes user and application has internet access. Assumes the meteorites present in the database have been inputted correctly.

**Open Issues:**


### UC-DAT-browse-database: Browse the Meteorite Database

**UC ID and Name:** `UC-DAT-browse-database`: Browse the Meteorite Database

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects the Meteorite Database on the Home screen.

**Description:** The visitor opens the list of every meteorite in the Monnig collection, on display or not, and scrolls through it in alphabetical order by name. The list loads in batches as the visitor scrolls, so the first meteorites appear without waiting for the whole collection of about 3,000 to load (`SCA-full-collection`). Selecting a meteorite opens it in View meteorite. Searching, filtering, and showing only items on display are separate use cases. This use case supersedes `UC-DAT-display-database`.

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
- **3a. The catalog cannot be reached, returns an error, or returns only part of the first batch.**
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

- `UC-DAT-view-meteorite` _(not yet written; today `UC-DAT-display-meteorite`)_: View meteorite. Opens the meteorite selected at step 7.
- `UC-DAT-search-database` _(not yet written)_: Search database. Reached from this list (\*a).
- `UC-DAT-filter-database`: Filter database. Reached from this list (\*a).
- `UC-DAT-view-on-display-items` _(not yet written)_: View on-display items. Lists only the meteorites on display.
- `UC-DAT-save-favorite` _(not yet written)_: Save favorite. Saving a favorite happens there, not from this list.
- `UC-DAT-display-database`: Superseded by this use case.

**Assumptions:**

- The list has one item per catalog record. If the catalog holds several samples of the same meteorite, its name appears more than once (see `OI-4` on meteorite versus sample).
- List items have no favorite control. Favoriting belongs to Save favorite.
- The list keeps its place only while the visitor goes to View meteorite and comes back (8a). Leaving for Home resets it (\*b).
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-4`: Where the meteorite data comes from, and whether the catalog distinguishes a meteorite from its samples.
- `OI-12`: Whether the full list must be readable offline. Today only data already loaded is promised (`ROB-offline`).
- `OI-13`: The load-time threshold for `PER-database-list`.


## TOUR: Gallery tour

### UC-TOUR-browse-gallery-section: Browse a Gallery Section

**UC ID and Name:** `UC-TOUR-browse-gallery-section`: Browse a Gallery Section

**Created By:** Tanner Temple

**Date Created:** November 11, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The source of gallery section content (`OI-24`)

**Trigger:** The visitor selects Gallery on the Home screen, or View gallery map hands off a room or a section the visitor chose.

**Description:** Each of the gallery's three rooms is divided into themed sections. The client interview (§2) walks several, such as the asteroid belt, the types of meteorites, collisions, and the all-Texas room. The visitor sees the sections grouped by room, in the order a visitor walks the gallery. They open one to see its name, its room, its description, and the displays it holds. Selecting a display opens it in View exhibit. The gallery map, a single exhibit's details, the guided order of a self-guided tour, and visitor information are separate use cases.

**Preconditions:**

- PRE-1. The setup survey has been completed or skipped on this device, so the Home screen is reachable.

**Postconditions:**

- POST-1. The visitor has seen the list of sections and, if they chose one, its details and displays.
- POST-2. If the visitor selected a display, View exhibit has opened with that display.
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Gallery on the Home screen.
2. The system requests the list of gallery sections.
3. The content source returns the sections.
4. The system shows the sections grouped under the room each one is in, with rooms and sections in the order a visitor walks the gallery.
5. The visitor selects a section.
6. The system shows the section screen: the section's name, its room, its description, and the list of displays in it by display name.
7. The visitor selects a display.
8. The system opens the selected display in View exhibit.
9. Use case ends.

**Extensions:**

- **1a. The visitor arrives from View gallery map with a section chosen.**
    - 1a1. The system requests that section's details.
    - 1a2. Flow continues at step 6.
- **1b. The visitor arrives from View gallery map with a room chosen.**
    - 1b1. Flow continues at step 2. At step 4 the system shows the full list, scrolled to the chosen room's sections.
- **2a. The device has no network connection, and the app has loaded section content before (`ROB-offline`).**
    - 2a1. The system shows the sections it already has.
    - 2a2. Flow continues at step 4.
- **3a. The section list cannot be loaded.**
    - 3a1. The system shows a message saying the gallery sections could not be loaded, with a way to try again (`FR-DATA-load-failure`). The rest of the app stays usable.
    - 3a2. If the visitor tries again, flow rejoins at step 2. Otherwise use case ends.
- **3b. No sections are defined.**
    - 3b1. The system shows a message saying gallery sections are not available, instead of an empty list.
    - 3b2. Use case ends.
- **3c. A section has no room recorded.**
    - 3c1. The system lists it at the end, under "[NOT INDICATED]" as its room (`FR-DATA-missing-field`).
    - 3c2. Flow continues at step 4.
- **6a. The section has no description, or no description in the selected language.**
    - 6a1. With no description at all, the system shows "[NOT INDICATED]" in its place (`FR-DATA-missing-field`).
    - 6a2. With an English description only, the system shows the English text, marked as not translated (`FR-LANG-content-fallback`, Proposed).
    - 6a3. Flow continues at step 7.
- **6b. The section has no displays.**
    - 6b1. The system shows the section's name, room, and description, with a message saying no displays are listed for this section.
    - 6b2. The visitor goes back, and flow rejoins at step 4.
- **6c. The section's details cannot be loaded.**
    - 6c1. The system shows a message on the section screen saying the section could not be loaded, with a way to try again (`FR-DATA-load-failure`).
    - 6c2. If the visitor tries again, flow rejoins at step 6. Going back to the section list still works (6d).
- **6d. The visitor goes back from the section screen.**
    - 6d1. The system shows the section list at the same place.
    - 6d2. Flow rejoins at step 5.
- **\*a. The visitor leaves for the Home screen.**
    - \*a1. Use case ends.

**Priority:** Medium

**Frequency of Use:** Mostly by visitors in the gallery, a few times per visit as they move between rooms; remote visitors can use it too (`OE-remote-use`). The gallery's exhibits are mostly permanent (`BR-permanent-exhibit`), so section content rarely changes.

**Business Rules:** `BR-permanent-exhibit`, `BR-only-admin-can-edit-database`, `BR-accessibility-standard`

**Associated Information:**

_Data fields. All are **Proposed**: the SRS domain model (§7.1) goes Gallery → Room → Display and has no Section yet, and where this content comes from is open (`OI-24`):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `sectionName` | text, per language | Required | Read-only to visitors; set by administrators | _Section (not yet in the glossary)_ |
| `room` | reference to a Room | Required; one of the gallery's three rooms. If missing, see 3c. | Read-only to visitors | Room |
| `order` | integer | Required; unique across the gallery. The section's place in the order a visitor walks the gallery. | Read-only to visitors | — |
| `description` | long text, per language | Optional; see 6a | Read-only to visitors | — |
| `displays` | ordered list of Display | Optional; may be empty (see 6b) | Read-only to visitors | Display |

- **Order.** Sections are shown in `order`. Rooms are shown in the order of their first section.
- **Language.** Section names and descriptions are shown in the selected language, falling back to English per `FR-LANG-content-fallback`. Interface text follows `FR-LANG-interface-text`.
- **Accessibility.** Every section and display in the lists has a screen-reader label (`USE-screen-reader`) and stays readable at every text size (`USE-text-scaling`).
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-TOUR-view-gallery-map` _(not yet written)_: View gallery map. Can hand off a chosen room or section (1a, 1b).
- `UC-TOUR-view-exhibit` _(not yet written)_: View exhibit. Opens the display selected at step 7.
- `UC-TOUR-self-guided-tour` _(not yet written)_: Self-guided tour. Moves the visitor through the sections in order, including any next and previous section controls.
- `UC-TOUR-visitor-info` _(not yet written)_: Visitor info. Hours and location; not shown here.

**Assumptions:**

- A section is a themed area inside exactly one room, and each display belongs to exactly one section.
- Samples are not listed on the section screen. The visitor reaches them through View exhibit.
- "Gallery" is a working label for the Home screen entry. The design names it.
- Reading a section's description aloud is not part of this use case. `FR-TTS-read-description` covers meteorite descriptions only.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-23`: What are the gallery's sections, which room is each in, in what order, and which displays does each hold?
- `OI-24`: Where do section names, descriptions, and display lists come from, and who keeps them current?
- `OI-25`: Is this use case in release 1.0, given that `FEAT-section-screens` is listed as out of MVP scope?


---

## Working these with your agent

_[Delegate: drafting the main success scenario once you have the trigger and the goal; proposing extensions you have not thought of, which it is genuinely good at; turning a filled-in use case into a first set of test cases; checking that every `BR-*` you cite exists in [business-rules.md](business-rules.md).]_

_Keep human: whether this is one use case or three, what the priority is, and whether an extension the agent proposed is a real path in your client's business or a generic one it has seen elsewhere. "The system handles concurrent edits" is a real requirement for some projects and invented complexity for others, and only you have met the client._

_The verification that catches the most: read the main success scenario aloud to someone who has not read the document, and stop wherever they ask a question. Every question is a missing step or a missing extension._

_**Checklist for each use case:** Does the name start with a verb? Can the system test every precondition? Does every step alternate actor and system? Is there at least one extension per step that can fail? Does every business rule appear as an identifier only? Could a tester write test cases from this without asking you anything?_
