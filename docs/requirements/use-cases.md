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
| 11/15/26 | 2.1 | Draft `UC-ADM-update-content` | Cody Pinkston |

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
| PREF | User preferences | `UC-PREF-identify-language-preference`: Identifies User Language Preference<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display |
| DAT | Meteorite catalog | `UC-DAT-display-database`: Display Meteorites in Catalog<br>`UC-DAT-filter-database`: Organize Meteorite Catalog Based on Specific Filters<br> `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite |
| ADM | Content administration | `UC-ADM-update-content`: Update Gallery Content |

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


## ADM: Content administration

### UC-ADM-update-content: Update Gallery Content

**UC ID and Name:** `UC-ADM-update-content`: Update Gallery Content

**Created By:** Cody Pinkston

**Date Created:** November 15, 2026

**Primary Actor:** Gallery administrator (Dr. Mayne or Heather Stepp, minutes 2026-11-09; SRS §2 user classes)

**Secondary Actors:** The content database: the database the admin portal writes to and the visitor app reads from (`OI-4`). The visitor app, which picks up the change.

**Trigger:** In the admin portal, the signed-in administrator chooses Add meteorite, or selects an existing meteorite in the portal's meteorite list to edit, hide, or restore it.

**Description:** A gallery administrator keeps the app's meteorite content current without a developer and without a new app-store release (`MNT-content-update`). From a browser-based admin portal (minutes, 2026-11-09), the administrator adds a new meteorite, edits an existing one, hides one so visitors no longer see it, or restores a hidden one. A meteorite's content is its record fields (SRS §7.2), its description in English and Spanish, its photos, and the gallery display it is in. Saved changes go live right away: visitors see them the next time their app checks for changes. Hiding keeps the record so it can be restored, which is how this use case "removes" a meteorite. Signing in is its own use case (`UC-ADM-log-in`).

**Preconditions:**

- PRE-1. The administrator is signed in to the admin portal (`UC-ADM-log-in`), and the session has not expired.

**Postconditions:**

- POST-1. **Added:** a new meteorite record exists in the content database with a `monnigNumber` no other record has, and it is visible to visitors.
- POST-2. **Edited:** the record holds the new values, photos, and placement.
- POST-3. **Hidden:** the record and its photos are still in the content database, marked hidden, and visitors cannot see it. **Restored:** the hidden mark is cleared, and visitors can see it again.
- POST-4. After any of these changes, the record's `lastEdited` and the database's `contentLastChanged` are the time of the change, and visitors see the change the next time their app checks for changes, with no new app-store release (`MNT-content-update`).
- POST-5. The gallery's catalog at monnigcatalog.tcu.edu has not been changed (`DI-catalog-source-of-truth`).
- POST-6. If the use case ends without a successful save, nothing in the content database has changed.

**Main Success Scenario:** _(adding a meteorite)_

1. In the portal's meteorite list, the administrator chooses Add meteorite.
2. The system shows an empty meteorite form: the record fields, an English and a Spanish description, a photo area, and a display picker listing the gallery's existing displays grouped by room.
3. The administrator fills in the fields, writes the description, uploads photos (with optional captions, in the order they should appear), and optionally picks the display the meteorite is in.
4. The administrator saves.
5. The system checks that the session is still valid (`SEC-admin-authenticated`) and validates the form: required fields are present, the `monnigNumber` is not used by any other record (hidden ones included), and every field meets its rule in Associated Information.
6. The system saves the record and its photos together, sets `onDisplay` from the placement (on display if a display was picked), and sets the record's `lastEdited` and the database's `contentLastChanged` to now.
7. The system confirms that the meteorite was added and shows the meteorite list with the new meteorite in it.
8. Use case ends.

**Extensions:**

- **1a. The administrator selects an existing meteorite to edit.**
    - 1a1. The system loads the record and shows the form filled with its current values, photos, and display. It notes the record's `lastEdited` time. The `monnigNumber` is shown but cannot be changed.
    - 1a2. The administrator changes any of the other fields, adds, removes, or reorders photos, edits captions, or changes or clears the display.
    - 1a3. Flow rejoins at step 4.
- **1a1a. The record cannot be loaded (the database cannot be reached, or the record no longer exists).**
    - 1a1a1. The system shows a message saying the meteorite could not be opened, and stays on the meteorite list.
    - 1a1a2. Use case ends.
- **1b. The administrator chooses Hide for a meteorite.**
    - 1b1. The system asks the administrator to confirm. The prompt names the meteorite and says that visitors will no longer see it, that visitors who saved it as a favorite will see it as no longer available, and that it can be restored later.
    - 1b2. The administrator confirms.
    - 1b3. The system checks the session (as in step 5), marks the record hidden, and sets the record's `lastEdited` and the database's `contentLastChanged` to now. The record and its photos are kept.
    - 1b4. The system confirms that the meteorite is hidden. In the meteorite list it is marked hidden and has a Restore control.
    - 1b5. Use case ends.
- **1b2a. The administrator cancels.**
    - 1b2a1. Nothing changes. Use case ends.
- **1c. The administrator chooses Restore for a hidden meteorite.**
    - 1c1. The system checks the session (as in step 5), clears the hidden mark, and sets the record's `lastEdited` and the database's `contentLastChanged` to now.
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
- **5c. (Editing) The record has changed since the administrator opened it: its `lastEdited` no longer matches the time noted at 1a1.**
    - 5c1. The system does not save. It says another administrator changed this meteorite, and when. The administrator's entries stay on the form so they can be copied.
    - 5c2. The administrator chooses to reload, and the system discards the unsaved entries. Flow rejoins at 1a1 with the latest version. Nothing is overwritten without the administrator first seeing the other change.
- **5d. The session has expired or is no longer valid.**
    - 5d1. The system does not save, and refuses the change (`SEC-admin-authenticated`). It says the administrator must sign in again (`UC-ADM-log-in`).
    - 5d2. After the administrator signs in again, the system returns them to the form with their entries, and flow rejoins at step 4.
- **6a. The content database cannot be reached, or the save fails partway (for example, a photo fails to store).**
    - 6a1. The system saves nothing: the record and its photos are saved together or not at all. It says the change could not be saved and offers to try again. Everything entered stays on the form.
    - 6a2. If the administrator tries again, flow rejoins at step 5.
- **\*a. The administrator cancels, or leaves the form with unsaved changes.**
    - \*a1. The system asks whether to discard the unsaved changes.
    - \*a2. If the administrator discards them, nothing is saved, the system shows the meteorite list, and the use case ends. Otherwise flow continues where it was.

**Priority:** High. It is the most-proposed use case in the tally (4 votes, minutes 2026-11-09). Whether release 1.0 includes the admin portal is still `OI-11`.

**Frequency of Use:** Rare. Exhibits are mostly permanent (`BR-permanent-exhibit`), and there are two administrators. Changes come mostly when a new meteorite is acquired (such as a new Texas find); the client has not given a rate (interview, §7). Concurrent edits are unlikely but possible (5c). Each live change makes every visitor's app reload content on its next check for changes (`MNT-content-update`).

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
| `lastEdited` | timestamp, per record | Set by the system on every save, hide, or restore of this record. Used to detect two administrators editing the same record (5c). | Set by the system. Not shown to visitors. | — |
| `contentLastChanged` | timestamp, one for the whole content database | Set by the system on every save, hide, or restore of any record. The visitor app checks only this value to decide whether to reload content, so it never checks records one by one (author's decision, 2026-11-15). | Set by the system. Readable by the visitor app. | — |

- **Going live.** A saved change is live right away, with no draft or approval step (author's decision, 2026-11-15). The visitor app finds out by checking the single `contentLastChanged` value and reloading only if it is newer than the copy it has (minutes, 2026-11-06). When it checks (on launch, or more often) and whether it reloads everything or only the records whose `lastEdited` is newer are left to the design.
- **What visitors see of a hidden meteorite.** It does not appear in any list (browse, search, filter, favorites, exhibits, similar meteorites). If a visitor opens it from a favorite or from a list loaded before it was hidden, `UC-DAT-view-meteorite` 3b shows that it is no longer available.
- **Security.** Every save, hide, and restore is checked against the session on the server, not only in the browser (`SEC-admin-authenticated`). Every portal account is an administrator account, so a valid session is all the check needs; there are no roles or permission levels to check (author's decision, 2026-11-15). All traffic uses HTTPS (minutes, 2026-11-09).
- **Systemic failure.** Every change is all or nothing (6a). A record is never left saved without its photos, or with only some of its changes.
- **Not in this use case:** adding or renaming rooms and displays; 3D models (`OI-27`); visitor information such as hours (`UC-TOUR-view-visitor-info`); creating administrator accounts; loading the full collection at the start (`OI-4`).
- **SRS changes needed.** SRS §7.2 needs the `hidden`, `lastEdited`, and `display` fields and the database-wide `contentLastChanged` value, and needs to show that `onDisplay` is derived from `display`. SRS §2 says it is open whether a back end exists at all (`OI-4`). This use case assumes one does.

**Related Use Cases:**

- `UC-ADM-log-in` _(in review, #46)_: Log In as an Administrator. Signs the administrator in (PRE-1) and signs them back in at 5d.
- `UC-DAT-view-meteorite` _(in review)_: View a Meteorite. Shows what this use case saves. Its 3b covers a meteorite that has been hidden.
- `UC-DAT-browse-database` _(in review)_: Browse the Meteorite Database. Lists only meteorites that are not hidden.
- `UC-DAT-filter-database`: Organize Meteorite Catalog Based on Filters. Its on-display filter uses the `onDisplay` this use case sets.
- `UC-DAT-save-favorite` _(in review)_: Save a Favorite Meteorite. Stores the `monnigNumber`, which is why it is locked here.
- `UC-TOUR-view-exhibit` _(in review)_ and `UC-TOUR-browse-gallery-section` _(in review)_: Show the meteorites placed in a display or room here.

**Assumptions:**

- The portal writes to the app's own content database, not to the gallery's catalog at monnigcatalog.tcu.edu. The catalog is never changed (`DI-catalog-source-of-truth`). Whether the content database starts as a copy of the catalog is `OI-4`.
- The portal is a browser-based tool, separate from the visitor app (minutes, 2026-11-09). Its layout is left to the design.
- The administrators are Dr. Mayne and Heather Stepp (minutes, 2026-11-09). Only administrators have portal accounts, and every account can do everything in this use case. Neither needs the other's approval.
- One record per `monnigNumber`, as in `UC-DAT-view-meteorite`. If the catalog separates a meteorite from its samples, this changes (`OI-4`).
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

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
