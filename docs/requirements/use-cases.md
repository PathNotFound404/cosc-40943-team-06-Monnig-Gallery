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
| TTS | Text-to-speech | `UC-TTS-listen-to-content`: Listen to Content |
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

### UC-TTS-listen-to-content: Listen to Content

**UC ID and Name:** `UC-TTS-listen-to-content`: Listen to Content

**Created By:** Cody Pinkston

**Date Created:** November 12, 2026

**Primary Actor:** Visitor

**Secondary Actors:** The device's text-to-speech engine, or a paid speech service (`SI-device-speech`, `DE-device-tts`)

**Trigger:** On a screen that shows a meteorite, a gallery section, or an exhibit, the visitor selects Listen.

**Description:** A visitor who cannot or would rather not read the screen has the app read the content aloud. The app reads the item's name and then its description, in the selected language, from start to finish. Once reading starts, the visitor can pause, resume, replay, or skip by paragraph (`UC-TTS-control-playback`). There is no separate Stop control: Pause silences reading, and leaving the screen ends it (`FR-TTS-stop-on-leave`). Changing the reading speed and the voice language belong to other use cases.

**Preconditions:**

- PRE-1. The visitor is viewing a meteorite detail screen (`UC-DAT-display-meteorite`), a gallery section screen (`UC-TOUR-browse-gallery-section`), or an exhibit screen (`UC-TOUR-view-exhibit`), and its content has loaded.
- PRE-2. The content shown has a description. It is not missing or shown as "[NOT INDICATED]".
- PRE-3. Text-to-speech is not already reading or paused on this screen.

**Postconditions:**

- POST-1. Text-to-speech has read the item's name and description aloud in the selected language, and shows that reading has finished with Replay available. If the visitor paused it, it stays paused until they resume it or leave the screen. If the visitor left the screen, reading has ended.
- POST-2. Nothing is saved. The reading position is not kept after the visitor leaves the screen or the app closes.
- POST-3. No content has changed (`FR-CONTENT-visitor-read-only`).

**Main Success Scenario:**

1. The visitor selects Listen.
2. The system checks that the description is available in the selected language.
3. The system prepares the text to read: the item's name as the first paragraph, then the description split into paragraphs at its paragraph breaks.
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
    - 3a1. The system treats the whole description as one paragraph (`OI-21`). The name is still its own paragraph.
    - 3a2. Flow continues at step 4.
- **3b. The item has no name, or its name is shown as "[NOT INDICATED]".**
    - 3b1. The system leaves the name out and reads only the description paragraphs.
    - 3b2. Flow continues at step 4.
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
    - \*b1. `UC-TTS-control-playback` \*b–\*f handles it. Reading pauses or stops as that use case says, and never resumes by itself.
- **\*c. The device's volume is muted or turned all the way down.**
    - \*c1. No change. The system reads anyway and does not detect or change the device volume, as in `UC-TTS-control-playback` \*e.
- **\*d. The device's screen reader (VoiceOver, TalkBack) is on.**
    - \*d1. No change. Listen is a labeled control that the screen reader can activate (`USE-screen-reader`). The system does not silence the screen reader. What the accessibility standard requires when both speak is open (`OI-20`).

**Priority:** High

**Frequency of Use:** For visitors who use text-to-speech, once for most items they open, in the gallery or remotely, so many times per visit. A visit runs about 30 to 60 minutes. With the device's built-in speech engine it adds no network load. With a paid speech service (`DE-device-tts`), each Listen is at least one request to that service.

**Business Rules:** `BR-accessibility-standard`, `BR-monnig-funds-costs`

**Associated Information:**

_Data fields (held in memory on the device for the screen that is reading; never saved). They exist only from step 5 until the visitor leaves the screen; before Listen is selected there is no reading state at all. `UC-TTS-control-playback` uses the same fields:_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| `paragraphs` | ordered list of text | Required; at least one item. The item's name, if it has one (3b), followed by the description split at its paragraph breaks (3a). Built at step 3 from the text in the selected language only (2a). | Memory only | — |
| `playbackState` | enum | One of Reading, Paused, Finished. Reading at step 5; Finished at step 7. `UC-TTS-control-playback` sets Paused and Reading. | Memory only | — |
| `currentParagraph` | integer | Required; from 0 to the number of paragraphs minus 1. Set to 0 at step 5. | Memory only | — |

_Content read (read-only to visitors, from the screen's own use case):_

| Property name | Data type | Validation rule | Security or access concerns | Glossary reference |
|---|---|---|---|---|
| name (meteorite name, section name, or display name) | text, per language | Optional for reading (3b) | Read-only to visitors | Display |
| `description` | long text, per language | Required (PRE-2); must exist in the selected language (2a) | Read-only to visitors | — |

- **Where Listen appears.** One Listen control on each meteorite detail, gallery section, and exhibit screen, shown only when PRE-2 holds. While reading is active, paused, or finished, the playback controls take its place (`UC-TTS-control-playback`). Listen returns only when the visitor leaves the screen and comes back. Placement is left to the design.
- **Controls.** Listen has a label that the device's screen reader reads (`USE-screen-reader`), is labeled in the selected language (`FR-LANG-interface-text`), and stays usable at every text size (`USE-text-scaling`). Messages in 2a, 4a, and 5a are also in the selected language and can be read by the screen reader.
- **Language.** The voice is always the selected language. Text with no translation in the selected language is never read, even though the screen shows it in English (2a).
- **Speed.** Reading uses the voice speed in effect when step 5 starts (`UC-TTS-voice-speed`). This use case does not change it.
- **One reader at a time.** Only the screen the visitor is viewing can be reading, because leaving a screen stops reading (\*a).
- **Systemic failure.** This use case makes no durable change, so a failure leaves nothing to roll back (see 4a, 5a, \*b).

**Related Use Cases:**

- `UC-TTS-control-playback`: Control Text-to-Speech Playback. Pause, Resume, Replay, and Skip for the reading this use case starts (6a, 7a, \*b).
- `UC-DAT-display-meteorite`: Display Information Regarding a Single Meteorite. One of the screens Listen appears on.
- `UC-TOUR-browse-gallery-section`: Browse a Gallery Section. The gallery section screen, one of the screens Listen appears on.
- `UC-TOUR-view-exhibit` _(not yet written)_: View exhibit. The exhibit screen, one of the screens Listen appears on.
- `UC-TTS-voice-speed` _(not yet written)_: Changes the reading speed.
- `UC-TTS-play-in-selected-language` _(not yet written)_: Chooses the language of the voice.

**Assumptions:**

- This use case replaces the empty legacy entry `UC-TTS-read-display-contents`, which has been removed from the Use Case List.
- Only the item's name and description are read. Other fields on a meteorite detail screen (type, location found, date found) are not read; visitors who need them use the device's screen reader.
- There is no Stop control. Pause meets the requirement that the visitor can stop reading (`FR-TTS-read-description`); Replay starts over; leaving the screen discards the reading position (\*a).
- After reading finishes, Replay replaces Listen until the visitor leaves the screen, matching `UC-TTS-control-playback` 11a.
- Other text in the app (Home, Settings, lists, activities) is not read by this use case. What else must be readable depends on the accessibility standard (`OI-3`).
- The IDs of use cases not yet written are coined from their names, following `UC-<AREA>-<slug>`. Their authors may choose different ones.

**Open Issues:**

- `OI-3`: Which accessibility standard applies, and what else it requires to be readable.
- `OI-20`: What the accessibility standard requires when the screen reader and the app's text-to-speech both speak.
- `OI-21`: Does the text being read come with paragraph breaks?
- `OI-25`: Is the gallery section screen in release 1.0? If not, Listen appears only on the meteorite detail screen (and the exhibit screen, if that is in 1.0).
- `OI-26`: Do visitors' devices reliably have a Spanish voice installed, and if not, should the app tell them how to add one?



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
