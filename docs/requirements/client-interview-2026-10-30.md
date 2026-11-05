# Client Interview Guide

**Project:** Monnig Meteorite Gallery Tour App (working name: TCU Monnig Museum Guide)
**Team:** 06
**Client:** Monnig Meteorite Gallery, TCU
**Meeting:** Meeting 2, the follow-up to the 10/15 kickoff

---

_**What this file is.** Your script going in, your meeting record coming out. Copy it once per meeting into `docs/requirements/` as `client-interview-YYYY-MM-DD.md` and commit it the same day._

_**How to use it.** Each section says what it is for, what it is worth in minutes, and whether it must happen in this meeting. The example questions are written for a different domain (technical recruiting) on purpose, so you cannot use them unchanged. Rewrite them in your client's words before you walk in, and write the answers underneath in **their** words rather than yours._

_**Work it with your agent.** Give it your one-page brief, this file **including these instructions**, and a role: "You are an experienced business analyst preparing for a first client interview. Using the question types in this guide, write the version of each question that fits this client's domain, and list every acronym in the brief you would want defined before the meeting." Then do the part it cannot: pick which of its questions are worth your client's limited hour. **Sort by what it costs you to stay wrong**, not by what is easy to ask. Anything you could answer by reading a document is not worth a client minute._

_Sources used to prepare this guide: the 10/15 kickoff notes (the client brief), [vision-and-scope.md](vision-and-scope.md), and the 2021–22 documentation. The **Already known** lists come from those sources. Don't spend client time re-asking them; confirm them only where marked._

## Listen before you build

**An idea you propose in the first twenty minutes is not worth what it costs you.** Your strongest instinct will be to show your client you understood by describing what you would build. Early, that ends the elicitation: a client who has heard your idea reacts to it instead of describing their world.

This is about order, not silence. Some clients want to think out loud with you, and a few asked for the project because they want exactly that help. Do it **after** the read-back in section 14, when you can describe their process back to them accurately and the brainstorm is grounded in their world rather than your imagination. If they open by asking for your ideas, say you have some and would rather earn them by understanding the process first, then come back to it before you leave.

**The separate rule is absolute: commit to nothing.** Not a deadline, not a feature, not "sure, we can add that". Five teammates are not in the room. "Let me write that down and bring it back to the team" is the whole sentence, and it holds even when a client pushes.

## Before you go

- [ ] **Three roles assigned.** Lead asks and moves the agenda, one person not four. Scribe writes and does not ask, capturing exact words, especially nouns. Observer watches what is not said: hesitation, the topic they keep returning to, who they defer to.
- [ ] **Everyone has read the client's pitch slides** (TCU Online) and written questions individually before you merged them. The ones two of you wrote independently are the ones to ask.
- [ ] **Your agent has interviewed you on the brief.** Ask it: "Interview me about this project, a few questions at a time, with multiple-choice answers. When I answer *ask the client*, add the question to this guide." Answer what the brief already tells you; everything else is a question for this meeting. Never pick an option for the client.
- [ ] **Shortlist sent to the client the day before.** They arrive with answers instead of promises.
- [ ] **This file open on the scribe's laptop**, with someone on paper as backup.
- [ ] **Someone owns the clock.** You will not get through this guide, and that is expected.

### Shortlist to send the client on 2026-10-29

These are the questions that are most expensive to get wrong, so the client can come with answers:

1. **Collection data:** Can we get access to the catalog at monnigcatalog.tcu.edu (an export or an API), plus the separate list of items currently on display? Who owns each one?
2. **Prior materials:** Can Asa share the 2021–22 app's code, data and documentation, and by when?
3. **After we graduate:** Who will maintain the app and its content, and who will own the App Store and Google Play accounts?
4. **First priority:** If only one thing works well in the first release, should it be accessibility for visually impaired visitors, or the general visitor guide (trip planning, collection, audio)?
5. **Real users:** Can we talk to visually impaired visitors, or to the visual-impairment specialist discussed with TCU Student Support Services?
6. **Approvals:** Who approves the app before release (Heather, Wei, TCU IT, TCU Marketing), and what is Primary Point's role?

## Meeting record

| | |
|---|---|
| **Date** | 2026-10-30 |
| **Time and location** | LIB 2122 |
| **Client participants** | Heather Stepp (Monnig) |
| **Team participants** | Tanner (scribe until 8:15), Bradley (scribe until 8:30), Edwin (scribe until 8:45), Turner(scribe), Cody (Lead) |
| **Recording** | Not Recorded |
| **Photos of screens or forms** | Given scavenger hunt sheets |

_Ask to record, and say why: so nobody is transcribing instead of listening. If they decline, the scribe matters more. Ask separately about photographing screens, forms, and reports. A photo of the spreadsheet they actually use beats a page of notes about it._

## The shape of the hour

Most first meetings run 60 to 90 minutes. Budget for the short one.

| Part | Sections | 60 min | 90 min |
|---|---|---|---|
| Opening | 1 | 5 | 5 |
| The business | 2, 3 | 10 | 15 |
| The process | 4, 5, 6, 7, 8 | 25 | 40 |
| The boundaries | 9, 10, 11, 12 | 10 | 15 |
| The close | 13, 14, 15 | 10 | 15 |

**Extra time goes into section 4 first.** It repays another ten minutes and it is the only section you cannot reconstruct from notes afterward.

"Can wait" means the next meeting, not never. When you are behind, drop from the middle. **Never drop 14 or 15:** the read-back is where you learn you misunderstood something, and the close is where you stop losing two weeks to scheduling.

---

# Opening

## 1. Get to know your client

_**Must ask. 5 min.** Not small talk. Whose problem is this, how much of the domain lives only in this person's head, and how much of their own time do they have for you? A client fitting this around a full job answers email slowly, and you want to know that in week 3 rather than week 9._

_Adapt:_

- Tell us about your role at the Monnig.
- How is running the gallery split between you and Dr. Mayne?
- How does restarting this app fit alongside the rest of your work this year?
- How much time can you give us between meetings, and when the two of you see something differently, who makes the call?

**Already known:**

- Heather wants to expand the app's scope beyond the 2021–22 version. Funding is available on Monnig's side.
- The gallery is supported by TCU staff: Dr. Rhiannon Mayne and Dr. Heather Stepp.

**What they said:**

- **Role:** Outreach educator. Over 20 years in education; formerly taught middle school science; a traveling teacher. Does tours and groups, public education, and tries to bring people into the gallery. Also gives class lessons (planetarium too).
- **Split with Dr. Mayne:** Skipped, not answered.
- **How the app fits this year:**
  - The app should be "accessible to all" (visually and hearing impaired included), with a guided tour for those who need it. "Main is guided tour."
  - The gallery is "not very child friendly" right now. "Make it interactive": scavenger hunt, escape room ideas, and different ones for different age ranges.
  - Follow-up raised: will the kids have iPads provided, or will they need their own device? (not answered)
- **Time between meetings / who makes the call:** Not answered. See section 13 for office hours.

---

# The business

## 2. Context and domain

_**Must ask. 5 min.** You are here for vocabulary as much as facts. Every term you do not recognize goes in the glossary before you leave. When your client says "cycle" in one sentence and "sprint" in the next, ask which they mean while they are still in front of you; an agent reading the transcript afterward cannot ask._

_Adapt:_

- Walk us through how the gallery is laid out today: the three rooms, the displays, and how a visitor usually moves through them.
- What is the difference between a display, an exhibit, a sample, and an entry in the catalog?
- What are you expecting in this app in relation to ADA?
- Is a specific standard of compliance/ADA we should refer to?

**Already known:**

- The gallery opened February 1, 2003. It has three large rooms, is in the Sid Richardson Building, and gets over 10,000 visitors a year.
- The 2021 glossary already defines Room, Display, Exhibit, Sample, Monnig #, Class, Group, Fall, Chondrite and Achondrite. Listen for whether the client uses these words the same way.

**What they said:**

- **Layout, in the order she walked it:**
  - People "need to know about the asteroid belt." About 90% of meteorites come from asteroids, so the gallery starts with the asteroid belt, then the theater area. Behind the theater is the history of meteorites, then how meteorites enter through the atmosphere.
  - Types of meteorites:
    - Stones: chondrites (about 80%) and achondrites.
    - Lunar and Martian meteorites. These "landed here" and were found on the ground. How do we know they are from the Moon or Mars? She covers that in tours.
    - Irons: iron and nickel, "same as core of Earth."
    - Stony irons: a mix of iron and minerals.
  - The next room is all about collisions.
  - The next wall is all terrestrial rocks and the transformation of rocks: what causes rocks to change (heat and pressure).
  - New acquisition area: a silver piece with "crazy stories" that kids love. (A handwritten note beside this reads "Arizona meteorite!!!"; likely the same piece, not confirmed.)
  - The final room is all Texas, only Texas: why Texas finds the most meteorites.
- **Display vs. exhibit vs. sample vs. catalog entry:** Skipped (struck through in the notes; typed notes say N/A).
- **ADA expectations:** "Accessible to all people": visually and hearing impaired. She is "not sure, will look into it."
- **Specific standard:** "No set standard right now for accessibility." She will look into it.

**Terms for the glossary, in their words:**

- Chondrite (about 80% of stones) and achondrite. Heard in the same breath: stones, lunar meteorites, Martian meteorites.
- Iron: iron and nickel, "same as core of Earth."
- Stony iron: iron plus minerals.
- Terrestrial rocks: the wall on what changes rocks (heat and pressure).
- Theater area, new acquisition area.
- Scavenger hunt vs. tour (self-guided or guided), mini lesson, outreach.
- Not heard: *station*, *ADA info*, *Primary Point*. Display vs. exhibit was skipped, so no usage difference to flag.

## 3. Business drivers and objectives

_**Must ask. 5 min.** Why this, why now. These become your business objectives, so push for a number: when they name a benefit, ask the follow-up nobody asks, **what is that number today?**_

_Expect to miss it here. Baselines surface in section 4, when they are looking at the thing that takes the time. Ask the objective now, listen for the number all hour, and close the gap in the read-back._

_Adapt:_

- Why restart the app now, after the 2021–22 version?
- What were the major failures of the last project?
- Of the goals in your brief (access for visually impaired visitors, trip planning, audio, and activities for kids), which one matters most if we can only do one really well?
- ***A year from now, how will you know the app worked: downloads, visitors using it in the gallery, feedback from visually impaired visitors, school groups?***
- What are those numbers today?

**Already known:** The brief's primary goal is to make the museum accessible to visually impaired visitors. The broader vision is to serve all visitors, with audio as a big emphasis.

**What they said:**

- **Why restart now / major failures of the last project:** Not answered. In section 6 she said she "wasn't here when the app launched" and that the graphics are "sad."
- **Which goal matters most:**
  - Heather: **kids** ("kids very important"), with a guided audio tour.
  - Dr. Mayne (as relayed by Heather): **ADA**.
  - Context: tours bring a lot of adults but mostly kids, and many have learning disabilities, so she wants a guided part.
- **How we'll know it worked in a year:**
  - A survey at the end asking how things were and whether they had a good time. Surveys are already positive.
  - People enjoy being in the space.
  - Hands-on experiences, interactivity, and the scavenger hunt.
  - Visitors love the part where meteorites are taken out of the case, touching the meteorites, and the interactive meteorite.
  - Kids find the hands-on experience fun.
- **What visitors want to see more of:**
  - Expansion into geology.
  - Info on space and meteorites, including how meteorites move through the atmosphere.
  - More interactivity.
  - "I wish it was easier to find on campus."
- **Numbers today:**
  - Over 600 people in tours since May (May 26).
  - Only tour groups, not people on their own.
  - 2,100 students reached through outreach (time period not stated).

**Candidate objectives (`BO-<slug>`), with baselines where you got them:**

- `BO-kids-engagement` (kids are very important; interactive, age-targeted activities): baseline unknown. Only the 600+ tour visitors since May and 2,100 outreach students were given.
- `BO-guided-audio-tour` (guided audio tour, especially for visitors with learning disabilities): baseline unknown.
- `BO-accessability`: no accessibility standard is set today. Heather will look into it, so "compliant" is still undefined.
- `BO-display-collection`: baseline unknown, not discussed.
- `BO-language-options`: not discussed.
- `BO-store-release`: no release date given. The only date was grant-related (see section 9).
- `SM-downloads`: no "X" given. Success was described through end-of-visit surveys, with survey results that are already positive. `OI-*` raised.

---

# The process

## 4. How it works today

_**Must ask. 10 min, the best ten in the meeting.** Ask them to show you rather than tell you. People describe the process they believe they follow; the spreadsheet shows the one they actually follow, and the gap is where the requirements hide. **"Show me" is the two most productive words in requirements engineering, and they cost nothing.**_

_Walk one real recent case end to end. "Take me through the last one you did" beats "how does it usually work", because the general shape is a summary they have given before and the last real one has the exceptions in it._

_Adapt:_

- Take us through the last visit you hosted, from the moment someone decided to come until they left.
- How does a visitor plan a trip today: the website, a phone call, an email?
- When did a visually impaired visitor last come, and what did staff do for them?
- How does a school group visit run?


**Already known:** Today the only ways to explore the gallery are the website (monnigmuseum.tcu.edu), the catalog (monnigcatalog.tcu.edu) and an in-person visit. A tour takes roughly 30 to 60 minutes.

**What they said:**

*Planning a visit (how a group books):*

1. The group fills out an interest form on the website.
2. Heather contacts them and works out days and times. Tours are usually between 9 AM and 12 PM; the gallery is closed to outsiders then and used for those groups.
3. She asks the number of people, gives parking instructions ("parking instruction!!!"), and asks whether they want a guided tour or a scavenger hunt. (A note here reads "Wave 'em down," which is unclear. It may refer to waving groups in at parking.)

*The visit itself (last visit / how a group visit runs):*

1. Greet the group.
2. Two options: the scavenger hunt, or the actual tour (walk them through; self-guided is also an option).
3. Scavenger hunt: set expectations, watch a video, then go search.
4. Once everyone is done, everyone gathers for a short hands-on mini lesson and she pulls out meteorites at the end.
5. People on their own can ask for a tour or a scavenger hunt on request.
6. She stays with guests, answering questions.

- **Last visually impaired visitor and what staff did:** Not answered.
- **School group visit:** No separate answer; the visit flow above is how groups run.

**Artifacts they showed us:** _[None noted. Ask for copies of everything.]_

## 5. What is hard about it

_**Must ask. 5 min.** The complaint is usually the requirement. Listen for "must", "unless", "only", and "except", which arrive unannounced in the middle of a story about something else. Those sentences are business rules, and they exist whether or not your software does._

_Adapt:_

- What do visitors ask staff that the gallery can't answer on its own?
- What is hardest about serving visitors with disabilities today?
- Where do kids lose interest?
- Are there rules about what we can show: items in the collection but not on display, loaned items, photos, or the incoming Alan Bean paintings?
- Does a scientist have to review content before it is published?

**What they said:**

- **What visitors ask that the gallery can't answer:**
  - "Wild crazy questions," including "what is this?" about certain rocks.
  - Heather's background is not meteorites, so she has gaps in her knowledge. She either googles or asks Dr. Mayne, who knows a lot more ("great if available").
  - The rest of the staff isn't in the gallery; they staff outside.
- **Hardest about serving visitors with disabilities:** Not answered.
- **Where kids lose interest:**
  - "Pretty quickly," right after the video.
  - Kids really like interactivity and touching things (including the Mars meteorite). They stay more engaged in the scavenger hunt.
  - From 3rd grade up it locks in; the "itty bitty" ones don't.
  - Pre-K through 12th grade is hard to work with all at once. She would potentially like more age-targeted activities.
  - Age groups she described:
    - Pre-K: find the big rock (pictures).
    - Kinder to 2nd: pre-readers, draw your favorite (draw pictures).
    - 3rd to 5th: start to read; the scavenger hunt is effective from here.
    - 6th to 8th.
    - 9th to 12th: "these guys also exist."
- **Rules about what we can show:** Not answered (struck through in the notes). Only related item: "inside says no photography" (see section 9).
- **Scientist review before publishing:** Not answered.

**Rules heard (candidate `BR-*` for week 4):**

- Groups are given the gallery during their tour slot (usually 9 AM to 12 PM); the gallery is closed to outsiders then.
- Today only tour groups are served; people on their own get a tour or scavenger hunt only on request.
- No photography is allowed inside the gallery (reason unknown).

## 6. What already works

_**Must ask. 3 min.** Ask what is good before you propose replacing it. A team that removes something the client liked has lost trust it will not get back this semester, and nobody volunteers this unasked._

_Adapt:_

- What about a visit today would you keep exactly as it is?
- Is anything from the 2021–22 app worth keeping: the language picker, QR scanning, the visual-preference survey, location by beacon, or the gallery tablets?
- What was tried before, and why?

**Already known:** The previous version had location awareness (sensors or NFC tags), Google Translate for translation, and an existing list of items on display.

**What they said:**

- **Keep exactly as is:**
  - The hands-on experience (if a tour).
  - The flow of the tour ("current flow is good").
  - The hands-on mini lesson at the end.
- **Anything from the 2021–22 app worth keeping:** N/A. She wasn't here when the app launched. Her one comment was "graphics are sad."
- **What was tried before, and why:** N/A (same reason).

**Explicitly: what must not change:** the hands-on tour experience, the tour flow, and the hands-on mini lesson at the end.

## 7. Volumes and scale

_**Must ask. 3 min.** These numbers decide most of your architecture, and they are cheap to ask for and expensive to guess. Twenty records a semester and two hundred thousand a day are different systems._

_Adapt:_

- How many visitors come in a typical week, and in the busiest week?
- When is that?
- What is the biggest group, such as a school field trip?
- How many items are on display, compared with the full catalog?
- *How much text, how many photos, and how much audio per item?
- How often does what's on display change?
- How good are Wi-Fi and cell signal inside the gallery rooms?

**Already known:** Over 10,000 visitors a year. The collection is roughly 3,000 items. Exhibits are mostly permanent, so content won't need frequent updates.

**What they said:**

- **Visitors per week / busiest week / when:** No weekly figure. Only the total: over 600 people in tours since May 26 (see section 3).
- **Biggest group:**
  - Space is limiting. About 30 is the max, and she is "pushing it" at 30.
  - Groups of 30 are typically split into 2 groups; 15 is best.
  - Personally she can handle a lot.
- **Items on display vs. full catalog:** Not answered.
- **Text, photos and audio per item:** Not answered.
- **How often the display changes:** Not answered.
- **Wi-Fi and cell:**
  - No problems. Wi-Fi is good, cell service is good, and the education room works well.
  - No guest Wi-Fi network.
  - If the gallery gets tablets, they will connect to the network.

## 8. Who the users are

_**Must ask. 4 min.** The person who commissions software is often not the person who uses it._

_**If you cannot reach the real users, that is a project risk, not a scheduling detail.** Record it as an `RI-<slug>` the same day. Building from a proxy's account is the most common way a capstone ships something nobody uses, and it is survivable only if you know you are doing it._

_Adapt:_

- Who do you picture using the app most: walk-in visitors, families, school groups, visually impaired visitors, people who never come in person?
- Can we talk with two or three visually impaired visitors, or the visual-impairment specialist discussed with TCU Student Support Services?
- Will staff or volunteers test the app before release?
- Will the gallery still lend tablets, or should we assume visitors use their own phones?

**Already known:** The stakeholders in the vision doc are general visitors, visitors with disabilities, children and families, Monnig staff, and Asa (TCU IT).

**What they said:**

- **Who uses it most:** "Can't say, but probably the groups." Individuals want to learn; they are seeking information to be given to them. Tour visitors want someone to give them the information, and groups usually come in to get the information.
- **Visually impaired visitors / the specialist:** Not answered.
- **Testing before release:**
  - The whole team can test the app, and Dr. Mayne and grad students can too. Heather's own children could also test.
  - She can ask a group that is going in to test the app and give feedback.
  - Starpoint School could be the "guinea pigs"; some of its students have dyslexia.
  - Testing with staff and kids was named as the plan.
- **Tablets:** "Possibility of gallery tabs." No firm answer; whether visitors use their own devices is still open (see the follow-up in section 1).

**Can we reach real users? If not, why, and what is the risk:** Not for visually impaired visitors. That question was not answered, so no access to them was offered. Starpoint School (including students with dyslexia), school groups and Heather's children were offered for testing. Risk: the stated top accessibility goal has no real users yet. Record as `RI-no-visually-impaired-users`.

---

# The boundaries

## 9. Constraints and rules

_**Must ask. 4 min.** Nobody asks these in meeting 1 and everybody regrets it in November. A constraint restricts how you may build, and it is a requirement even though it describes no behavior. Ask directly; clients do not volunteer these, they assume you know._

_Adapt:_

- Does the app have to be published under a TCU developer account?
- Do TCU IT or TCU Marketing have to approve the technology, the branding, or the name, and how long does that take?

- Should the app collect any visitor data, accounts, or analytics?
- Are there image rights on collection photos or the Alan Bean paintings?
- Are there hard dates we should know about?
- Who pays for developer accounts, hosting, and translation or text-to-speech services, and who signs off?

**Already known:** Planned for both the iOS App Store and Google Play.

**What they said:**

- **TCU developer account:** Not answered. One handwritten note says it "might not go through Monnig for deployment"; no other note confirms this, so who deploys is unclear.
- **Approvals and branding:**
  - Only brand with Monnig, not TCU (for now). Maybe don't brand TCU in the app, just Monnig.
  - Ask TCU Marketing about TCU branding.
  - Monnig has a logo; the color scheme is white and purple, as on the website ("spacey").
  - How long approval takes: not answered.
- **Visitor data, accounts, analytics:**
  - Yes, "very useful if it can be done," especially with the grant. Survey.
  - Kids' age range, grade range and adult age range.
- **Image rights:** "Don't know of any." Inside the gallery signs say no photography; she doesn't know why.
- **Hard dates:**
  - There are 2 grants right now.
  - The first one ends "next December" (year not stated; it was said on 2026-10-30).
  - The new grant runs for 4 years.
- **Who pays:** Monnig pays for everything. Who signs off on spending: not stated.

## 10. External dependencies

_**Must ask. 3 min.** What your system has to talk to. Access credentials take weeks to obtain, so the ask has to happen now._

_Adapt:_

- Who owns the catalog at monnigcatalog.tcu.edu?
- *Can we get an export or an API, and does it record whether an item is on display and where it is in the gallery?
- Is the separate list of items on display, and who keeps it current?
- *Does Asa still have the 2021–22 code, data, and documentation, and when can we have them?
- Did the old app pay for Google Translate or text-to-speech?


**Already known:** The collection database exists and is assumed to be maintained. Asa likely has the prior materials and the secondary list.

**What they said:** None of these questions were answered. One related remark came up in section 13: the meteorite collection is in the vault, and that is a question for Dr. Mayne.

## 11. Lifetime and who maintains it

_**Must ask. 2 min.** The question students never ask and every client can answer. **Who runs this after we graduate, and what do they already know how to run?** It constrains your entire technology choice, so ask before you pick a stack rather than after._

_Adapt:_

- How many years should the app keep running?
- Who keeps it working and updates content after we graduate: Asa or TCU IT, gallery staff, a future student team?
- What do they already know how to maintain, and in what languages?
- Should staff be able to edit content without a developer?
- Who owns the App Store and Google Play accounts, and who pays the renewals next year?

**What they said:** Not asked or no answer recorded. (The only related fact: the new grant runs 4 years; see section 9.)

## 12. Other stakeholders

_**If there is time. 1 min.** Cheap, and occasionally it turns out somebody with a veto has not been consulted._

_Adapt:_

- Who signs off on the finished app?
- Is there anyone who would rather this project did not happen?

**Already known:** The brief's next steps say documents go to Heather and Wei for approval.

**What they said:**

- **Who signs off:** It comes down to Dr. Mayne for final sign-off; Heather has input.
- **Anyone who would rather this didn't happen:** "No." They don't answer to anyone.

---

# The close

## 13. Anything else

_**Must ask. 1 min.** Ask it, then stop talking and wait through the silence. Highest-yield question in the guide, and it only works if you do not fill the pause._

_Adapt:_

- Is there anything we should have asked and didn't?
- What worries you most about restarting this app?

**What they said:**

- **Anything we should have asked:**
  - Whatever we need, just let Mrs. Heather know.
  - Office hours: Mon to Thu, 7 AM to 2 PM.
- **What worries her about restarting:**
  - "Looking into getting access into the software." (Unclear which software; needs a follow-up.)
  - "Core app done this semester. Next semester just build fun stuff." (The notes do not say who said this; confirm it was the client.)
  - The meteorite collection is in the vault. That is a question for Dr. Mayne.

## 14. The read-back

_**Never skip. 5 min.** The part teams cut when they run late, and the highest-value five minutes of the hour. Say what you understood in your own words and watch for the correction. A client who is nodding may be being polite; a client correcting you is engaged, and that correction is usually the single most useful sentence of the meeting._

_Read back four things: the problem in one sentence, the objectives with any numbers you got, the top three things you heard are hard, and one thing you believe is **out** of scope. The last produces more correction than the other three together._

_Fill in the [vision-and-scope.md](vision-and-scope.md) vision statement table during the meeting, read its six rows aloud, and see what they fix. Ninety seconds._

**Draft read-back (adjust it live):**

1. **Problem:** The gallery has almost no digital presence, so visitors can't easily plan a visit, explore the collection, or take in the exhibits on their own terms, and visually impaired visitors are the most underserved.
2. **Objectives:** Show the whole collection, meet ADA requirements, offer multiple languages, include interactive learning, and publish on both app stores. Add any numbers you got today.
3. **Top three hard things:** _[Fill in from section 5.]_
4. **Out of scope for the first release:** The interactive features (scavenger hunts, quizzes, the find map, section screens, videos and games) come after the core app works.
5. **Vision table:** Read the six rows of vision-and-scope §2.4 aloud. Confirm the product name: is it "TCU Monnig Museum Guide" from the brief, or "Monnig Meteorite Gallery Tour App" from the vision doc?

**What we read back, and what they corrected:** _[No read-back is recorded in any of the notes.]_

## 15. Before you leave the room

_**Never skip. 4 min.** Unglamorous, and where teams lose two weeks._

- [ ] **Next meeting on the calendar** before anyone stands up. Not "we will be in touch". _[Date, time, place: not noted]_
- [ ] **Cadence agreed:** how often, roughly how long, and in person or remote. This course expects meetings **in person, on campus** where your client can travel; if they are outside DFW, agree the tool and who sends the link. _[Cadence: not noted]_
- [ ] **Contact channel and how fast they reply.** _[Heather: email is the best way. Office hours Mon to Thu, 7 AM to 2 PM. Phone number written in the handwritten notes: 817-723-6018 (confirm it is hers). Turnaround: not noted.]_
- [ ] **Who to contact between meetings**, including when this person is away. _[Heather ("let Mrs. Heather know"). Backup contact: not noted. Dr. Mayne is the content expert.]_
- [ ] **Copies requested** of every artifact you were shown. _[What, and who is sending it: not noted]_ At minimum, request:
    - the 2021–22 code, data and documentation (Asa)
    - access to or an export of monnigcatalog.tcu.edu
    - the list of items currently on display
    - the display label text
    - a floor plan of the three rooms
    - information on the Alan Bean paintings
- [ ] **Introductions requested** to anyone named in sections 8 and 12. _[Who: not noted. Names that came up: Dr. Mayne, Starpoint School (test group). Likely candidates still: Asa, Wei, Primary Point, the TCU Student Support Services contact, and the visual-impairment specialist.]_
- [ ] **Say what happens next**, in one sentence, so they know what to expect and when.

---

# After the meeting

_File everything within 24 hours, while you still remember why each answer mattered. This file is a record, not a home._

| Section | Feeds |
|---|---|
| 1, 2 | [project-glossary.md](project-glossary.md), and Background in [vision-and-scope.md](vision-and-scope.md) |
| 3 | Business Opportunity, Objectives, and Success Metrics in [vision-and-scope.md](vision-and-scope.md) |
| 4, 6 | Background and the process flow in [vision-and-scope.md](vision-and-scope.md); use cases in week 4 |
| 5 | Business rules catalog, week 4 |
| 7, 9, 10 | Quality attributes, constraints, and external interfaces in the specification, week 4 |
| 8, 12 | Stakeholder Profiles in [vision-and-scope.md](vision-and-scope.md) |
| 8, 11 | Risks (`RI-<slug>`) and assumptions (`AS-<slug>`) in [vision-and-scope.md](vision-and-scope.md) |
| 14 | Scope and the vision statement in [vision-and-scope.md](vision-and-scope.md) |
| Anything unanswered | [OPEN-ISSUES.md](OPEN-ISSUES.md) |

## Initial ideas

_[Solutions anyone floated, yours or theirs. Record them here and nowhere else yet. A solution the client already picked ("then I select the state from a drop-down") is not a requirement, and writing it into the specification makes a design decision on their behalf. Ask why until you reach the need underneath, then write down the need.]_

These ideas were already floated before this meeting. Ask why until you reach the need underneath each one:

- Location awareness through sensors, NFC tags or Bluetooth beacons, so the app knows which exhibit a visitor is near.
- "Scan at a station" activities for kids.
- QR codes on displays and signage.
- Translation through Google Translate.
- Gallery-owned tablets for visitors.
- Scavenger hunts, quizzes, a find map with a heat map, and videos and games.
- Light/dark mode, adjustable text size, and text-to-speech.
- Bundling content in the app so it works on weak gallery Wi-Fi.

Floated in this meeting (Heather's ideas, in her words):

- A guided audio tour, for those who need it (especially visitors with learning disabilities).
- Scavenger hunt in the app, with different versions for different age ranges. Her examples: Pre-K "find the big rock" (pictures); Kinder to 2nd "draw your favorite" (pre-readers); 3rd to 5th and up a reading-based scavenger hunt.
- Escape room ideas.
- Asking questions inside the app (handwritten idea note; the notes don't say who floated it).
- Expansion into geology content, and info on how meteorites move through the atmosphere.
- Help finding the gallery on campus ("I wish it was easier to find").
- Survey and analytics in the app, by age range, grade range and adult age range, tied to the grant.
- Gallery tablets ("possibility of gallery tabs").
- Keep the hands-on mini lesson at the end of the tour.

## Disagreements and hesitations

_[The observer's section, and the one that evaporates fastest. Two participants using the same word differently. A question answered by the wrong person. A topic they returned to three times. An answer that changed between the start and the end. A visible pause before "yes". None of it is evidence on its own; all of it tells you where to look next.]_

- **First priority differs between the two stakeholders.** Heather said kids; she relayed that Dr. Mayne's priority is ADA. Nobody settled which comes first in release 1.
- **ADA answers were hesitant.** "Not sure, will look into it," and "no set standard right now."
- **Kids and interactivity came up repeatedly.** The kids theme (not child friendly, scavenger hunt, interactivity, hands-on) came up in sections 1, 3, 5 and 6. Visually impaired visitors came up only in the general "accessible to all" answer.
- **Wi-Fi.** Several notes say Wi-Fi is good, and also that there is no guest Wi-Fi network. Cell service is good.
- **Number of meteorite types.** One set of notes says "2 types of meteorites"; another lists stones, irons and stony irons.
- **Who deploys and brands.** "Only brand with Monnig, not TCU (for now)" and Monnig pays for everything, but one handwritten note says it "might not go through Monnig for deployment." Unresolved.
- **Sign-off.** The handwritten notes show a second name (looks like Dr. Stepp) crossed out after Dr. Mayne. Other notes say Dr. Mayne signs off and Heather has input.
- **Heather leans on Dr. Mayne** for content knowledge ("her background is not meteorites"). Dr. Mayne was not in the room, and several content and data questions went to her.
- **Skipped questions.** The split with Dr. Mayne, and display vs. exhibit vs. sample vs. catalog entry.
- **Dates.** The "next December" grant end could mean December 2026 or 2027.

## Open questions

_[Everything you could not answer, and everything they answered with "I would have to check". Copy each into [OPEN-ISSUES.md](OPEN-ISSUES.md) as an `OI-*` with the person who can answer it, then sort them before the next meeting by what it costs you to stay wrong.]_

Going in, these are the open questions, sorted by what it costs to stay wrong. Cross off what gets answered:

1. Access to the catalog data and its format, and to the list of items on display. Without these there is no content (section 10). **Still open.** Heather says the meteorite database is in the vault; this is a question for Dr. Mayne.
2. Who maintains the app after graduation, and who owns the store accounts. This shapes the technology choice (section 11). **Not asked, still open.**
3. Whether Asa's prior code, data and docs are available, and when (section 10). **Not asked, still open.**
4. First-release priority: accessibility for visually impaired visitors, or the general visitor guide (section 3). **Partly answered, still open:** Heather says kids, Dr. Mayne says ADA. One note says core app this semester and "fun stuff" next semester (confirm who said it).
5. Whether we can reach visually impaired users or the specialist (section 8). **Not answered, still open.** Starpoint School (some students have dyslexia) was offered for testing.
6. Which accessibility standard to meet (section 9). **Still open:** none is set; Heather will look into it.
7. Primary Point's role, and how the work is split (sections 10 and 12). **Not discussed, still open.** (Heather mentioned Starpoint School as a test group; not the same as Primary Point as far as the notes show.)
8. Who approves the app: Wei, TCU IT, TCU Marketing (sections 9 and 12). **Partly answered:** Dr. Mayne gives final sign-off, Heather has input. TCU IT, Wei and Marketing not covered; ask Marketing about TCU branding.
9. Whether location awareness is wanted in the first release (NFC, beacons, QR or none) (section 6). **Not discussed, still open.**
10. ~~Wi-Fi and cell coverage in the gallery (section 7).~~ **Answered:** no problems, cell good, no guest Wi-Fi, education room works well.
11. Which languages, and whether machine translation is acceptable for scientific terms (sections 3 and 5). **Not discussed, still open.**
12. The app's name (section 14). **Not discussed, still open.**
13. Success targets: the download number, and any usage numbers in the gallery (section 3). **Partly answered:** success is judged by end-of-visit surveys (already positive); baseline is 600+ tour visitors since May 26 and 2,100 outreach students; no download target.

New questions raised by this meeting:

14. Will kids use gallery-provided tablets/iPads or their own devices? With no guest Wi-Fi, how will visitors' phones reach content (cell service is good)? (sections 1, 7, 8)
15. Who publishes and deploys the app: Monnig or TCU? And what branding can the app use (TCU Marketing)? (section 9)
16. Which grant ends "next December" (2026 or 2027), what does the new 4-year grant require us to report (surveys, age ranges), and who pays for the grant-related data collection? (section 9)
17. What did Heather mean by "looking into getting access into the software"? And confirm who said "core app done this semester, fun stuff next semester." (section 13)
18. Why is there no photography inside the gallery, and does it affect collection photos in the app? (section 9)
19. How should content differ by age range (Pre-K to 12th grade) and for visitors with learning disabilities? (sections 1, 3, 5)
20. Does a scientist (Dr. Mayne) have to review content before it is published? Not answered (section 5).

Not asked or no answer recorded: why restart now and the last app's major failures (sec 3); the last visually impaired visit and what is hardest about serving visitors with disabilities (secs 4, 5); rules on what we can show (sec 5); items on display vs. catalog, text/photo/audio per item, and how often the display changes (sec 7); visitors in a typical or busiest week (sec 7); TCU developer account and how long approvals take (sec 9); all of sections 10 and 11; time between meetings and who makes the call (sec 1); the split with Dr. Mayne (sec 1).

---

_**Within 24 hours**, send the client your notes and the open questions. It creates the record and gives them a second chance to correct you while the meeting is fresh. Then commit this file._