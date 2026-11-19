# Meeting Minutes: Monnig Gallery App Team Meeting (Use Case Review Session)

**Date:** Monday, November 16, 2026, ~8:00 AM CT (about 78 min)
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Bradley Helmholz, Edwin Rodriguez, Turner DeMott (arrived partway), Tanner Temple (remote), Koen Dolezar (remote)

> The transcript has Cody saying "the whole gang is here" once Turner arrived. Please confirm whether Koen attended.

---

## Summary

A working session to finish reviewing use cases in pairs. The team decided to let Claude collect and renumber all open issues during the final merge, settled several use case scope questions, and discussed where the meteorite data and pictures will come from. Goal: get all use cases marked ready (green) tonight so Cody can merge them.

## Discussion

### Open issues
- Nobody had pushed open issues to the open issues branch (the branch Cody set up last week). Open issue numbers conflict between branches (for example, more than one branch uses #39).
- **Decision:** Because the team has fallen behind, skip pushing open issues to that branch. Open issues are already listed in each use case, so Claude will collect them at the end during the merge and renumber to avoid duplicates. For any new open issue going forward, ask the agent to commit it to the open issues branch if convenient.

### Merging the use cases
- Once most use cases are green, Claude will combine everything into one document with **no wording changes**. Most conflicts are in the list at the top of each document and the open issue numbering, not in the content.
- After the merge, Claude compares the SRS and the use cases. **The use case document is the source of truth**; the SRS is updated to match.

### Review mechanics
- Reviewers make changes directly, keeping them in a single commit so the partner can see them in the **Commits** tab (the Files changed tab doesn't show them clearly).
- Notify your partner by **@mentioning them in a comment** on the PR; it appears in their GitHub inbox. The reviewer/assignee options don't always work (for example, a person who opened the branch can't be its reviewer).
- Mark a PR **ready for review** (green) only when it is fully done.
- Reminder: agents over-build. Ask them to think about what is in scope. Example: Control playback was suggesting both pause and stop, but pause and resume is enough since the longest audio is about 60 seconds.

### Use case decisions
- **Text-to-speech "read description" (#28):** It no longer reads the meteorite's name. Reading the name becomes its **own use case** (like the speaker icons next to a word and its definition in Google). The feature isn't removed. Tanner's commit also edited the SRS; Cody left that, since the SRS will be reconciled later.
- **View meteorite (#29):** Remove extension 5B (open photo full screen with pinch zoom) from version 1. Just show the picture; zooming uses the platform default (Flutter).
- **First launch survey (#20):** The primary actor is no longer "visitor" or "remote visitor" (the glossary treats these as separate). The tablet case stays as an open issue (secondary actor). English is preselected at step 2. Two other use cases are cited.
- **Browse database:** One wording change, the old use case was removed from the branch, tags updated to "in review", and a description added to 3a.
- Wording was aligned between Control playback and Listen to content.
- **Admin login:** Administrators log in through a **separate online portal**, not the app. The use case for adding or editing content is simple: the admin is logged in, chooses add/edit, enters the fields, and it is saved to the database.

### Data source (open)
- The existing Monnig catalog database lacks the **pictures and item descriptions** the app needs. The old app's data (wall descriptions, pictures, locations) lives in the old app, built by Asa, and the data on the gallery tablet is locked down so Cody can't copy the app off it.
- The plan is still to put this data in its own database rather than bundling it in the app, so content changes don't require republishing to both app stores. Cody is trying to get the data from Asa and the old app.
- For the **MVP**, a couple of meteorites on screen are enough to show it working. Setting up the full data set comes second.

### Course note
- Dr. Wei sent an email about working up to a "0.2" checkpoint. It's unclear what that means (possibly after the earlier "0.1" slices). The team will clarify.

## Decisions
1. Claude will gather and renumber open issues during the merge, so nobody has to push them to the open issues branch.
2. The use case document is the source of truth over the SRS.
3. Reading the meteorite name is a separate text-to-speech use case.
4. Pinch zoom on photos is out of version 1.
5. Admins use a separate web portal.
6. The MVP needs only a few meteorites; the full data set comes later.

## Action Items

| Owner | Action | Due |
|---|---|---|
| All pairs | Finish reviews and mark all use cases ready (green) | Tonight |
| Tanner | Review the remaining use cases from Cody; remove extension 5B from view meteorite (#29) | Tonight |
| Cody | Merge the use cases into one document with Claude once green | After use cases are green |
| Cody | Keep trying to get the data and pictures from Asa and the old app | Ongoing |
| Team | Clarify the "0.2" checkpoint from Dr. Wei's email | Soon |

## Next Meeting
**Wednesday, November 18, 2026.** Go through all open issues together, list who to ask about the unanswered ones, and start the design discussion. Plan to start building on Friday, November 20.