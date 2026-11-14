# AURORA — NASA data and evidence manifest

**Data handling principle:** NASA research datasets are used as scientific context and traceable evidence. They are not treated as an individual astronaut's real-time clinical baseline, and they are not represented as a validated diagnostic or predictive model.

| Source | What it contains | AURORA use | Important limitation |
|---|---|---|---|
| NASA Human Research Roadmap, Risk 85 | Evidence and mitigation framing for altered immune response | Defines immune-risk explanation cards and symptom-assessment pathway | Risk evidence is not a patient-specific diagnosis or a clinical threshold table |
| NASA HRR Task 1564, Functional Immune | ISS work integrating immune dysregulation with nutrition, radiation, virology, host-pathogen factors and stress | Supports multi-hazard context and the need for integrated monitoring | Research task description, not a released real-time clinical feed |
| NASA HRR Task 2670, Immunology Biomarkers — Artemis | Planned/active deep-space monitoring of saliva/dry-blood cytokines, antimicrobial proteins, stress hormones, latent herpesvirus DNA and BDNF | Informs the future biomarker panel design | A research plan; do not imply these tests are deployed in the prototype or available as consumer sensors |
| OSDR OSD-575 | Inspiration4 human serum, immune/cardiac cytokine multiplex assays and comprehensive metabolic panel; preflight and postflight timepoints | Human spaceflight biomarker evidence card and future dataset ingestion candidate | Small four-person commercial mission, short duration; samples described are preflight/postflight, so it is not a longitudinal deep-space validation set |
| OSDR OSD-656 | Inspiration4 urine inflammatory panel; 203 inflammatory, cytokine and chemokine proteins quantified; preflight and recovery timepoints | Urine biomarker evidence card and future ingestion candidate | Research biospecimens; no direct consumer-health threshold or diagnostic interpretation |
| OSDR OSD-280 | Salivary microbiome sequencing from 10 male astronauts, with preflight, in-flight and postflight samples | Supports research context around saliva/microbiome and potential association with viral reactivation | Microbiome study; it is not a direct clinical viral test and the study does not establish causation |
| NASA RadLab API | Radiation instrument telemetry including absorbed dose rate in μGy/hour, dose-equivalent rate in μSv/hour, flux, timestamp and some location fields | Provides historical ISS radiation-context series; CSV sample in this package | Archived instrument telemetry is not an astronaut's personal absorbed dose and is not a live feed for the user's mission |
| NASA Environmental Data App | ISS mission environmental measurements such as temperature, relative humidity, CO₂ and radiation data | Environmental context layer and source link | Historical mission/hardware context; requires matching mission/time and correct sensor provenance |

## Verified RadLab excerpt

The included `data/radlab_iss_sample.csv` transcribes five rows from this NASA RadLab API query:

https://visualization.osdr.nasa.gov/radlab/api/?spacecraft=ISS&instrument=DosTel&timestamp%3E=2022-04-01T23%3A00&timestamp%3C2022-04-02T01%3A05&absorbed_dose_rate%3E2&flux&latitude&longitude&altitude&b&l&format=html

The sample demonstrates two DosTel instrument readings at 2022-04-01 23:00:00: 9.815504 and 10.2160856667 μGy/hour. These are historical instrument readings. They must not be presented as current or crew-specific dose values.

## NASA source URLs

- Risk 85: https://humanresearchroadmap.nasa.gov/Risks/risk.aspx?i=85
- Functional Immune task: https://humanresearchroadmap.nasa.gov/tasks/task.aspx?i=1564
- Artemis saliva and dry-blood biomarker task: https://humanresearchroadmap.nasa.gov/tasks/task.aspx?i=2670
- OSD-575: https://osdr.nasa.gov/bio/repo/data/studies/OSD-575
- OSD-656: https://osdr.nasa.gov/bio/repo/data/studies/OSD-656
- OSD-280: https://osdr.nasa.gov/bio/repo/data/studies/OSD-280
- OSDR API documentation: https://api.nasa.gov/
- RadLab overview: https://visualization.osdr.nasa.gov/radlab/gui/overview/
- RadLab API documentation: https://visualization.osdr.nasa.gov/radlab/gui/data-api/
- Environmental Data App: https://visualization.osdr.nasa.gov/eda/
- NASA OSDR overview: https://science.nasa.gov/biological-physical/data/osdr/
- NASA sleep risk: https://www.nasa.gov/reference/risk-from-inadequate-sleep-and-irregular-schedules/

## Data provenance note

The dashboard's current vital-sign values and symptom scenario are synthetic demonstration values. The historical radiation excerpt is NASA RadLab data. OSDR records are cited as research evidence and integration candidates; the prototype does not claim to have parsed or trained on their raw omics/biospecimen files.
