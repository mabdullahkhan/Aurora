# AURORA — Adaptive Unified Risk Observation & Response Assistant

**Tagline:** Turn health signals into mission-ready action.

AURORA is an offline-first astronaut self-assessment and explainable decision-support prototype. It combines routine health indicators, symptom reports, personal-baseline trends, and spaceflight context to create a clear next-step card and a structured handoff for the crew medical officer / flight surgeon.

## Run the prototype

1. Extract this package.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox or Safari).
3. Use the Daily self-assessment panel and select example symptoms.
4. Press **Generate health check summary**.
5. Export the illustrative handoff as a `.txt` file.

No server, API key, account, or external JavaScript library is required for the static demonstration.

## What's implemented

- Responsive mission-health dashboard.
- Offline-capable static demonstration: the page and interaction logic run locally without an account or server; the demo does not persist health records between sessions or implement encrypted synchronization.
- Illustrative heart rate, blood pressure, glucose, temperature, sleep and mood cards.
- Seven-day illustrative sleep trend.
- Interactive symptom checklist with a basic non-diagnostic rule-template response.
- Urgent escalation copy for selected emergency symptoms (the mission's actual emergency procedure always takes precedence).
- Exportable structured handoff text.
- NASA evidence cards and source links.
- Five-hazard mission context panel.
- A small historical NASA RadLab CSV excerpt at `data/radlab_iss_sample.csv`.

## NASA data use and limitations

Read `docs/NASA_DATA_MANIFEST.md` for dataset-level provenance and caveats. The RadLab CSV contains a verified historical ISS instrument-data excerpt in μGy/hour. The prototype vital signs, symptom profile, and sleep chart are synthetic and are clearly labelled as demo data. The NASA OSDR studies are referenced as research evidence/integration candidates; raw transcriptomic, cytokine or biospecimen analysis is not implemented in this short prototype.

## Super Intelligence disclosure

ChatGPT assisted the project preparation process with ideation, research synthesis, and drafting of the submission kit and demo materials. The browser prototype itself uses deterministic JavaScript response templates; it does not call a live language model or send health data to an external AI service. The team should verify every source and statement before submission.

## What this is not

- Not a certified medical device.
- Not a diagnostic system or clinical risk predictor.
- Not connected to actual astronaut medical records, spacecraft sensors, wearable devices, or live NASA mission telemetry.
- Not a substitute for the crew medical officer, flight surgeon, or mission-specific medical protocols.
- The demo's thresholds and alert rules are illustrative templates only; production rules must be configured and validated by qualified aerospace medical personnel.

## Suggested production architecture

- Front end: offline-capable Progressive Web App (PWA).
- Local data layer: encrypted local database with an auditable event log and a store-and-forward sync queue.
- Integrations: approved wearable/medical device adapters; NASA OSDR metadata/file APIs; RadLab and EDA feeds where mission/time matching is supported.
- Analytics: baseline deviation and trend calculations, plus transparent configurable medical rules.
- SI/AI layer: constrained retrieval-augmented natural-language explanation and handoff drafting only; never sets alert severity, diagnoses, or prescribes medication.
- Governance: clinician-owned thresholds, role-based access, encryption, consent, retention controls, validation and human review.

## Files

- `index.html` — working browser prototype.
- `data/radlab_iss_sample.csv` — historical NASA RadLab excerpt.
- `docs/NASA_DATA_MANIFEST.md` — source descriptions, provenance and caveats.
- `AURORA_Submission_Kit.docx` — detailed project submission document (provided separately).
- `AURORA_7_Slide_Demo.pptx` — exactly seven demo slides.
- `AURORA_Dashboard_Screenshot.png` — full-page prototype screenshot suitable for the project page image field (review and replace after final team branding).

## Before public submission

1. Replace the team-name and member-name placeholders in the slide deck.
2. Put this folder in a public GitHub repository or deploy the site to a public static host.
3. Test the public website and repository links in a private/incognito browser.
4. Upload the seven-slide deck to a public file host (or include it in the repository) and paste its public URL into the Project Demo field.
5. Add a short screen recording or screenshots only as supplementary material; do not replace the required 7-slide/30-second demo.
6. Check the challenge's own Resources tab and list the exact resource(s) used there, alongside the NASA sources in this manifest.
7. Do not claim live sensor, live NASA feed, clinical validation, or AI diagnosis unless your team actually implements and verifies it.
8. Submit the NASA Space Apps form before the deadline shown for your Local Event.

## Attribution

AURORA is an independent hackathon prototype. NASA, OSDR, RadLab and the Human Research Program are cited as data/research sources; this project is not endorsed by NASA. Do not add NASA insignia or imply NASA endorsement.
