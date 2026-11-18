# Meeting Minutes: Monnig Gallery App Team Meeting (Use Case Status and Merge Plan)

**Date:** Friday, November 13, 2026, ~8:00 AM CT (about 67 min)
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Bradley Helmholz, Edwin Rodriguez, Tanner Temple (remote), Turner Demott was expected to be late (unconfirmed whether he joined)
**Not mentioned:** Koen Dolezar


---

## Summary

Most use cases are written and in review. The team agreed on how to track them (draft vs. ready pull requests) and decided to **combine all use case branches into one "major branch" using Claude** instead of resolving conflicts by hand. Cody walked through the "Save favorite" use case as a review example. The plan is to merge on Monday, then move to design and start implementation, with an MVP targeted for December.

## Discussion

### Use case status
- Cody has two branches left to push. Tanner has finished all of his. Edwin has finished all of his but needs to open draft PRs. Bradley's two PRs were regular and will be switched to draft until finished.
- Cody reviewed Tanner's "Retake setup survey" and Tanner is reviewing Cody's work. Cody reviewed Edwin's use cases and expects about three open issues from them.

### Pull request tracking (agreed)
- Put every use case branch into a **draft pull request** and tag your partner as reviewer. Claude can open the draft PRs for you.
- When you and your partner agree a use case is done, mark it **ready for review**. A green PR means done.
- Open issues go to the **open issues branch**. Any open issues found while working on a use case should be pushed there, not only to the use case branch.

### Combining the use cases (agreed)
- Keep each use case in its own PR rather than resolving about 26 branch conflicts by hand ("don't do it by hand").
- Once everything is green, have Claude merge them into **one major branch**, resolving conflicts, fixing misspelled references and tying up open issues.
- **Monday's meeting:** build the major branch, then everyone skims their own use cases to check them. When all agree, merge it, delete the other PRs and branches, clean up the repo, and go through the open issues together (close what can be closed, and find out what needs research or who to contact).

### Tips for writing and reviewing use cases
- Claude tends to generate many extensions. Keep the app's small scope in mind and trim extensions that aren't needed, without cutting anything important.
- Example: in "Listen to content", tracking a separate "stop" state was dropped because pause already covers it (leaving the use case stops playback anyway).

### Remaining documents and next phases
- **Traceability:** Fill in once all use cases are combined; Claude can do it.
- **Glossary:** Scan the combined use cases for missing terms.
- **Business rules:** Mostly done; scan for gaps. **Client interview:** done.
- **SRS:** Needs small tweaks to match the use cases. After the merge, have Claude find where the SRS and use cases differ, then decide as a group which is the source of truth.
- **Old documents:** Can be deleted after the work is finished (kept until then).
- **Architecture design:** Most details are worked out. Fill in the basics now and finish it as open issues close.
- **Design records:** These are written **per area, not per use case**. Hold off running the design step until the use cases are merged (Monday).
- Then run the app and the implementation step.

### Timeline
- **Monday (Nov 16):** Merge into the major branch, review, clean up, review open issues.
- **By Wednesday (Nov 18):** Architecture and design records done or close.
- **Friday (Nov 20):** Possibly start implementation; some work possible over Thanksgiving break.
- **December:** An MVP ("however janky") to show Heather and Dr. Mayne.
- **January:** Return to the client with the MVP and ask about funding. Interactivity features follow next semester.

### Example review: Save favorite (Cody)
- A toggle (such as a star) in the meteorite view is the only place to save or remove a favorite. Favorites are stored on the device as a list of Monnig numbers (the meteorite ID), with details fetched from the database. No account is needed.
- Favorites survive a preferences reset. They are cleared only by a "new visitor" full reset or by uninstalling the app.
- Saving and removing work offline, but loading the details needs a network connection.
- Low priority; occasional use. Shared favorites and leaderboards need a backend and come later.
- **Review changes agreed:**
  1. Remove the "setup survey completed" precondition. The only precondition is that the visitor is viewing a meteorite.
  2. Confirm saving visually (the star changes) instead of with a text message.
  3. Accessibility: the control must not rely on color alone and needs a screen reader label. Possible open issue: should it also show text such as "Add to favorites" / "Favorited"?
- Design note: checking the favorites list each time a meteorite is viewed could be slow; a hash map may be the fix.
- Tanner approved with these changes. Cody will make them and mark it done.

## Decisions
1. Use draft PRs for work in progress and ready-for-review (green) for finished use cases.
2. Combine all use cases into one major branch using Claude, not by hand.
3. Design records are written by area, after the use cases are merged.
4. Trim use case extensions that fall outside the app's scope.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Cody | Push the last two use case branches; make the review changes to Save favorite | Today |
| Edwin | Open draft PRs for all use case branches | Soon |
| Bradley | Convert the two regular PRs to draft until finished | Soon |
| All pairs | Finish reviewing use cases; push any open issues to the open issues branch | Before Monday |
| All | Attend Monday in person if possible | Monday |
| Cody | Post the meeting minutes and a Slack recap of tips and the GitHub structure | Soon |

## Next Meeting
**Monday, November 16, 2026.** Build and review the major branch, then go through open issues.