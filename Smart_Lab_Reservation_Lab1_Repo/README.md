# Smart Lab Equipment & Slot Reservation Portal — Lab 1

**Course:** Requirements Engineering & UML Use-Case Modelling  
**Institution:** PES University, Department of CSE  
**Problem Statement:** #01 — Campus & Academic Operations

## Project overview
A requirements and UML modelling submission for a portal that prevents double-booking of high-value laboratory equipment, checks calibration status, supports reservations, and records late returns for disciplinary review.

## Repository contents
- `docs/Requirements_Table.xlsx` — editable requirements table (exactly 5 FRs and 2 NFRs).
- `docs/Requirements_Table.docx` — formatted Word version of the requirements.
- `docs/Use_Case_Flow.docx` — editable one-page use-case flow specification.
- `docs/Use_Case_Flow.pdf` — exported one-page use-case flow.
- `diagrams/Use_Case_Diagram.pdf` — UML use-case diagram export.
- `diagrams/use_case_diagram.drawio` — editable diagram for diagrams.net (draw.io).
- `diagrams/use_case_diagram.puml` — PlantUML source of the use-case model.

## Actors
1. **Student** — views equipment, reserves calibrated equipment, and views/cancels their reservations.
2. **Lab Technician** — updates calibration records, records equipment returns, and reviews late-return flags.
3. **University Identity Provider** — supporting external actor for authentication.

> **Modelling assumption:** The scenario names Student and Lab Technician as its target stakeholders. The handout separately asks for at least three actors. The University Identity Provider is therefore introduced as an explicit supporting actor assumption; it is not stated in the problem scenario.

## Core business rules
- A student must be authenticated to reserve equipment.
- Only calibrated equipment may be reserved.
- Reservations may be made up to 7 days in advance.
- A reservation may not exceed 2 hours.
- A successful reservation produces a unique reservation token.
- Overlapping reservations for the same equipment must not be accepted.
- Returns later than the scheduled end time are flagged for technician review.

## UML relationships
- `Reserve Calibrated Equipment` **includes** authentication, calibration-status check, and slot-availability check.
- `Flag Late Return` **extends** `Record Equipment Return` when the actual return time is later than the scheduled end time.
- `Review Late Return Flag` includes the late-return flag review action.

## Requirement traceability
- FR-001 preserves the instructor's sample reservation requirement.
- NFR-001 preserves the instructor's sample performance and database-isolation requirement.
- FR-002 to FR-005 and NFR-002 are derived from the scenario context and are phrased as testable requirements.

## How to view/edit the diagram
Open `diagrams/use_case_diagram.drawio` at https://app.diagrams.net/ or import the `.puml` file into a PlantUML-compatible renderer. The PDF is the ready-to-submit export.

## Submission checklist
- [ ] Verify student name / SRN if your instructor requires them.
- [ ] Review the explicit third-actor assumption with your instructor if necessary.
- [ ] Upload this repository to your GitHub account.
- [ ] Confirm the PDF and editable source files are visible in the repository.
