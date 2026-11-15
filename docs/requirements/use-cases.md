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
| PREF | User preferences | `UC-PREF-identify-language-preference`: Identifies User Language Preference<br>`UC-PREF-customize-visual-preferences`: Change Settings |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display |
| DAT | Meteorite catalog | `UC-DAT-display-database`: Display Meteorites in Catalog<br>`UC-DAT-filter-database`: Organize Meteorite Catalog Based on Specific Filters<br> `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite |

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


### UC-PREF-customize-visual-preferences: Change Settings

**UC ID and Name:** `UC-PREF-customize-visual-preferences`: Change Settings

**Created By:** Koen Dolezar (rewrite of Bradley Helmholz's November 3, 2026 draft)

**Date Created:** November 15, 2026

**Primary Actor:** Visitor (including child visitors with an adult's help)

**Secondary Actors:** Gallery staff (on a gallery tablet, if the gallery provides tablets, `OI-7`)

**Trigger:** The visitor selects Settings on the Home screen.

**Description:** After setup, the visitor changes their display preferences one at a time in Settings: language, text size, and light or dark mode. Each change applies to every screen as soon as it is selected and is saved on the device, so there is no separate confirm step. The Settings screen also holds the controls that belong to other use cases: voice speed, captions, retaking the setup survey, and resetting preferences. This use case keeps its original identifier, but its content replaces the earlier "Customize Visual Preferences" draft to match later team decisions: Settings is a screen reached from Home, not a popup on every screen (minutes 2026-11-06, 2026-11-09); font style is not offered (minutes 2026-11-09); and text size has three choices.

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

**Related Use Cases:**

- `UC-PREF-first-launch-survey` _(in review)_: Sets the same three preferences the first time the app opens.
- `UC-PREF-retake-setup-survey` _(in review)_: Runs the setup survey again from this screen.
- `UC-PREF-reset-preferences` _(in review)_: Returns every preference to its default from this screen.
- `UC-PREF-toggle-captions` _(in review)_: Turns captions on or off from this screen.
- `UC-TTS-voice-speed` _(in review)_: Sets the voice speed from this screen.
- `UC-TTS-play-in-selected-language` _(in review)_: Uses the language chosen here for reading aloud.

**Assumptions:**

- Preferences belong to the device, not to a person (SRS §7.1, `VisitorPreferences`).
- The defaults are those of `UC-PREF-first-launch-survey` (English, Medium, Light). If `OI-40` settles different defaults, 2a uses them.
- An adult helps a child visitor who cannot read the Settings screen yet.

**Open Issues:**

- `OI-8`: The SRS and the use cases disagree on whether preferences persist. This use case follows the 2026-11-02 decision that they persist (`FR-PREF-persist`).
- `OI-19`: Whether the accessibility standard requires more settings, such as font style or high contrast.
- `OI-40`: The defaults a preference falls back to when it cannot be read (2a).

## TTS: Text-to-speech



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


---

## Working these with your agent

_[Delegate: drafting the main success scenario once you have the trigger and the goal; proposing extensions you have not thought of, which it is genuinely good at; turning a filled-in use case into a first set of test cases; checking that every `BR-*` you cite exists in [business-rules.md](business-rules.md).]_

_Keep human: whether this is one use case or three, what the priority is, and whether an extension the agent proposed is a real path in your client's business or a generic one it has seen elsewhere. "The system handles concurrent edits" is a real requirement for some projects and invented complexity for others, and only you have met the client._

_The verification that catches the most: read the main success scenario aloud to someone who has not read the document, and stop wherever they ask a question. Every question is a missing step or a missing extension._

_**Checklist for each use case:** Does the name start with a verb? Can the system test every precondition? Does every step alternate actor and system? Is there at least one extension per step that can fail? Does every business rule appear as an identifier only? Could a tester write test cases from this without asking you anything?_
