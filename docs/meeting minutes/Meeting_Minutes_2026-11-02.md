# Meeting Minutes: Monnig Gallery App Team Meeting

**Date:** Monday, November 2, 2026, ~8:00 AM CT (about 39 min)
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Edwin Rodriguez, Bradley Helmholz, Turner DeMott, Koen Dolezar
**Absent / not confirmed:** Tanner Temple

---

## Summary

The client interview is complete, and Vision & Scope is finished. The team reviewed the remaining documents, assigned business rules and the software requirements specification, and agreed on which legacy use cases to keep, change or remove. Everyone will bring use case ideas to Wednesday's meeting.

## Discussion

### Other project (USPTO), brief status
- Cody finished the "create visualizations" use case, which is in a pull request. Two use cases remain: **verify source** (Cody) and **export visuals** (saved for Tanner).
- Once those are done, the plan is to build a signed Mac app with GitHub Actions and send it to Malachi.

### Documents status
- **Client interview guide:** The interview happened. Cody will fill in the guide from the team's notes. Turner will send his paper notes, and Cody will combine them with his own.
- **Vision & Scope:** Done. Review it as needed.
- **Glossary:** No additions needed now. Add terms as they come up (and add "DB" if used as shorthand).
- **Open issues:** Cody will close the two issues that have been answered. Everyone adds new questions as they come up.
- **Remaining:** Business rules, software requirements specification (SRS), use cases.
- **Next steps after use cases:** Architecture and design record, then implementation.

### Business rules (owner: Turner)
- The client interview produced few constraints, and the old documentation had no business rules.
- Rules and constraints identified so far:
  - **No TCU affiliation** (the only constraint given in the interview; unconfirmed meaning, see questions).
  - **Only admins can add content** (the app is otherwise read-only for visitors).
  - **Group size** for guided tours: about 30 is the maximum, 15-20 is more comfortable. This could affect how interactive features work.
  - The accessibility standard to be met, once identified.
- Survey data and final sign-off were noted as useful to document. The guided tour time window is only a suggestion and doesn't need to be included.
- Cody created a shared Google Doc for collecting these before they are pushed to the repo.

### Use cases
- Process: each member brings general use case ideas on their own; the team compares lists (overlap shows the core use cases), writes down names and descriptions, then splits the writing.
- The legacy use cases will each be reworked, renamed or re-verified. Currently there are about eight legacy use cases to keep and customize.
- **Keep (revise):**
  - User preferences, language preferences and visual preferences (revisit once an ADA standard is chosen).
  - Text-to-speech.
  - Meteorite and category use cases: display a single meteorite, organize and filter the full collection, display meteorites in the list.
- **Remove:**
  - Text-to-speech by location (no location tracking this time).
  - Scan display code (QR). It can be added back later if wanted.
  - Tour and location use cases built around Bluetooth detection and selecting your location. The team will make its own decisions on navigation.
- **Rename:** "Catalog" becomes **"Database"** (spelled out).
- **Preferences design:** Previously the survey ran on every launch, which suits a shared gallery tablet but is annoying on a personal device. New approach: survey on first launch, saved as preferences, retakeable from Settings. For gallery tablets, a "new person" button resets the app and restarts the survey.
- Interactivity use cases should also be titled and documented even if they land in later versions, since the traceability document asks for version 1.0, 1.1, 1.2 and so on (Wei's request).
- No objections to the use case plan.

### Software requirements specification (owner: Edwin)
- Not much can be completed before business rules and use cases are done. Edwin will draft what he can, leave blanks, and fill in the rest later. He'll ask for help if needed.

## Decisions
1. Use cases will be settled by group brainstorming, then split among members.
2. Legacy use cases removed or kept as listed above; "catalog" renamed "database".
3. Preferences are set at first launch and changed in Settings, with a reset option for gallery tablets.
4. Turner owns business rules; Edwin owns the SRS.
5. Document owners will give a 5-10 minute summary to the group when their document is done.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Turner | Draft business rules (use the meeting notes and transcript) | Wed |
| Edwin | Work on SRS, filling in what is possible now | Wed |
| Cody | Update the client interview guide with team notes | Wed |
| Turner | Send paper notes from the client interview to Cody | ASAP |
| Cody | Edit legacy use cases: delete removed ones, rename items, format; close answered open issues | Wed |
| Bradley | Fill out a couple of the database-related use cases | Wed |
| Everyone | Bring general use case ideas, including interactivity use cases | Wed |
| Everyone | Add new questions to Open Issues | Ongoing |
| Cody | USPTO: build verify-source feature and merge the pull request | Soon |

## Questions / Open Issues
- Which accessibility standard applies, if any? (Will become a business rule.)
- What exactly does "no TCU affiliation" mean for the app? (The transcript is unclear.)

## Next Meeting
**Wednesday, November 4, 2026.** Agenda: document owners present business rules and SRS changes; brainstorm and split use cases. Use cases are targeted for completion by the end of this week or Monday.
