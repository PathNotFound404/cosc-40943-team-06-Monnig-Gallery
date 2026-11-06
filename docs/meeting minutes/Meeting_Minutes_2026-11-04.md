# Meeting Minutes: Monnig Gallery App Team Meeting (Use Case Planning)

**Date:** Wednesday, November 4, 2026, 1:30 PM CT
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Tanner Temple, Koen Dolezar, Bradley Helmholz
**Not in Attendance:** Edwin Rodriguez, Turner DeMott

---

## Summary

The team clarified how business objectives, features and use cases fit together, added a **Tour** business objective, and set up a shared use case document organized by area. Everyone will add their use case ideas by Friday. Open questions remain on where the meteorite data will come from.

## Discussion

### How use cases are structured
- Use cases come from **features**, which are defined in Vision & Scope. Features in turn tie to **business objectives**.
- Work can go both ways: if a use case doesn't fit an existing feature, a new feature can be added.
- Each use case should have a feature tag, and possibly one or more business objective tags. The **use case area** is a separate grouping used to organize use cases.
- For now, write only use case names and short descriptions. Linking references (objectives, rules, features) can wait, since time is short. AI can help cross-reference these later.

### Business objectives
- A business objective states the benefit the product will provide, not a rule. Business rules are separate.
- Current objectives: display the collection, accessibility, language options, interactive components, and release on the app stores.
- **Decision: add a "Tour" objective**, covering a gallery experience that provides explanations and works like an audio tour. Existing use case areas such as tour and scan display code fit under it.
- Interactive components stay as a single objective. The scavenger hunt, Texas map and quizzes are features under it.
- Cody updated Vision & Scope with the new objective in a pull request, which was merged.

### Data sources (open)
- It's still undecided whether the app stores its own copy of the meteorite list or queries the existing Monnig database. This depends on Asa.
- The Monnig database holds meteorite data, but the previous app has additional content (descriptions, pictures) that isn't in it. The old app's code is on GitHub, but it is hard to follow. Data can be pulled from there if needed, though getting it from Asa is preferred.
- The team may also create its own content, such as 3D scans of meteorites.
- Cody will contact Asa.

### Gallery navigation
- Keep the old app's **room-selection view**: show a map of the gallery divided into rooms, tap a room to see everything in it, then back out. It needs no Bluetooth or other external technology.
- The gallery already has a detailed floor plan, so the team won't redraw it. A Matterport scanner (equipment Cody may be able to borrow, availability unconfirmed) could produce an accurate 2D plan if one is needed. A full 3D model of the gallery is not needed.

### Ideas raised (mostly spring semester)
- **Audio tour:** Number the gallery sections; the user picks "I'm at #1" and plays narration. Heather could write the narration, with Dr. Mayne or outside researchers adding interviews, and Cody could record and edit the audio. Little coding is needed; the effort is in audio production. Physical handheld audio guides were tried previously and were hard to program.
- **Gamification:** Achievements or badges and a scavenger hunt leaderboard. These would need servers and APIs, so they belong in spring semester. A full reset should account for achievements.
- Tanner proposed new tour use cases: follow a self-guided tour, and jump to a display.

### Use case areas and decisions
- **Preferences:** About five use cases already exist (in Bradley's branch). Merge "reset user preferences" and "reset for new visitor" into one general reset use case (working name "Reset preferences/settings"). A separate "settings" tag may be added later if needed.
- **Text-to-speech:** Currently empty. Needs use cases added (e.g., speech speed).
- **Tour:** Becomes its own use case area.
- Areas in the new document:
  1. Preferences and accessibility
  2. Audio / text-to-speech
  3. Meteorite database
  4. Tour (gallery and exhibits)
  5. Interactive learning
  6. Admin / content administration (analytics, adding to databases and content)
- Anyone can add another area on a new page using the same format.
- Process: each of the six team members adds ideas under their own name in each area. Duplicates are welcome, since overlap shows the important use cases. Then the team merges them into agreed use cases and splits the writing.

### Repository status and practices
- Open pull requests: Cody's (merged), Bradley's use cases (to review Friday), Turner's business rules (needs one fix: a `.DS_Store` file was committed and must go into `.gitignore`; it also contained two edits to the client interview guide, which look fine).
- Reminders: never commit `.DS_Store`, `.env` or secrets files. Always pull main and merge main before pushing a new branch.

## Decisions
1. Add a **Tour** business objective and give tour its own use case area.
2. Combine the preference reset use cases into one general reset.
3. Keep the room-selection approach for gallery navigation (no location detection).
4. Use the shared use case document, organized by area, for brainstorming.
5. Audio tour, achievements and leaderboard are deferred to spring semester.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Everyone | Add use case ideas (name plus short description) under your name in each area of the shared document | Friday |
| Cody | Share the use case document link in Slack with a recap | Soon |
| Cody | Clean up the document's front page | Soon |
| Cody | Contact Asa about the old data and database | Soon |
| Turner | Remove `.DS_Store` from the business rules branch and add it to `.gitignore` | Before merge |
| Team | Review Bradley's use case pull request and Turner's business rules | Friday |

## Open Issues
- Does the app keep its own copy of the meteorite data or query the Monnig database? (Waiting on Asa.)
- Will "settings" need its own tag separate from "preferences"?

## Next Meeting
**Friday, November 6, 2026.** Cody wants everyone there in person (Tanner is unavailable). Agenda: go through the Flutter installation and setup, then review everyone's use case ideas and choose which to take forward. Flutter was mentioned only in passing; confirm it is the chosen framework.