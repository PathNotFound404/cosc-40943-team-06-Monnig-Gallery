# Meeting Minutes: Monnig Gallery App Team Meeting (Use Case Merge and Conflicts)

**Date:** Wednesday, November 18, 2026, ~1:30 PM CT (about 63 min), remote
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Tanner Temple, Turner DeMott, Bradley Helmholz
**Absent:** Koen Dolezar (out of town), Edwin Rodriguez (exeused)

---

## Summary

All use cases were merged into the main branch, and the open issues were consolidated. Claude found about 16 conflicts between use cases, which pairs will resolve before Friday. Friday's meeting will focus on open issues and conflicts so the team can move on to design.

## Discussion

### Use case merge
- Nearly all use cases were marked ready. Four were not (two from Koen and two from Bradley). Cody marked them green and merged them anyway. Once the database structure is known, Claude can go back through the use cases and add the official data structure.
- Claude combined everything into one branch ("merge all open use cases"). Cody reviewed his own use cases and asked everyone to check theirs in the branch (the document is about 2,700 lines).
- Tanner approved the PR and merged it into main.
- Claude produced a **use case conflicts page**: about **16 conflicts** across roughly 30 use cases. Cody is involved in most of them (Tanner counted 11), and Cody and Edwin share many. Turner has none because Edwin committed his shared use cases. If you conflict with Edwin, consult both Edwin and Turner.
- Example: "View favorite" conflicts with another use case. Only the Monnig number is stored for the favorites list.

### Open issues
- Claude ran the open issue consolidation once (only one person needs to run it, since open issues already exist in every branch; nobody had uncommitted ones). Do not all run it at the same time, or numbers will overlap.
- The result changed only a few numbers in the use case document (two conflicting numbers). Tanner reviewed and merged it.
- Everyone should review the open issues related to their own use cases (asking Claude for a summary is fine) and come prepared to discuss and close as many as possible.

### Gallery map
- Cody's idea for the MVP: three buttons (Room 1, Room 2, Room 3) that divide into sections. A full gallery map can follow.
- The map should not be hard, and the team can reuse it from the previous app. Cody plans to put the gallery tablet in debug mode over break to get it.
- The map stays in the use cases for now and remains open for discussion (Bradley's comment about the use case being the default was noted).
- Some outdated references remain in the use cases. They will be fixed later.

### Next phases
- **Use cases are the source of truth.** After they are final (Friday), update the SRS to match them where they conflict.
- The team must finish the MVP before starting interactivity use cases. If the MVP is done by the end of the semester, interactivity work can start over break.
- Cleanup: each person deletes their old branches and closes their old PRs. Tanner closed his. Cody bulk-closed Koen's and Edwin's (16 PRs).
- Cody is behind on posting minutes. A minutes branch covering the past three weeks will appear soon, and Cody will post a Slack recap.

### Schedule
- **Friday, November 20:** Cody plans to hold it. Tanner cannot attend (flying out at 7 AM for Thanksgiving). Cody will assume the meeting happens. Turner's and Bradley's availability was not confirmed. Friday should be more relaxed: go through open issues and conflicts.
- **Thanksgiving break:** Cody suggested informal optional sessions. He cannot commit until he gets his work schedule.

## Decisions
1. All use cases, including the four not marked green, are merged into main.
2. Open issues are consolidated into main (one person runs the consolidation).
3. Use cases are the source of truth; the SRS will be updated to match after Friday.
4. Old use case PRs and branches are closed or deleted.
5. The MVP comes before interactivity use cases.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Everyone | Review open issues for your own use cases and come prepared to discuss | Friday |
| Pairs involved | Resolve the use case conflicts with the person each conflicts with. Post in Slack when one is resolved, and push fixes to a PR and tell everyone | Friday |
| Cody | Send the conflicts list (HTML) in Slack, plus a recap of the meeting | Today |
| Cody | Post minutes from the past three weeks (minutes branch) and tell Edwin and Koen to review | Soon |
| Cody | Possibly open a Slack channel for conflict resolutions | Soon |
| Cody | Update the SRS to match the use cases | After Friday |
| Cody | Get the gallery map and data from the old app (tablet debug mode) | Over break |
| Team | Decide on optional informal meetings over Thanksgiving break | Soon |

## Next Meeting
**Friday, November 20, 2026, 8:00 AM.** Go through open issues and conflicts, then start moving on to design. Tanner will be absent.