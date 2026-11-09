# Meeting Minutes: Monnig Gallery App Team Meeting (SRS Review and Use Case Tally)

**Date:** Monday, November 9, 2026, ~8:00 AM CT (about 65 min)<br>
**Facilitator / Notes:** Cody Pinkston<br>
**Attendees:** Cody Pinkston, Tanner Temple, Edwin Rodriguez, Bradley Helmholz, Turner DeMott; Koen Dolezar (remote)<br>
**Presenter:** Edwin (Software Requirements Specification)<br>

---

## Summary

Edwin walked the team through the Software Requirements Specification (SRS) section by section, and the team settled several requirements. Cody then tallied everyone's use case ideas by area. The team agreed to write the use cases in pairs, with progress due Wednesday and completed use cases due Friday.

## 1. SRS Review (Edwin)

**General**
- The SRS now reflects the current use cases and documents. Gallery loaner tablets are listed as **pending**; they'll be added if the gallery gets the devices. For now the product is an app people download.
- **Decision: start from scratch.** The team is not building on the previous app. Edwin will fix the introduction to say so.
- Edwin's changes were merged into main.

**Scope and users**
- User classes: visitors, child visitors, and gallery administrators.
- Open question: should "visitor with accessibility needs" be its own user class? One view is that it's covered by "visitor" (about 10% need accessibility tools but far more benefit from them). The other is that a separate class would allow more detail. Left as a comment for later.

**Operating environment and constraints**
- Platforms: mobile devices, plus gallery tablets if available.
- The gallery has no public Wi-Fi. Tablets could be put on a network, but this needs confirmation.
- Constraints added: branding (Monnig or TCU), no photography in the gallery, and who owns the mobile app publisher accounts (Apple charges a fee).
- Assumptions and dependencies: App Store accounts are needed; the app should support the most commonly spoken languages; text-to-speech.
- The comment about the glossary and Vision & Scope was removed, since both are already linked.

**Functional requirements**
- Visitors are read-only and need no account. Only admins (Dr. Mayne and Heather) can edit the database. Content ownership is covered by the admin-only rule.
- **Settings access: decision.** Instead of a settings button on every screen, settings are reached from the **home screen**, and a home button is available from every screen (with an "are you sure?" confirmation from interactive activities). Wording: "Settings shall be accessible from the home screen." The team noted that AI tools may read "one tap from every screen" as a hard requirement, so the wording should be precise. The home-button detail belongs in the design, not the SRS.
- **Languages:** English and Spanish first (French and Vietnamese from the old app are possible later). Interface text is translated; content with no translation shows in English.
- **Text-to-speech:** Reads descriptions aloud and stops when the visitor leaves the screen. How far it extends depends on the accessibility standard.
- **Visit planning:** No in-app booking in 1.0. The app provides a **link to the gallery website/contact page**. The booking idea goes in Vision & Scope as a future item, not in Open Issues.
- **Fonts:** Offer small, medium and large text size. Offering font style is unlikely unless an ADA standard or consultant requires it. Use freely licensed fonts, since some fonts are copyrighted.
- **Business rules in the SRS:** The team is concerned that repeating them here and in the business rules document will let the two go stale. Consider linking instead of copying (unresolved).

**Data and interfaces**
- The data model is a good starting point: the gallery has three rooms, which contain displays, which hold one or more samples. It will change once the team sees the real data.
- There are no reports. After launch, a small group will try the app for feedback.
- The meteorite catalog has no picture descriptions, and it's unclear where those would go. The app uses only the gallery's data and collects no personal information.
- Keep the **gallery map divided into three rooms** for room selection, as in the old app.
- Interfaces: the collection database, a text-to-speech engine, and the gallery website. There's no API document yet, and communication interfaces are not yet defined.

**Quality attributes**
- No overlapping text. Gallery text is used verbatim, and it's already readable for young visitors. Games should suit different age ranges (the client mentioned age-based scavenger hunts).
- Fast loading; HTTPS for all calls, with credentials only for admin; safety not applicable.
- Gallery hours were stated as 1-4 PM Monday to Saturday (to confirm).
- Missing data or a missing network should show a clear message instead of crashing, and show already-loaded data if available.
- Supports iOS and Android; admins handle content updates; the app needs a handoff plan and ownership of service accounts.
- Localization: Spanish first, no currency or time-zone handling (Central time).

**Idea raised:** Dr. Mayne researches a near-Earth asteroid expected to pass close to Earth around 2039; the app could show a visualization or countdown.

## 2. Use Case Tally (Cody)

Cody compiled everyone's ideas (counts show how many people proposed each). Similar ones were merged: "customize visual preferences" counts under change settings, and "identify language preference" counts under both change settings and the first-launch survey.

**26 use cases across 5 areas.** "Votes" is how many people proposed each one.
 
#### Preferences (PREF)
| Use case | Votes | Notes |
|---|:-:|---|
| First launch survey | 3 | Includes choosing a language |
| Change settings | 2 | Includes visual preferences, font size and language |
| Reset preferences | 2 | One general reset (combines "reset for new visitor") |
| Retake setup survey | 1 | |
| Captions on/off | 2 | For audio and video. New idea |
 
#### Text-to-speech (TTS)
| Use case | Votes | Notes |
|---|:-:|---|
| Listen to content | 3 | Reads exhibit and meteorite descriptions aloud |
| Play in selected language | 1 | |
| Narrate activities | 1 | Walks players through games and activities |
| Voice speed | 1 | About 0.5x to 2x |
| Control playback | 1 | Pause, play, replay, skip |
 
#### Data (DAT)
| Use case | Votes | Notes |
|---|:-:|---|
| View meteorite | 3 | |
| Browse database | 2 | |
| Search database | 2 | |
| Filter database | 2 | |
| View favorites | 2 | Saved on the device for now |
| View on-display items | 1 | |
| View 3D model | 1 | Rotate and zoom; depends on 3D scans |
| Save favorite | 1 | |
| View similar meteorites | 1 | Like "related products"; needs a look at the data |
 
#### Tour
| Use case | Votes | Notes |
|---|:-:|---|
| Self-guided tour | 3 | |
| Browse gallery section | 2 | |
| View exhibit | 2 | |
| View gallery map | 1 | |
| Visitor info | 1 | Hours and location |
 
#### Admin (ADM)
| Use case | Votes | Notes |
|---|:-:|---|
| Update content | 4 | Same as "update meteorite database"; edit via a browser-based option |
| Admin login | 1 | |

Notes:
- Koen's ideas were text-to-speech and changing font size. Font size is part of preferences ("every preference in the preference table can be changed").
- "Spoken/audio tour" overlaps with text-to-speech but is a later feature. "Join a group" (a shared tour) is noted for a future version.
- Favorites saved on the device are fine for now. Shared favorites or leaderboards need backend support and are later.
- "View similar meteorites" works like related-product suggestions when shopping (needs a look at the data).
- Database edits should be done through a browser-based option. No cross-cutting use cases were identified. "Sync content" was dropped as it duplicates "update content".
- The **interactive features** area was skipped due to time. The team wants to stay realistic about what will be built and will discuss interactivity separately.

## 3. Writing the Use Cases

- **Decision:** Write use cases in **pairs**, with each person writing some and reviewing the partner's, going back and forth until complete. Pairs then present finished use cases to the group. The team wants to work this way for code too.
- **Pairs:** Cody and Tanner; Koen and Bradley; Edwin and Turner.
- Everyone takes a little from each area instead of whole areas.
- Cody will list the use cases, possibly have AI propose a split, and post it in Slack.
- **Deadlines:** Show some progress by **Wednesday**; completed use cases due **Friday**. The team then moves on to design.

## Decisions
1. Start the app from scratch (not building on the old app).
2. Settings are accessible from the home screen, and the home button is reachable from every screen.
3. English and Spanish first; text size options, with font style only if required.
4. Visit planning is a link to the gallery website in version 1.0.
5. Use cases are written in pairs with cross-review.

## Action Items

| Owner | Action | Due |
|---|---|---|
| Cody | Post the use case list and proposed split in Slack | Soon |
| Cody | Add the in-app booking idea to Vision & Scope as a future item | Soon |
| Each pair | Start the assigned use cases and show progress | Wednesday |
| Each pair | Complete the assigned use cases | Friday, Nov 13 |
| Edwin | Update the SRS: start-from-scratch note, settings and home screen wording, constraints, resolved comments | Soon |
| Team | Confirm with the client: gallery tablets, Wi-Fi, gallery hours | Next client contact |

## Open Issues
- Will the gallery provide loaner tablets, and does it have Wi-Fi for them?
- Should accessibility needs be a separate user class?
- Which accessibility standard applies (affects fonts and text-to-speech scope)?
- Who owns the Apple and Google publisher accounts?
- Should the SRS repeat the business rules or link to them?
- What are the gallery's hours?

## Next Meeting
**Wednesday, November 11, 2026.** Show progress on use cases. Completed use cases are due Friday, November 13.