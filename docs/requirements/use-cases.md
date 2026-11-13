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
| PREF | User preferences | `UC-PREF-identify-language-preference`: Identifies User Language Preference<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display |
| DAT | Meteorite catalog | `UC-DAT-display-database`: Display Meteorites in Catalog<br>`UC-DAT-filter-database`: Organize Meteorite Catalog Based on Specific Filters<br>`UC-DAT-view-meteorite`: View a Meteorite |

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


### UC-DAT-view-meteorite: View a Meteorite

**UC ID and Name:** `UC-DAT-view-meteorite`: View a Meteorite

**Created By:** Cody Pinkston

**Date Created:** November 12, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The Monnig catalog, or the data source that replaces it (`SI-monnig-catalog`, `OI-4`)

**Trigger:** The visitor selects a meteorite in any list that shows meteorites: the Meteorite Database list, search or filter results, favorites, on-display items, an exhibit, or similar meteorites.

**Description:** The visitor opens one meteorite to see what the gallery knows about it: its name, its classification (class, group, composition), where and when it was found and whether its fall was observed, its description, and its pictures. If the gallery has a 3D scan of the meteorite, the 3D model takes the place of the main picture. The visitor can swipe through the photos and open any of them full screen to zoom in. From this view the visitor can also have the name and description read aloud, save the meteorite as a favorite, open similar meteorites, or turn the 3D model; each of those is its own use case. Whether the view is a full screen or a popup over the list is left to the design. This use case replaces `UC-DAT-display-meteorite`, which has been removed.

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
    - 5b1. The system opens the photo full screen. The visitor can pinch to zoom and pan, and swipe to the next or previous photo.
    - 5b2. The visitor closes the full-screen photo.
    - 5b3. The system returns to the meteorite view, with the gallery showing the photo the visitor was last on.
    - 5b4. Flow rejoins at step 5.
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
- **Photo gallery.** Swipeable, starting at the hero, with an indicator of which photo of how many is showing. Selecting a photo opens it full screen with pinch-zoom (5b).
- **Accessibility.** Every photo, the 3D model, and every control has a screen-reader label (`USE-screen-reader`); a photo with no caption is labeled with the meteorite's name and its position, such as "photo 2 of 4". Every field stays readable at every text size, in both languages (`USE-text-scaling`). Swiping has a non-gesture alternative, such as next and previous buttons, so it works with a screen reader.
- **Performance.** The details must be complete within `PER-detail-load` (threshold TBD, `OI-13`). The name and text fields should not wait for photos or the 3D model to load (4b, 4c).
- **Data source.** If the app keeps its own copy of the catalog (`OI-4`), steps 2 and 3 read from that copy, and 3a happens only when the copy cannot be read.
- **Systemic failure.** This use case only reads, so a failure leaves nothing partly changed.

**Related Use Cases:**

- `UC-DAT-browse-database` _(in review)_: Browse the Meteorite Database. Opens a meteorite here at its step 7.
- `UC-DAT-search-database` _(not yet written)_: Search database. Its results open a meteorite here.
- `UC-DAT-filter-database`: Organize Meteorite Catalog Based on Filters. Its results open a meteorite here.
- `UC-DAT-view-favorites` _(not yet written)_: View favorites. Opens a saved meteorite here.
- `UC-DAT-view-on-display-items` _(not yet written)_: View on-display items. Opens a meteorite here.
- `UC-TOUR-view-exhibit` _(not yet written)_: View exhibit. Opens a meteorite in the display here.
- `UC-DAT-view-similar-meteorites` _(not yet written)_: View similar meteorites. Reached from this view (5f), and opens a meteorite here.
- `UC-DAT-save-favorite` _(not yet written)_: Save favorite. Reached from this view (5e).
- `UC-DAT-view-3d-model` _(not yet written)_: View 3D model. Turning and zooming the hero 3D model (5c).
- `UC-TTS-listen-to-content` _(in review)_: Listen to Content. Reads the name and description aloud (5d).
- `UC-DAT-display-meteorite`: Replaced by this use case and removed.

**Assumptions:**

- One view per catalog record. If the catalog holds several samples of the same meteorite, each opens its own view (see `OI-4` on meteorite versus sample).
- Class, group, and the fall value are a fixed list, so they are shown in the selected language. Free-text values (composition, country, location found) are shown as the catalog stores them, untranslated.
- Opening a meteorite from a meteorite view (5f) stacks views: closing returns to the previous meteorite, not to the original list.
- If a 3D model cannot load, the first photo takes its place (4b). The visitor is not told a 3D model exists until it loads.
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-4`: Where the meteorite data comes from, which fields it has (composition values, date precision), and whether it distinguishes a meteorite from its samples.
- `OI-9`: Whether machine translation of descriptions is acceptable, and who reviews it.
- `OI-12`: Whether a meteorite's details must be readable offline. Today only data already loaded is promised (`ROB-offline`).
- `OI-13`: The load-time threshold for `PER-detail-load`.
- `OI-15`: Who owns the meteorite photos, and what credit they need.
- `OI-27`: Which meteorites have 3D scans, in what file format, who owns them, and where they will be hosted for the app?
- `OI-28`: Which meteorites will have a written description in release 1.0, and who writes and approves them? The catalog may not hold descriptions (SRS §7.4).


---

## Working these with your agent

_[Delegate: drafting the main success scenario once you have the trigger and the goal; proposing extensions you have not thought of, which it is genuinely good at; turning a filled-in use case into a first set of test cases; checking that every `BR-*` you cite exists in [business-rules.md](business-rules.md).]_

_Keep human: whether this is one use case or three, what the priority is, and whether an extension the agent proposed is a real path in your client's business or a generic one it has seen elsewhere. "The system handles concurrent edits" is a real requirement for some projects and invented complexity for others, and only you have met the client._

_The verification that catches the most: read the main success scenario aloud to someone who has not read the document, and stop wherever they ask a question. Every question is a missing step or a missing extension._

_**Checklist for each use case:** Does the name start with a verb? Can the system test every precondition? Does every step alternate actor and system? Is there at least one extension per step that can fail? Does every business rule appear as an identifier only? Could a tester write test cases from this without asking you anything?_
