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
| PREF | User preferences | `UC-PREF-identify-language-preference`: Identifies User Language Preference<br>`UC-PREF-measure-visual-preferences`: Measures Visual Preferences Through Survey<br>`UC-PREF-reset-user-preferences`: Reset User Preferences in Settings<br>`UC-PREF-customize-visual-preferences`: Customize Visual Preferences During Application Usage |
| TTS | Text-to-speech | `UC-TTS-read-display-contents`: Text-To-Speech Reads Contents of Each Display<br>`UC-TTS-speak-by-location`: Text-To-Speech Based on User’s Location In The Museum |
| TOUR | Gallery tour and navigation | `UC-TOUR-scan-display-code`: Scans a QR/Barcode to Pull Up a Page of Display<br>`UC-TOUR-display-gallery-section`: Display Information Regarding Sections of the Gallery<br>`UC-TOUR-illustrate-areas-of-importance`: Illustrate Areas of Importance In the Gallery |
| CAT | Meteorite catalog | `UC-CAT-display-meteorite`: Display Information Regarding a Single Meteorite<br>`UC-CAT-filter-catalog`: Organize Meteorite Catalog Based on Specific Filters<br>`UC-CAT-display-catalog-meteorites`: Display Meteorites in Catalog |

---

## 4. Use Cases

_[One `###` heading per use case, grouped under a `##` heading per area. Worked example below, taken from Project Pulse. Delete it and write your own.]_

## PREF: User preferences

### UC-PREF-identify-language-preference: Identifies User Language Preference

**UC ID and Name:** `UC-PREF-identify-language-preference`: Identifies User Language Preference
**Created By:** Kendric D’Spain
**Date Created:** October 16, 2021
**Primary Actor:** Monnig Gallery Visitor
**Secondary Actors:** Museum volunteers
**Trigger:** A user starts an app for the first time the user tours the Monnig Meteorite Gallery.
**Description:** The user starts up the TCU MMG mobile app for the first time and prompts the user for their preferred language. The user is able to select their preferred language out of the four currently supported, English, Spanish, French and Vietnamesse.

**Preconditions:**

**Postconditions:**

- POST-1. The user’s language preference is temporarily stored and the remaining session of the gallery should illustrate the displays in the preferred language.

**Main Success Scenario:**

1. The system requests the user to choose their preferred language.
2. The user inputs their preferred language.
3. The system applies the preference to the current session.

**Extensions:**

- **1a. The User does not provide a language preference and tries to proceed**
    - 1a1. The system defaults language to English.

**Priority:** High
**Frequency of Use:** Everytime the MMG application is opened, and the user is ready to tour the Gallery.
**Business Rules:**

**Associated Information:**

1. The user is able to change their preferred language anytime throughout the gallery as well.

**Related Use Cases:**
**Assumptions:** Assume that the user must complete the language Preference survey prior to starting his/her tour at TCU’s Monnig Meteorite Gallery.
**Open Issues:**

### UC-PREF-measure-visual-preferences: Measures Visual Preferences Through Survey

**UC ID and Name:** `UC-PREF-measure-visual-preferences`: Measures Visual Preferences Through Survey
**Created By:** Kendric D’Spain and Aparajita Biswas
**Date Created:** October 8, 2021
**Primary Actor:** Visually Impaired User
**Secondary Actors:** Museum volunteers
**Trigger:** A user starts an app for the first time to tour the Monnig Meteorite Gallery.
**Description:** A user starts up the TCU MMG mobile app for the first time and is prompted by a survey. The survey identifies the user’s preferences based on a multitude of different questions presented.

1. Virtual Assistance Preference
2. Font Size Preference
3. Font Style Preference
4. Color blind prompt/test

**Preconditions:**

**Postconditions:**

- POST-1. The user’s Visual Preferences are temporarily stored and the remaining session should reflect the user’s visual preferences to the current instance of the application running.

**Main Success Scenario:**

1. The system requests the user for enabling virtual assistance.
2. The user responds to the system declining the feature by User Interface.
3. The system requests the user to select his/her preferred font size.
4. The user responds to the system choosing his/her preferred font size.
5. The system requests the user to select his/her preferred font style
6. The user responds to the system choosing his/her preferred font style.
7. The system prompts the user for the color blind test.
8. The user responds by inputting values for the test.
9. The system then applies the changes from all preferences and the colorblind examination to the current session.

**Extensions:**

- **1a. The User does not provide a response for enabling virtual assistance.**
    - 1a. The system proceeds after 30 seconds of auto enabling the feature.
- **2a. The user responds by accepting the virtual assistance feature via UI.**
    - 2a. The system proceeds ignoring all remaining preferences fields and proceeds to 9 in Main Success Scenario.

**Priority:** High
**Frequency of Use:** Every time the MMG application is opened, and the user is ready to tour the Gallery.
**Business Rules:**

**Associated Information:**

2. The user is able to access the Visual Preference survey anytime throughout the Gallery.

**Related Use Cases:**
**Assumptions:** Assume that the user needs are listed and that the user selects all the options they need assistance with. Volunteers will help in case the user can not navigate this stage of the application.
**Open Issues:**

## TTS: Text-to-speech

### UC-TTS-read-display-contents: Text-to-speech Reads Contents of Each Display

**UC ID and Name:** `UC-TTS-read-display-contents`: Text-to-speech reads contents of each display
**Created By:** Kendric D’Spain
**Date Created:** October 8, 2021
**Primary Actor:** Visually Impaired User
**Secondary Actors:** Museum volunteers
**Trigger:** User approaches a specific display.
**Description:** Upon completion of the preference survey, the user navigates to a display and would like to use the integrated Text-To-Speech feature throughout the exhibit.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. The system confirms the user is at a specific display.
2. The system vocally presents the specified material to the user.
3. The system indicates to the user the display is over and to visit the next display.
4. The system polls the user’s location for the next display.

**Extensions:**

- **3a. User Wants to Revisit Same Display**
    - 3a1. The user indicates to the system verbally to continue at the same display.
- **3b. User Wants to Exit the Gallery**
    - 3b1. The user indicates to the system verbally to exit at the exhibit.

**Priority:** High
**Frequency of Use:** Approximately 10 times per individual touring the Gallery.
**Business Rules:**

**Associated Information:**

1. The user is able to take a break from the Gallery by simply not interacting with the voice assistant at the end of a given display.

**Related Use Cases:**
**Assumptions:** Assume that the user preference text-to-speak functionality is enabled.
**Open Issues:**

### UC-TTS-speak-by-location: Text-To-Speech based on User’s Location In The Museum

**UC ID and Name:** `UC-TTS-speak-by-location`: Text-To-Speech based on User’s Location In The Museum
**Created By:** Amanuel Taddesse
**Date Created:** October 8, 2021
**Primary Actor:** Visually Impaired User
**Secondary Actors:** Museum volunteers
**Trigger:** User approaches a specific display.
**Description:** Upon completion of the preference survey, the user approaches a display and system will know that the user is close to a specific display via bluetooth beacons

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. The system confirms the user is at a specific display.
2. The system plays Text-To-Speech of Meteorites in a humanly sequence.
3. The user is able to interrupt/pause the Text-To-Speech audio if needed

**Extensions:**

- **4a. User Wants to Replay the Text-To-Speech Audio**
    - 4a1. The user passes this command via a button or a voice command.
- **4b. User Wants to Choose the Meteorite they want to learn more about**
    - 4a1. Visually impaired user makes a choice via voice command to explore one of the meteorites available on the shelf they are close to

**Priority:** Medium
**Frequency of Use:** At least as many as the number of displays in the museum
**Business Rules:**

**Associated Information:**

**Related Use Cases:**
**Assumptions:** The system will be getting a good approximate location of the user using the Bluetooth beacons
**Open Issues:**

## TOUR: Gallery tour and navigation

### UC-TOUR-scan-display-code: Scan QR/Barcode to access a page on a specific display

**UC ID and Name:** `UC-TOUR-scan-display-code`: User should scan a QR/Barcode in App to access a page to see information regarding display.
**Created By:** Asa Tuten
**Date Created:** October 11, 2021
**Primary Actor:** Visually Impaired User
**Secondary Actors:** Gallery Visitors
**Trigger:** The user walks up to the display and uses a camera within the App to scan a QR/Barcode.
**Description:** When a user scans the QR/barcode, the app will pull up a page regarding the display that was scanned and follow along the path the gallery takes.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. The user presses a button to pull up the camera in the app
2. The app pulls up the QR/Barcode scanner
3. The user holds up the device’s camera to the QR/barcode
4. The app validates the QR/barcode
5. The app opens up the page associated with that QR/barcode

**Extensions:**

- 1a. The user’s device does not have a camera.
    - 1a1. The user manually enters the display number on the camera screen.

**Priority:** Medium
**Frequency of Use:** Number of visitors within the gallery
**Business Rules:**

**Associated Information:**

**Related Use Cases:**
**Assumptions:** The user has a camera and can operate their phone to access their camera on the app.
**Open Issues:**

### UC-TOUR-display-gallery-section: Display Information Regarding Sections of the Gallery

**UC ID and Name:** `UC-TOUR-display-gallery-section`: Display information regarding sections of the gallery
**Created By:** Asa Tuten
**Date Created:** November 3, 2021
**Primary Actor:** Monnig Visitor
**Secondary Actors:**
**Trigger:** Selection of the section of the gallery on the app or tour assistant reaches that part of the tour in the app.
**Description:** The app will populate the UI with the text of the specific section that is in the gallery on the wall. It will also have meteorites listed in the UI that are specific to the topic the section is covering.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. The user selects the start button for the tour of the gallery.
2. The system will call the backend to gather section data.
3. The backend returns information regarding the section selected.
4. The system populates the UI with information regarding the section selected.
5. The system displays the information of the section of the gallery.
6. The user will then choose to continue the tour.

**Extensions:**

- 1a. The user selects a specific section they want to be displayed on the app.
- 6a. The user decides to end the tour.
- 6b. The user selects a specific section they want to be displayed on the app.

**Priority:** High
**Frequency of Use:** Every tour of the gallery
**Business Rules:**

**Associated Information:**

The database will have this information populated in JSON format and will be called using REST API calls for the UI to then format the JSON text into usable data for the UI to display.

**Related Use Cases:**
**Assumptions:** The database has all text of the gallery and the flow of the app has been created.
**Open Issues:**

### UC-TOUR-illustrate-areas-of-importance: Illustrate areas of importance in the gallery

**UC ID and Name:** `UC-TOUR-illustrate-areas-of-importance`: Illustrate areas of importance in the gallery
**Created By:** Asa Tuten
**Date Created:** 5/4/2022
**Primary Actor:** Monnig Visitor
**Secondary Actors:**
**Trigger:** Reaching the tour assistance screen after initial user flow. Can also occur was a user enters a different region of the gallery.
**Description:** The app will populate the UI with an image of the gallery with a highlighted area based on where the user is currently in the gallery. It will also change depending on where the user stands based on bluetooth beacon signals.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. User enters the gallery and goes through the initial survey and lands on the Tour Assistance screen.
2. Tour assistance screen updates relevant information about the area the visitor is currently in based on bluetooth beacons.
3. As the visitor moves around the gallery, the map will update based on the user’s new location and position in the gallery.

**Extensions:**

- 2a. The user accesses the app outside the gallery and the image will not update.

**Priority:** Medium
**Frequency of Use:** Everytime the app is used.
**Business Rules:**

**Associated Information:**

Uses the iBeacon technology.

**Related Use Cases:**
**Assumptions:** Assumes user is using one of the provided tablets in the gallery.
**Open Issues:**

## CAT: Meteorite catalog

### UC-CAT-display-meteorite: Display Information Regarding a Single Meteorite

**UC ID and Name:** `UC-CAT-display-meteorite`: Display Information Regarding a Single Meteorite
**Created By:** Kendric D’Spain
**Date Created:** November 3, 2021
**Primary Actor:** Monnig Gallery Visitor
**Secondary Actors:**
**Trigger:** The user selects a meteorite he/she wants to view in detail.
**Description:** A user visiting the Gallery wants to be able to view a specific meteorite.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. The user selects a meteorite to view.
2. The system will call the backend to collect the meteorites data.
3. The system reflects the data to the user displaying the meteorites stored contents.

**Extensions:**

- 2a. The system cannot retrieve any data on the selected meteorite.
- 3a. The system cannot display the data on the selected meteorite.

**Priority:** High
**Frequency of Use:** Every time the gallery is toured.
**Business Rules:**

**Associated Information:**

**Related Use Cases:**
**Assumptions:** The meteorites are inputted into the database correctly in the appropriate format.
**Open Issues:**

### UC-CAT-filter-catalog: Organize Meteorite Catalog Based on Filters

**UC ID and Name:** `UC-CAT-filter-catalog`: Organize Meteorite Catalog Based on Filters
**Created By:** Asa Tuten
**Date Created:** 5/4/2022
**Primary Actor:** Monnig Visitor
**Secondary Actors:**
**Trigger:** User selects the Meteorite Catalog screen tab on the app once through the survey.
**Description:** The app is equipped with being able to query meteorites for visitors to look at, whether the meteorite is on display in the gallery or not. The user can also filter out meteorites based a variety of categories.

**Preconditions:**

**Postconditions:**

**Main Success Scenario:**

1. User accesses the Catalog screen by hitting the catalog screen button.
2. Meteorites pop up based on users location in the gallery.
3. User will click the search bar and type in letters based on what they want to query.
4. Meteorites will update based on user’s query

**Extensions:**

- 4a. Query can be based on selected filter, like country, size, weight, etc.

**Priority:** Low
**Frequency of Use:** Any time a user wants to view more meteorites.
**Business Rules:**

**Associated Information:**

**Related Use Cases:**
**Assumptions:** Assumes user has internet access.
**Open Issues:**

### UC-CAT-display-catalog-meteorites: Displays Meteorites in Catalog

**UC ID and Name:** `UC-CAT-display-catalog-meteorites`: Displays Meteorites in Catalog
**Created By:** Aparajita Biswas
**Date Created:** November 03, 2021
**Primary Actor:** Monnig Gallery Visitor
**Secondary Actors:** Museum visitors
**Trigger:** A user selects to view the meteorite from the catalog in the Monnig Meteorite Gallery.
**Description:** After the user selects the meteorite to view, it is displayed on the screen

**Preconditions:**

**Postconditions:**

- POST-1. The meteorite information is stored in the database.
- POST-2. The system displays the catalog

**Main Success Scenario:**

1. The system waits for the input from user
2. The user selects the meteorite from the catalog to view
3. The system displays the selected meteorite with the stored information

**Extensions:**

- **1a. The User does not select a meteorite from the catalog**
    - 1a1. The system requests user input before proceeding.

**Priority:** High
**Frequency of Use:** Everytime the MMG application is opened, and the user is ready to tour the Gallery.
**Business Rules:**

**Associated Information:**

3. The user is able to view the meteorite anytime throughout the gallery as well.

**Related Use Cases:**
**Assumptions:** Assume that the user must select the meteorite before being able to view it.
**Open Issues:**

---

## Working these with your agent

_[Delegate: drafting the main success scenario once you have the trigger and the goal; proposing extensions you have not thought of, which it is genuinely good at; turning a filled-in use case into a first set of test cases; checking that every `BR-*` you cite exists in [business-rules.md](business-rules.md).]_

_Keep human: whether this is one use case or three, what the priority is, and whether an extension the agent proposed is a real path in your client's business or a generic one it has seen elsewhere. "The system handles concurrent edits" is a real requirement for some projects and invented complexity for others, and only you have met the client._

_The verification that catches the most: read the main success scenario aloud to someone who has not read the document, and stop wherever they ask a question. Every question is a missing step or a missing extension._

_**Checklist for each use case:** Does the name start with a verb? Can the system test every precondition? Does every step alternate actor and system? Is there at least one extension per step that can fail? Does every business rule appear as an identifier only? Could a tester write test cases from this without asking you anything?_
