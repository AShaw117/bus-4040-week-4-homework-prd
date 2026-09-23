# PRD: CBE Event Schedule/Agenda Database & Builder

## Problem Statement

CBE program coordinators currently build event schedules/agendas for three recurring
energy-sector programs (Energy Executive Course, Energy Executive Summit, Legislative
Energy Horizon Institute) by manually creating Word/PDF documents, broken into days and
time blocks. Because different people have created these over 2016-2026, formats have
drifted, making it slow and error-prone to build a new schedule from past ones and
difficult to search or reference past events. CBE needs a centralized, standardized
system for storing this historical data and assembling new schedules from it.

## Goals

1. **Primary: Faster, easier new-schedule creation.** A coordinator can assemble a new
   multi-day event agenda by drawing on standardized past data (sessions, speakers, time
   blocks) instead of manually recreating one from scratch or copy-pasting an old file.
2. **Full historical migration.** All event data from 2016-2026 is uploaded and
   converted into the standardized format - not just new events going forward.
3. **One standard format, no exceptions.** Every event, regardless of program
   (Course/Summit/Institute) or original source format (Word/PDF), is stored under a
   single consistent schema.
4. **Time/structure-focused analysis.** Session runtimes and time allocation across
   topics/blocks, trackable across years - not attendee engagement (no such data exists
   in the sources).
5. **Open/pending client input:** whether the builder outputs a from-scratch canvas or a
   standardized fill-in-the-blank template, and whether the database or the builder is
   the higher client priority (see client questions 7-8).

## Constraints

1. **Must ingest inconsistent legacy formats.** Source data arrives as Word docs and
   PDFs with formats that drifted across 2016-2026 (different structures, terminology,
   levels of detail) - the product must be able to accommodate/convert that into one
   schema.
2. **Must model multi-day, time-blocked events.** The data structure has to represent
   events spanning multiple days, each broken into time blocks, and handle drift in how
   those blocks are described.
3. **No privacy/security constraints.** All data is public, so no access control,
   encryption, or PII handling requirements.
4. **Usable by non-technical staff.** The primary user is a program coordinator, not a
   developer - so the product can't require code/scripting to operate day-to-day (add,
   edit, search, build a schedule).
5. **Small-scale, low-concurrency.** Realistically one user at a time, not built for
   public access or simultaneous multi-editor use.
6. **Open/unknown, pending more info:**
   - Whether the course/project requires a specific platform or tool.
   - Whether the final schedule needs to be exported to Word/PDF for distribution, or
     stays digital/in-app only.
   - Whether concurrent editing (e.g., two people editing different events at once)
     needs to be supported.

## Target Users / Personas

- **Program Coordinator** (primary and, for now, only known user) - manages schedules
  for all three CBE programs. Not highly technically capable; comfortable with everyday
  office documents (Word/PDF) but not databases or code. Owns the full workflow: looking
  up past events, entering/editing records, and building new event schedules.

## User Stories

*(Draft - presented for review, not yet fully confirmed)*

1. As the coordinator, I want to **enter a past event's schedule into a standard
   format** so that all historical events (2016-2026) live in one consistent structure.
2. As the coordinator, I want to **add, edit, or delete a session/speaker/time-block
   record** so that I can fix mistakes or update details without recreating the whole
   event.
3. As the coordinator, I want to **search past events** (by program, year, speaker, or
   topic) so that I can quickly find precedent when planning.
4. As the coordinator, I want to **build a new multi-day event schedule** by pulling
   from past sessions/speakers/structure, so that I don't have to start from a blank
   page every time.
5. As the coordinator, I want to **back up and restore the data** so that I don't lose
   years of historical records to a mistake or crash.
6. As the coordinator, I want to **see basic analysis** (e.g., how time is allocated
   across topics, session runtimes over the years) so that I can spot patterns when
   planning future events.

## Functional Requirements

*(TBD - to be derived from the User Stories above once confirmed)*

## Out of Scope

*(TBD)*

---

## Open Questions for Client

See [PRD-client-questions.md](PRD-client-questions.md) for the running list of
questions to ask the program coordinator.
