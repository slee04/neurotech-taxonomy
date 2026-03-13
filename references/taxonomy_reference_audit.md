# Neurotechnology Database — Audit Against Reference Taxonomy

*Created: 2026-02-25*
*Purpose: Compare current `neurotech_database.yaml` (24 technologies) against the reference taxonomy in `neurotechnology_definition_and_taxonomy.md` and identify required changes.*

---

## Current database: neurotech_database.yaml

24 technologies (NT001–NT024) in 3 categories: Sensing (13), Modulation (6), Integrated Systems (5).

---

## 1. Technologies to KEEP (well-supported, no changes needed)

| ID | Technology | Category | Status |
|---|---|---|---|
| NT001 | EEG | Sensing / Electrophysiology | Supported by Cinel 2019, NIHR 2024, Nuffield 2024 |
| NT002 | MEG | Sensing / Electrophysiology | Supported by Cinel 2019 |
| NT003 | ECoG | Sensing / Electrophysiology | Supported by Cinel 2019 |
| NT004 | Intracortical microelectrode arrays | Sensing / Electrophysiology | Supported by Cinel 2019 |
| NT005 | fMRI | Sensing / Hemodynamic | Supported by Cinel 2019 |
| NT006 | fNIRS | Sensing / Hemodynamic | Supported by Cinel 2019 |
| NT014 | TMS | Modulation / Non-invasive | Supported by Cinel 2019, NIHR 2024, Nuffield 2013/2024 |
| NT016 | Focused ultrasound (FUS) | Modulation / Non-invasive | Supported by Cinel 2019, NIHR 2024 |
| NT017 | DBS | Modulation / Invasive | Supported by Cinel 2019, NIHR 2024, Nuffield 2013/2024 |
| NT018 | VNS | Modulation / Invasive | Supported by Nuffield 2024 |
| NT020 | Invasive motor BCI | Integrated / BCI | Supported by NIHR 2024, Nuffield 2013/2024 |
| NT021 | Non-invasive BCI | Integrated / BCI | Supported by NIHR 2024, Nuffield 2024 |
| NT022 | Neurofeedback | Integrated / Neurofeedback | Widely recognised, consumer market growing |
| NT023 | Motor neuroprosthetics | Integrated / Neuroprosthetics | Supported by Nuffield 2024 |
| NT024 | Sensory neuroprosthetics | Integrated / Neuroprosthetics | Supported by Nuffield 2024 |

**15 technologies — no action needed.**

---

## 2. Technologies to MODIFY

| ID | Technology | Current state | Required change | Rationale |
|---|---|---|---|---|
| NT015 | tDCS | Listed as standalone | Rename to **"Transcranial Electrical Stimulation (tES)"** covering tDCS, tACS, tRNS as subtypes | Cinel 2019 lists tDCS and tACS separately; grouping as tES family is cleaner since TIPSS profiles are similar. Avoids needing a separate tACS entry. |
| NT007 | PET | Listed under Sensing / Hemodynamic | Add `neuro.claim: neuro.claim.proxy_inference` and note in entry that this is a borderline inclusion | Reference taxonomy classifies as borderline. NIHR excludes. Included for TIPSS relevance (predictive biomarkers). |
| NT008 | SPECT | Listed under Sensing / Hemodynamic | Same as PET | Same reasoning. |
| NT012 | Eye tracking | Listed under Sensing / Neural Proxy | Add `neuro.claim: neuro.claim.proxy_inference` (already has `neuro.target.neural_proxy`) | Not neurotech by published definitions. Included for TIPSS relevance in convergent systems. |
| NT013 | Facial EMG / emotion recognition | Listed under Sensing / Neural Proxy | Same as eye tracking | Same reasoning. |
| NT019 | Optogenetics | Listed under Modulation / Invasive | No structural change, but add note: "Pre-clinical only. Included for forward-looking TIPSS analysis." | No human deployment outside retinal trials. Acknowledged by sources as frontier technology. |

**6 technologies — minor modifications.**

---

## 3. Technologies to REMOVE

| ID | Technology | Current category | Reason for removal |
|---|---|---|---|
| NT009 | Structural MRI | Sensing / Structural | Images brain structure, not neural activity. Not neurotechnology by any published definition. Out of scope per reference taxonomy. |
| NT010 | CT | Sensing / Structural | Structural/acute imaging. Same reasoning. |
| NT011 | DTI | Sensing / Structural | Maps white matter structure, not activity. Same reasoning. |

**3 technologies to remove. Entire "Structural/Anatomical" subcategory eliminated.**

> **Note:** These technologies may still appear in the RER corpus (papers discussing brain imaging in a TIPSS context). They don't need database entries — they're part of the broader neuroimaging ecosystem but are not neurotechnologies. If needed, they can be referenced as contextual technologies without ontology entries.

---

## 4. Technologies to ADD

| Proposed ID | Technology | Category | Rationale | TIPSS relevance |
|---|---|---|---|---|
| NT025 | **Electroconvulsive therapy (ECT)** | Modulation / Non-invasive | Included by Cinel 2019. Unambiguously a neurotechnology (electrical brain stimulation). Major omission from current database. | Coercion/consent history, safety, identity/memory effects, stigma. One of the most ethically charged neurotechnologies. |
| NT026 | **Spinal cord stimulation (SCS)** | Modulation / Invasive | Major clinical neuromodulation technology (~50,000 implants/year). VNS already included — excluding SCS is inconsistent. | Consent, safety, device dependence, data from implanted systems. |

**2 technologies to add.**

> **Deferred:** TPS (transcranial pulse stimulation) — emerging, small evidence base. Can note under FUS entry as variant. Peripheral nerve stimulation (beyond VNS and SCS) — could be added later if scope expands.

---

## 5. Summary of changes

| Action | Count | Details |
|---|---|---|
| Keep as-is | 15 | NT001–006, NT014, NT016–018, NT020–024 |
| Modify | 6 | NT007, NT008, NT012, NT013, NT015, NT019 |
| Remove | 3 | NT009, NT010, NT011 |
| Add | 2 | NT025 (ECT), NT026 (SCS) |
| **New total** | **23** | Down from 24 (removed 3, added 2) |

### Resulting database structure

```
Sensing (10)
├── Electrophysiology: EEG, MEG, ECoG, microelectrode arrays
├── Hemodynamic/Metabolic: fMRI, fNIRS, PET*, SPECT*
└── Neural Proxy: eye tracking*, facial EMG*
    (* = borderline, tagged neuro.claim.proxy_inference)

Modulation (7)
├── Non-invasive: TMS, tES (tDCS/tACS/tRNS), FUS, ECT [NEW]
└── Invasive: DBS, VNS, SCS [NEW], optogenetics

Integrated Systems (5)
├── BCI: invasive, non-invasive
├── Neurofeedback
└── Neuroprosthetics: motor, sensory
```

---

## 6. Downstream impact

Changes to the database will need to propagate to:

| Downstream artifact | What changes |
|---|---|
| `neurotech_database.yaml` | Apply all changes above |
| `neurotech_database.xlsx` | Mirror YAML changes |
| `neurotech_ontology_v0.yaml` | No change needed — ontology dimensions already support all modifications |
| RER search strategy (`search_strategy.md`) | Add ECT and SCS search terms; remove structural MRI/CT/DTI terms if present |
| RER screening criteria | Confirm structural imaging papers are excluded or handled as context |
| Corpus landscape analysis (`corpus_landscape.py`) | Update modality keyword dictionaries to match revised database |
| Protocol (`rer_protocol_v1.md`) | Update neurotech scope definition to reference `neurotechnology_definition_and_taxonomy.md` |

---

## 7. Decisions for Sieun

- [ ] **Confirm removal** of structural MRI, CT, DTI (NT009–011)
- [ ] **Confirm borderline tagging** of PET, SPECT, eye tracking, facial EMG
- [ ] **Confirm addition** of ECT (NT025) and SCS (NT026)
- [ ] **Confirm tES grouping** (rename NT015 from tDCS to tES family)
- [ ] **Confirm scope boundary** on peripheral nerve stimulation beyond VNS/SCS — include or defer?
