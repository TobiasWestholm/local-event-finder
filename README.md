# Event Scanner

An agent skill for discovering, scoring, and shortlisting local events matched to your taste profile.

Supports optional Google Calendar integration for availability checks and adding events.

## How to install

There are two ways to use this skill:

**As a standalone project** — clone this repo and open the folder in your coding agent. The agent reads `CLAUDE.md` or `AGENTS.md` at the root and is ready to scan immediately after setup.

**As a skill in an existing project** — copy the `skills/event-scanner/` folder into your project's `skills/` directory. Your agent will pick it up automatically. No other files from this repo are needed.

## Setup

Once installed, send the prompt below to your agent. Replace the `FILL IN` placeholders with your actual preferences before sending.

```text
Set up the event scanner skill for me.

First, create my personal configuration files by copying the example files in skills/event-scanner/assets/:
- Copy taste-profile.example.md to taste-profile.md in the same folder
- Copy sources.example.md to sources.md in the same folder

Then replace the <PLACEHOLDER> blocks in both copied files with my preferences below.

Interests to add to my taste profile:
- (FILL IN: eg ceramics, techno, traveling, italian wines, DIY, ...)

Dealbreakers to add:
- (FILL IN: eg age restrictions, audience restrictions, fully booked events, ...)

Default location: (FILL IN: eg your home city)

Primary sources for my default location:
- (FILL IN, optional: URLs where you usually find good local events)

Optional additional location: (FILL IN, optional: eg your work city)
- (FILL IN, optional: sources for that location)

Optional: install the Google Calendar tool so the scanner can check availability and add events when I ask.

Optional: set up a weekly automation that runs every Monday at 09:00 and finds events for the coming week.
```

## Usage

Just ask your agent for event suggestions. Examples:

- *"What's on in Copenhagen this weekend?"*
- *"Find me AI events in the next two weeks."*
- *"Any good things to do in Paris this summer?"*

The agent will invoke the `event-scanner` skill, run discovery and scoring, and return a ranked shortlist with source links and caveats. Scan results are saved to `skills/event-scanner/runs/`.

To add a shortlisted event to your calendar, tell your agent explicitly: *"Add X to my calendar."*
