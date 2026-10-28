# Business Rules

**Project:** Monnig Meteorite Gallery Tour App
**Team:** 06
**Client:** Monnig Meteorite Gallery, Texas Christian University
**Version:** 0.1

---

## 1. Introduction

### 1.1 Purpose

This document records the business policies and operating constraints that govern the Monnig Meteorite Gallery app so that the project requirements can cite them rather than restating them. These rules define the business context the software must serve, including accessibility expectations, visitor-facing content standards, and the product priorities the museum has for the first release.

### 1.2 Scope

These business rules cover the museum's digital visitor experience, including accessibility, multilingual support, exhibit information, collection search, and the release priorities for the mobile app. This document does not define internal software design choices or non-business implementation details; those are addressed in the specification and architectural documents.

---

## 2. Rules

### 2.1 Visitor Access and Accessibility

- **`BR-accessibility-first`:** The app must provide an accessible visitor experience for people with disabilities by supporting readable text, strong contrast, adjustable text size, and assistive-friendly content presentation.  
  **Source:** Monnig Meteorite Gallery project brief and vision and scope, 2026.
- **`BR-audio-tts-available`:** Every visitor-facing exhibit description and informational label in the app must be available through audio or text-to-speech output when the visitor chooses to use it.  
  **Source:** Monnig Meteorite Gallery project brief and accessibility goals, 2026.
- **`BR-language-options`:** The app must support English, Spanish, French, and Vietnamese as visitor language options and present the selected language consistently across the interface and exhibit content.  
  **Source:** Monnig Meteorite Gallery project brief and vision and scope, 2026.

### 2.2 Content, Search, and Collection

- **`BR-exhibit-content-source`:** Exhibit and collection information displayed in the app must come from the museum's established collection database and remain aligned with the gallery's current exhibit content.  
  **Source:** Monnig Meteorite Gallery project brief and database integration requirement, 2026.
- **`BR-full-collection-search`:** Visitors may search and filter the full meteorite collection, not just the artifacts currently on display in a single room or exhibit area.  
  **Source:** Monnig Meteorite Gallery vision and scope, 2026.
- **`BR-read-only-content`:** Visitor-facing museum content is treated as largely read-only, with revisions tied to the museum's catalog and exhibit updates rather than routine visitor-generated changes.  
  **Source:** Monnig Meteorite Gallery vision and scope, 2026.

### 2.3 Release and Product Priorities

- **`BR-mobile-platforms`:** The app must be available to visitors on both iOS and Android devices so that the museum can serve the broadest possible audience.  
  **Source:** Monnig Meteorite Gallery vision and scope and target deployment goals, 2026.
- **`BR-core-before-interactive`:** The first release must prioritize accessibility, exhibit information, search across the collection, and multilingual support before later interactive features such as scavenger hunts, quizzes, and location-based experiences.  
  **Source:** Monnig Meteorite Gallery MVP scope and product priorities, 2026.

## Revision History

| Date | Version | Description | Author |
|---|---|---|---|
| 2026-10-28 | 0.1 | Initial business rules for the Monnig Meteorite Gallery app | Team 06 - Koen Dolezar |
