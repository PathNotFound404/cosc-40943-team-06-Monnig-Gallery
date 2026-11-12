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
| PREF | User preferences | `UC-PREF-first-launch-survey`: Set Up Preferences on First Launch<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display |
| DAT | Meteorite catalog | `UC-DAT-display-database`: Display Meteorites in Catalog<br>`UC-DAT-filter-database`: Organize Meteorite Catalog Based on Specific Filters<br> `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite |

---

## 4. Use Cases

_[One `###` heading per use case, grouped under a `##` heading per area. Worked example below, taken from Project Pulse. Delete it and write your own.]_

## PREF: User preferences

### UC-PREF-first-launch-survey: Set Up Preferences on First Launch

**UC ID and Name:** `UC-PREF-first-launch-survey`: Set Up Preferences on First Launch

**Created By:** Cody Pinkston

**Date Created:** November 11, 2026

**Primary Actor:** Visitor (including child visitors with an adult's help)

**Secondary Actors:** Gallery staff (they may hand a visitor a gallery tablet, if the gallery provides tablets)

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
2. The system checks that no setup survey has been completed on this device and shows the language screen. This screen holds only the language choice: English and Spanish.
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

**Frequency of Use:** Once per installation, on each visitor's own device. It runs again only after a reset (`UC-PREF-reset-preferences`) or a retake (`UC-PREF-retake-setup-survey`). If the gallery provides shared tablets (`OI-7`), it runs once per visitor, after each "new visitor" reset (`FR-PREF-reset-for-new-visitor`). Every run stays on the device, so it adds no load to any server.

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
- **Accessibility.** Every control must work with the device's screen reader, since visually impaired visitors set their preferences here before anything else. The required standard depends on `BR-accessibility-standard` (`OI-3`).
- **Default color mode.** Light (`OI-18`, resolved 2026-11-11). A future version may preselect the device's own light or dark setting instead.
- **Out of scope.** Font style is not asked (dropped unless an accessibility standard requires it, minutes 2026-11-09). The grant's visitor-demographics questions (`BR-visitor-survey-data`, `FR-SURVEY-optional`) are not part of this use case (`OI-10`, `OI-16`).

**Related Use Cases:**

- `UC-PREF-customize-visual-preferences`: Changes the same preferences later, from Settings.
- `UC-PREF-retake-setup-survey` _(not yet written)_: Runs this survey again from Settings, starting at step 2 with the current preferences preselected. Leaving it before step 6 keeps the existing preferences.
- `UC-PREF-reset-preferences` _(not yet written)_: Clears the preferences and the survey-complete record, so this use case runs on the next launch (PRE-2).

**Assumptions:**

- The visitor completes or skips the survey before reaching the Home screen. Nothing else in the app is reachable during the survey.
- Preferences belong to the device, not to a person (SRS §7.1, `VisitorPreferences`).
- An adult helps a child visitor who cannot read the survey yet.

**Open Issues:**

- `OI-19`: Will the accessibility standard (`OI-3`) require more questions at setup, such as font style, high contrast, or turning text-to-speech on?


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

**Related Use Cases:** `UC-PREF-first-launch-survey`

**Assumptions:** The UI element to open the visual preferences popup is always visible on the application.

**Open Issues:**

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
