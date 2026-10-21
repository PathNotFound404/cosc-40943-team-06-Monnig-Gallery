# Meeting Minutes: Monnig Meteorite Gallery Team Meeting

**Date:** Wednesday, October 21, 2026, ~1:36 PM CT (59 min), Teams
**Facilitator / Notes:** Cody Pinkston
**Attendees:** Cody Pinkston, Tanner Temple (in room with Cody; chat only), Edwin Rodriguez, Koen Dolezar, Bradley Helmholz
**Absent:** Turner (sick)

---

## Summary

The project is being reframed from an app for visually impaired users to a general museum tour app with built-in accessibility (ADA) features. The team agreed to rewrite Vision & Scope, set a new meeting schedule, and signed the updated team contract. The client replied during the meeting that she isn't available until November.

## Discussion

**Project direction**
- Users with visual impairments already have their own assistive tools, and ADA features are easy to add through settings. The app should serve any visitor, since the gallery has no good digital presence (the current website is hard to use).
- ADA and kid-friendly interactivity were the client's two biggest priorities. ADA is kept; the weighting will be confirmed with the client.
- Published ADA standards can be given to AI tools to find gaps and generate compliant color schemes.

**Documents**
- **Vision & Scope:** Rewrite and reword the problem statement; reuse what's useful (e.g., flowcharts). Cody owns it.
- **Glossary:** Keep; it has useful meteorite terms.
- **Business rules:** Few exist so far (e.g., the exhibit is permanent; the app is mostly read-only). They depend on client answers.
- **Use cases:** Wait until Vision & Scope is done. Everyone brings their own list of use case names, then one meeting is used to agree on the master list, then they are split up and written.
  - Drop the Bluetooth indoor-location use cases.
  - Move language, text size and light/dark mode from launch-time prompts into a Settings/Accessibility tab (set once, change later).
  - Language change is a setting, not its own use case.
- **Tech stack:** Cannot be decided until the client says what to build in.

**Feature ideas** (interactivity is second priority, after the base app works; a formal brainstorming session will follow once client details are in)
- Videos, interactive elements and games from the gallery.
- Quizzes and a scavenger hunt based on physical items in the gallery.
- Interactive map of where meteorites were found (the physical Texas map has to be replaced with each new find), possibly a zoomable heat map.
- Tap a gallery section for a details screen.
- Search and filter the full collection (~3,000 meteorites), not just those on display.

**Client outreach**
- Cody emailed Heather and Asa (CC: team and Dr. Mayne), asking to meet and for data from the previous app.
- Heather replied that she is free only Mon Nov 2 or Wed Nov 4. Cody asked about earlier times and offered Mon/Fri 8 AM.
- Cody will write a client interview guide.

## Decisions

1. Rewrite Vision & Scope and reframe as a museum tour app with ADA features.
2. Defer use case writing until the team agrees on a master list.
3. User preferences move to a settings tab.
4. New meeting schedule:
   - **Mon 8 AM:** in person, library.
   - **Wed 1:30 PM.**
   - **Fri 8 AM:** one- to two-week trial, replacing Fri 1:30 PM.
   - **Thu 7 PM:** backup only. Whether it happens is decided at the end of Wednesday's meeting.
5. Team contract updated for the new schedule and signed by all members (via GitHub commits) during the meeting.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Cody | Rewrite and push Vision & Scope | Before Friday |
| Cody | Write client interview guide | Before Friday |
| Cody | Follow up with Heather on earlier meeting times | Ongoing |
| Everyone | Add questions to Open Issues | Ongoing |

## Questions for the Client

1. If only one thing could be built, what is the main focus? What features are wanted?
2. How much weight should ADA/accessibility get versus general touring and kid interactivity?
3. Which ADA standard or code applies? Is a consultant available?
4. What tech stack is required?
5. Should the app use a database? Can we access the full collection database and its location data (how detailed is it)?
6. Is data from the previous app available?
7. Are there any firm business rules (e.g., admin-only edits)?

## Next Meeting

**Friday, October 23, 2026, 8:00 AM:** review Vision & Scope draft and interview guide; list needed use cases.
