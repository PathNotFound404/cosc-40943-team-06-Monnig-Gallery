# Meeting Minutes: Monnig Gallery App Team Meeting

**Date:** Friday, November 6, 2026
**Facilitator:** Cody Pinkston
**Attendees:** Cody Pinkston, Bradley Helmholz, Edwin Rodriguez, Turner
**Presenters:** Turner (business rules), Bradley (use cases)

---

## Summary

The team reviewed Turner's business rules and Bradley's revised use cases, discussed how the app should store and update meteorite data, and set up the Flutter development environment together. The use case brainstorming document was not filled out, so it moves to Monday.

## Discussion

### 1. Business rules (Turner)

| Rule | Notes |
|---|---|
| **Group size** | The gallery can handle 30 visitors, but prefers two groups of 15. They don't want more than 15 per group where they can control it. |
| **Guided tour windows** | 9 AM to 12 PM, reserved for designated tours. The gallery is closed to everyone else during those hours. |
| **No gallery photography** | One of the few hard rules. |
| **Branding / affiliation** | Two related rules: (1) **No TCU affiliation.** The app is presented as a Monnig product, not a TCU product (more of an App Store listing concern). (2) **Monnig branding.** The app uses the Monnig logo and color scheme only, not TCU branding (the in-app visual language). The two could be combined. It is not confirmed that TCU branding is strictly prohibited; the team leans toward starting without it, since TCU affiliation is easier to add later than to remove. |
| **Content administration** | Only an admin can add rocks or other content to the database or app (not the team's decision). |
| **Permanent exhibit** | What is on display rarely changes. |
| **Funding and grants** | The gallery pays for the project, including all costs. |
| **Grant timeline** | The draft said December 26 or 27 (unconfirmed). The team believes it means **December 2027**. The first grant runs well past the end of this project and the four-year grant runs longer. Unlikely to affect the project but worth documenting. |
| **Visitor survey data** | Gallery grants and sponsors require visitor surveys (e.g., age range), and the results go back to funders. |
| **Final sign-off** | Dr. Mayne approves essentially everything. |
| **Accessibility standard** | No specific standard identified yet, but the app should meet some standard so it is accessible to all visitors. |

**Database access rule removed:** An earlier draft said access to the meteorite database "is kept in the vault" and is Dr. Mayne's decision. The vault holds the **physical meteorite collection**, which only Dr. Mayne can access, not the database. The rule was dropped and the interview guide updated. The database the team was sent has very little information on each meteorite, and it's unclear whether it is the one the team will be given access to.

**Booking process:** It appears as out of scope in Vision & Scope. **Decision:** In the MVP, planning a visit is a **link to the gallery's contact page** (email or contact form). A built-in booking flow can be added later if time allows.

### 2. Use cases (Bradley)

The legacy use cases were shortened to: two preferences, one text-to-speech, and three meteorite catalog/database use cases. The tour use cases were removed so the team can design its own.

- **Language preference:** The first screen on first launch, where the user selects a language (e.g., by flag icon). Bradley cut the legacy list down to **English and Spanish**, given the Texas audience. More languages can be added later.
- **Visual preferences:** A general setting available at any time for font size, font style and language. **Decision:** It will not be its own floating UI element. Preferences are reached through one general **Settings** tab, so a Settings use case needs to be added and linked to preferences.
- **Light/dark mode:** Dark mode was suggested as the default. The group settled on letting users switch between light and dark.
- **Text-to-speech:** Currently empty. Start with reading a meteorite's description aloud, treating TTS as one universal feature rather than many separate use cases. What else needs TTS depends on the ADA standard chosen, and it may land in a later version (1.1 or 1.2), after the base app works. This ties to the traceability document.
- **Database use cases:** Reached from a home-screen tab ("show me the catalog/database"). They show a scrollable list of meteorite cards. "Catalog" and "database" are used interchangeably, and the glossary should reflect that.
  - Many details are guesses until the team sees what the real data looks like.
  - Feedback: <u>use cases should focus on system behavior, not design decisions (such as card layout), since every use case gets a design document.</u>
  - Filter idea: by type, location found, and a time-range slider.
- **Other suggestions:** Hold a wireframe session to sketch screens and button placement. Review other museum and gallery tour apps for ideas (a list already exists).
- The use case branch was merged.

### 3. Data storage and updates (open question)
- Open question: store a local copy of the meteorite data, or query the Monnig database directly? To be added to Open Issues; it depends on access to the database and its form.
- Cody's leaning (not a decision): keep the app light.
  - Keep the data in a database that admins edit, ideally through a simple web portal, so Dr. Mayne can add meteorites without rebuilding the app and pushing an app store update.
  - Cache text data on the device; always query (or cache) images rather than bundling them.
  - To avoid querying every time, the database would store a "last edited" flag. On launch, the app makes a small request to check whether anything changed and re-queries only if so.

### 4. Use case brainstorming document
- No one had filled it out, so this moves to **Monday's meeting**.
- Purpose: each person lists the use cases they think the app needs, without looking at others' lists. Overlap shows the most important use cases, and ideas only one person had may be niche but still valuable.
- Everyone agreed to complete it by Monday.

### 5. Flutter environment setup
The team installed and tested Flutter together:
1. Prerequisites: Git and VS Code. Turner follows the macOS instructions.
2. Install the Flutter extension in VS Code and download the SDK into a dedicated folder (the instructor's suggestion was a `develop/flutter` folder).
3. Run `flutter doctor` to confirm setup. Several people had to add Flutter to their PATH. Warnings that aren't errors can be ignored.
4. Install Android Studio, then use the Virtual Device Manager to create a "resizable (experimental)" emulator. This downloads about 2 GB. The hypervisor must be enabled, which may require a restart.
5. Create a test Flutter application in a separate folder (it can be deleted afterward) and run it on the emulator from VS Code.
6. Use hot reload and hot restart to see changes quickly. The first build is slow, especially on Windows.
- Known issues: the Android emulator can have trouble on high-resolution displays, and one teammate had trouble resizing the emulator window.
- iOS testing (simulator or a physical device) is not yet set up. It will depend on the team members with Macs, or a remote Mac. Cody will look into it.

## Decisions
1. Keep the business rules as presented, with the grant date corrected to December 2027.
2. Remove the "meteorite database in the vault" rule; keep "only admins can add content".
3. Booking is out of the MVP; link to the contact page instead.
4. Preferences are reached through a general Settings tab, not a floating control.
5. Start with English and Spanish.
6. Use cases will describe system behavior, with design details left for the design documents.
7. The use case brainstorming document is due Monday.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Edwin | Complete the SRS | Monday |
| Everyone | Fill out the use case brainstorming document | Monday |
| Turner | Correct the grant timeline to December 2027 and finalize the business rules | Soon |
| Bradley | Revise the use cases to focus on system behavior and add a Settings use case linked to preferences | Soon |
| Cody | Add the data storage question to Open Issues | Soon |
| Cody | Add the catalog/database terminology note to the glossary | Soon |
| Cody | Look into iOS testing for Flutter | Over the weekend, if time allows |
| Team | Ask the client for the visitor survey and its questions | Next client contact |
| Team | Confirm whether "no TCU affiliation" and Monnig-only branding are firm | Next client contact |

## Open Issues
- Does the app store a local copy of the data or query the Monnig database?
- Is TCU affiliation or branding strictly prohibited?
- Which accessibility standard applies, and what does it require for text-to-speech?
- Will the team get access to a fuller meteorite database?
- How will the team test on iOS?

## Next Meeting
**Monday, November 9, 2026.**