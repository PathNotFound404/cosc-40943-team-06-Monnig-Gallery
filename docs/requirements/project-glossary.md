# Project Glossary

**Project:** Monnig Meteorite Gallery Tour App
**Team:** _[Team NN]_
**Client:** _[Client name and organization]_
**Version:** 0.1

---

_**How to use this template.** Instructions appear in italic square brackets. Fill in underneath them and leave them in the file until the document is stable._

_**What this document is for.** Every project has words that mean something specific inside the client's organization and something else outside it, or nothing at all. This file fixes one word to one concept, and commits the team, the client, and the AI teammate to using it. That shared vocabulary is called a **ubiquitous language**: the same term in the client conversation, in the vision and scope, in the use cases, in the class names, and in the database columns._

_**Why the glossary is the first artifact you write and the last one you finish.** It is the cheapest document to start, because your client hands you the terms in the first meeting whether you ask or not, and it is the one that keeps paying: every later document cites it instead of redefining things._

## Why this matters when an agent writes your code

_[Read this once, then delete this section when the document goes stable.]_

_If two words in your project mean the same thing and nothing says so, your team will use both. So will your agent. You will end up with a `Team` class and a `Group` table, a `submitReport` endpoint and a `war_entry` record, and every one of those pairs is a bug waiting for the week you try to join them._

_An agent cannot resolve this on its own. Asked to add a feature, it reads what is in the repository and imitates it. If the repository is inconsistent it will faithfully reproduce the inconsistency, and it will invent a plausible synonym for anything the repository never names. A glossary in the repository is the only thing that stops it, because the repository is the whole of the agent's memory of your project._

_There is a second cost, and it arrives before any code is written. **An agent does not read your repository, it searches it**, and it builds the search out of the words you used. If you ask about a "peer review score" in a codebase that calls it a peer evaluation, the first search returns nothing. The agent does not stop; it widens, reads whatever it lands on, and gets to the right file eventually, having spent context and time on the detour. Every term you and your client agree on, written down here and used everywhere, is one search that lands first time._

_The other half is human. When your client says "cycle" in one sentence and "sprint" in the next, that is your signal to ask which one they mean, in the meeting, while they are in front of you. An agent reading the transcript later cannot ask._

## The entries that earn their place

_[The temptation is to define words your teammates already know. Skip those. The entries worth writing are:]_

- _**Terms two stakeholders use differently.** The highest-value entry in any glossary. In airline statistics, the International Civil Aviation Organization says **city-pair** and the International Air Transport Association says **O and D**, for the same thing; the two bodies also say **traffic by flight stage** and **segment traffic** for another. A team that misses this builds a report that silently mixes them._
- _**Terms that sound generic but are not.** "Active", "submitted", "complete", "week". Ask what makes a record active and you often find a business rule nobody had stated._
- _**The client's acronyms**, spelled out, including the ones they use so fluently they have forgotten they are acronyms._
- _**Terms you invented** that the client does not use. Record them, then consider dropping them in favor of the client's word._

_Ask the client directly: "Is there a word your team uses here that I would not guess the meaning of?"_

## Conventions

_[The **term itself is the identifier**. There is no separate numbering scheme, because a glossary entry already has a unique, meaningful name: the word. Cite a term by writing it, and keep the spelling identical everywhere it appears._

_Rules:_

- _One entry per concept. If two words mean the same thing, pick one, define it, and list the other as a synonym under it rather than giving it its own entry._
- _Alphabetical order, so a reader can find a term without searching._
- _Define the concept, not the implementation. "A weekly record of what a student did" is a definition; "a row in the `war` table" is not._
- _Use the client's word when the client has one. You are joining their world, not renaming it._
- _If a term has a meaning outside this project that differs from the one here, say so explicitly.]_

## Revision History

| Date | Version | Description | Author |
|---|---|---|---|
| 10/10/21 | Alpha 1.0 | Initial Definition of Terms | Alex Matthews |

---

## Introduction

The Monnig Meteorite Gallery Tour Assistance Application is an application run on the Android tablets within the gallery, to allow users to navigate more easily

### Purpose

This Glossary displays the terminology used in conjunction with the project and associated database

### Scope

This glossary covers the technology required for the implementation of the application/

## Definitions

_[One `###` heading per term, alphabetical. Follow the heading with a definition of one to three sentences. Add **Synonyms**, **Not to be confused with**, or **Source** lines where they help. Where a term only makes sense with an example, give one._

### Accessibility Feature

“A feature or quality of the application offering a benefit to a user with a visual impairment to aid in their visual experience”

### Achondrite

A stony meteorite that does not contain chondrules.

### Blindness

“The state or condition of being unable to see because of injury, disease, or a congenital condition. Specifically, a complete lack of detail vision”

### Blurred Vision

“Decreased clarity or sharpness in vision.”

### Chondrite

A stony meteorite that has not been modified, by either melting or differentiation of the parent body.

### Chondrule

Forms as molten or partially molten droplets in space and are found within chondrites.

### Class

The make up of what the meteorite is made of. Can either be iron, stone, or stony-irons.

### Contrast

“the degree of difference between tones in a television picture, photograph, or other image”

### Country

The country the meteorite was found in

### Display

“A case in a museum room containing one or more samples”

### Exhibit

“A display, interactive sample, or interactive audiovisual learning aid”

### Fall

Whether or not a fall was observed

### Font

“A set of type of one particular face and size”

### Group

A classification a meteorite can fall into. Can either be a chondrite, primitive achondrite, or achondrite.

### Light Sensitivity

“Extreme sensitivity to environmental brightness and resulting discomfort”

### Loss of central vision

“The loss of detail vision, resulting in having only side vision remaining”

### Meteorite Name

### Monnig #

The catalog number of the specific meteorite

### Outreach Partner

“An individual or group, such as a school, which interacts with museum staff in order to provide an educational experience to its members”

### Remote Visitor

“A visitor accessing the application without being physically present in the museum”

### Room

“One of three large rooms composing the Monnig

### Sample

“An individual meteorite, either on display or in the collection”

### Staff

“An individual involved in managing the operations of the museum”

### Visitor

“An individual present in the museum as a guest”

### Visual Impairment

“A decreased ability to see to a degree that causes problems not fixable by usual means, such as glasses”
