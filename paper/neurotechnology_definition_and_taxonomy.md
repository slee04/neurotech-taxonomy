# Neurotechnology: Definition, Scope, and Taxonomy

*Working document. Last updated: 2026-02-25.*
*Purpose: Establish a defensible, reference-grounded foundation for what counts as neurotechnology and how to classify it. This document supports the NeuroCET-TIPSS ontology, database, and RER.*

---

## 1. Definition

### 1.1 Published definitions

| Source | Definition |
|---|---|
| OECD (2019) | "Devices and procedures used to access, monitor, investigate, assess, manipulate, and/or emulate the structure and function of the neural systems of natural persons." |
| Yuste et al. (2017) | "Methods or devices or tools to record or change brain activity." |
| UNESCO (2025) | Technologies that "interact with the brain and central nervous system" for medical and non-medical purposes. |
| Nuffield Council (2013) | Technologies that "intervene in the brain" — specifically those that record brain activity, stimulate the brain, or both. |
| Ienca & Andorno (2017) | Technologies for "recording and decoding brain activity" and "stimulating or modulating brain activity." |

### 1.2 Working definition for this project

> **Neurotechnology** is any device, system, or method that directly interfaces with the nervous system to record, monitor, stimulate, or modulate neural activity, or that uses neural signals as input for computation, communication, or control.

This definition:
- **Includes** devices that record neural activity (EEG, fMRI, ECoG, etc.)
- **Includes** devices that stimulate or modulate neural activity (TMS, tDCS, DBS, etc.)
- **Includes** integrated systems that do both (BCIs, neurofeedback, neuroprosthetics)
- **Includes** consumer and non-medical applications, not just clinical
- **Excludes** technologies that image brain structure without measuring neural activity (structural MRI, CT)
- **Requires judgment** for technologies that infer neural states indirectly (eye tracking, facial EMG) — these are "neural proxies" and are treated as borderline

This aligns with the OECD definition (broadest and most authoritative) while remaining operationally specific.

---

## 2. Taxonomy

### 2.1 Classification framework

The taxonomy uses two primary axes, following Cinel et al. (2019):

**Axis 1 — Function:**
- **Sensing/Recording:** Technologies that detect, measure, or image neural activity
- **Modulation/Stimulation:** Technologies that alter, stimulate, or modulate neural activity
- **Integrated:** Systems that combine sensing and modulation in a functional loop (e.g., BCIs, neurofeedback, closed-loop stimulation)

**Axis 2 — Invasiveness** (Cinel et al. 2019; OECD 2019):
- **Non-invasive:** No breach of the body's surface (e.g., EEG, TMS, fNIRS)
- **Minimally invasive:** Temporary or minor intrusion (e.g., radiotracer injection for PET; transcutaneous VNS)
- **Invasive:** Surgical implantation or penetration of neural tissue (e.g., DBS, ECoG, intracortical arrays)

Additional classification dimensions (per Cinel et al. 2019; our ontology):
- **Mechanism:** Electrical, magnetic, optical, acoustic, chemical
- **Interface target:** Brain, peripheral nervous system, neural proxy
- **Maturity:** Experimental → clinical trial → approved (limited) → approved (broad) → consumer
- **Spatial and temporal resolution**
- **Portability**

### 2.2 Technology inventory

#### Sensing / Recording

**Electrophysiology** — recording electrical or magnetic signatures of neural activity

| Technology | Mechanism | Invasiveness | Maturity | Key references |
|---|---|---|---|---|
| **Electroencephalography (EEG)** | Electrical | Non-invasive | Approved (broad), Consumer | Cinel 2019; NIHR 2024; Nuffield 2024 |
| **Magnetoencephalography (MEG)** | Magnetic | Non-invasive | Approved (limited) | Cinel 2019 |
| **Electrocorticography (ECoG)** | Electrical | Invasive | Approved (limited) | Cinel 2019 |
| **Intracortical microelectrode arrays** | Electrical | Invasive | Experimental / Clinical trial | Cinel 2019 |

**Hemodynamic / Metabolic imaging** — recording neural activity via blood flow or metabolic correlates

| Technology | Mechanism | Invasiveness | Maturity | Key references |
|---|---|---|---|---|
| **Functional MRI (fMRI)** | Magnetic (BOLD) | Non-invasive | Approved (broad) | Cinel 2019 |
| **Functional near-infrared spectroscopy (fNIRS)** | Optical | Non-invasive | Approved (limited), Consumer | Cinel 2019 |
| **Positron emission tomography (PET)** | Chemical (radiotracer) | Minimally invasive | Approved (broad) | — (see note 1) |
| **Single-photon emission CT (SPECT)** | Chemical (radiotracer) | Minimally invasive | Approved (broad) | — (see note 1) |

> **Note 1 — PET and SPECT:** These measure metabolic activity and receptor binding rather than real-time neural activity. NIHR (2024) explicitly excludes standard imaging modalities. They are included here because they can reveal neural function (e.g., dopamine activity in Parkinson's, amyloid burden in Alzheimer's) and have TIPSS implications (predictive biomarkers, incidental findings, insurance discrimination). Their inclusion is a project scope decision — they sit at the boundary. In the ontology, they should be tagged `neuro.claim.proxy_inference` or `scope.borderline`.

#### Modulation / Stimulation

**Non-invasive stimulation**

| Technology | Mechanism | Target | Maturity | Key references |
|---|---|---|---|---|
| **Transcranial magnetic stimulation (TMS)** | Magnetic | Brain (cortex) | Approved (broad) | Cinel 2019; NIHR 2024; Nuffield 2013, 2024 |
| **Transcranial electrical stimulation (tES)** — includes tDCS, tACS, tRNS | Electrical | Brain (cortex) | Approved (limited), Consumer | Cinel 2019; NIHR 2024 |
| **Focused ultrasound neuromodulation (FUS/TUS)** | Acoustic | Brain (cortical + deep) | Experimental / Clinical trial | Cinel 2019; NIHR 2024 |
| **Electroconvulsive therapy (ECT)** | Electrical | Brain (global) | Approved (broad) | Cinel 2019 |
| **Transcranial pulse stimulation (TPS)** | Acoustic | Brain | Experimental | NIHR 2024 |

> **Note 2 — tES family:** Cinel et al. (2019) list tDCS and tACS as separate technologies under transcranial electrical stimulation (tES). The family also includes transcranial random noise stimulation (tRNS). For this project, grouping them as "tES" with subtypes is cleaner than separate entries, since their TIPSS profiles are similar.

> **Note 3 — ECT:** Although old and well-established, ECT is unambiguously a neurotechnology (electrical brain stimulation) with significant TIPSS implications: coercion/consent history, safety, identity/memory effects, stigma. Its omission from a neurotech-TIPSS taxonomy would be a notable gap.

**Invasive stimulation**

| Technology | Mechanism | Target | Maturity | Key references |
|---|---|---|---|---|
| **Deep brain stimulation (DBS)** | Electrical | Brain (subcortical nuclei) | Approved (broad) | Cinel 2019; NIHR 2024; Nuffield 2013, 2024 |
| **Vagus nerve stimulation (VNS)** | Electrical | Peripheral (vagus nerve) | Approved (broad), Consumer (transcutaneous) | Nuffield 2024 |
| **Spinal cord stimulation (SCS)** | Electrical | Spinal cord | Approved (broad) | — (see note 4) |
| **Peripheral nerve stimulation (PNS)** | Electrical | Peripheral nerves | Approved (limited to broad) | — (see note 4) |
| **Optogenetics** | Optical + chemical (gene therapy) | Brain (cell-type specific) | Experimental | Cinel 2019 (acknowledged) |

> **Note 4 — SCS and PNS:** These are established clinical neuromodulation technologies (~50,000 SCS implants/year globally). VNS is already included as a peripheral nerve technology; SCS and broader PNS are the same modality class targeting different nerves. Including VNS but excluding SCS creates an inconsistent boundary. However, if the project scope is restricted to brain-targeting technologies, these would be excluded. This is a scope decision.

#### Integrated Systems

| Technology | Function | Invasiveness | Maturity | Key references |
|---|---|---|---|---|
| **Invasive motor BCI** | Sensing + control output | Invasive | Clinical trial | NIHR 2024; Nuffield 2013, 2024; Yuste 2017 |
| **Non-invasive BCI** | Sensing + control output | Non-invasive | Approved (limited), Consumer | NIHR 2024; Nuffield 2024 |
| **Neurofeedback** | Sensing + real-time feedback | Non-invasive | Approved (limited), Consumer | — |
| **Motor neuroprosthetics** | Sensing + motor actuation | Invasive to non-invasive | Clinical trial to approved | Nuffield 2024 |
| **Sensory neuroprosthetics** (cochlear implant, retinal implant) | Stimulation → sensory perception | Invasive | Approved (broad) to clinical trial | Nuffield 2024 |

---

## 3. Scope boundaries

### 3.1 Clearly in scope

Technologies that directly interface with the nervous system to record or modulate neural activity. All technologies listed in Section 2.2 without boundary notes.

### 3.2 Borderline — included with justification

| Technology | Why borderline | Why included | Recommended tag |
|---|---|---|---|
| **PET / SPECT** | Metabolic imaging, not real-time neural activity. Excluded by NIHR. | Measures neural function (receptor binding, metabolism). TIPSS-relevant (predictive biomarkers, discrimination). | `neuro.claim.proxy_inference` |
| **Eye tracking** | Not a neural interface. No published neurotech taxonomy includes it. | Infers cognitive states (attention, intent, fatigue) from oculomotor behaviour. Core component of consumer neurotechnology convergence (VR headsets, driver monitoring). Among the most TIPSS-relevant sensing technologies in the consumer space. | `neuro.claim.proxy_inference` + `neuro.target.neural_proxy` |
| **Facial EMG / emotion recognition** | Not a neural interface. No published neurotech taxonomy includes it. | Infers affective states from facial muscle activity or expressions. TIPSS-relevant (surveillance, profiling, bias). | `neuro.claim.proxy_inference` + `neuro.target.neural_proxy` |
| **Optogenetics** | No human deployment (except retinal). | Represents the frontier of neurotechnology with unique TIPSS profile (gene therapy + neural control). Important for forward-looking analysis. | `neuro.maturity.experimental` |

### 3.3 Out of scope

| Technology | Reason |
|---|---|
| **Structural MRI** | Images brain anatomy, not neural activity. Not a neurotechnology by any published definition. |
| **CT (head)** | Structural/acute imaging. Same reasoning. |
| **DTI / diffusion MRI** | Maps white matter structure, not activity. |
| **Neural stem cell therapies** | Biological intervention, not a device/interface technology. Included by Nuffield (2013) but conceptually different from device-based neurotech. |
| **Pharmaceuticals / psychopharmacology** | Chemical modulation of neural activity, but not device-based. Outside the technology scope. |
| **General biosensors** (heart rate, GSR, respiration) | Physiological sensing with no neural specificity, unless combined with neurotech in a convergent system. |

### 3.4 Justification for scope decisions

The scope boundary follows two principles:

1. **Neural specificity:** The technology must interface with, or make specific inferences about, the nervous system. General physiological sensors and structural imaging are excluded.
2. **TIPSS relevance as tiebreaker:** For borderline cases (PET, eye tracking, facial EMG), inclusion is justified when the technology raises distinctive TIPSS concerns that would be missed by excluding it — particularly where it appears in convergent consumer systems.

This is deliberately broader than some published taxonomies (which focus on brain activity recording and stimulation) but narrower than the broadest definitions (which could include any biomedical device). The broader scope is appropriate for a TIPSS-focused project because TIPSS risks often arise at the boundary — from technologies that *infer* rather than *directly read* neural states.

---

## 4. Organisational notes

### 4.1 Relationship to published frameworks

Our three-category organisation (Sensing / Modulation / Integrated) is an extension of Cinel et al.'s (2019) two-category scheme (Recording / Stimulation). The "Integrated Systems" category captures technologies that combine both functions in a closed loop — BCIs, neurofeedback, and neuroprosthetics. This is pragmatically useful because these systems have distinct TIPSS profiles (continuous neural data flow, real-time adaptation, user dependence).

### 4.2 Relationship to the ontology

Each technology maps to the ontology's neurotech facet dimensions:
- `neuro.claim` → direct / proxy_inference / none
- `neuro.target` → brain / peripheral_nervous_system / neural_proxy
- `neuro.interaction` → sensing / stimulation / bidirectional_closed_loop / hybrid_other
- `neuro.mechanism` → electrical / optical / magnetic / acoustic / chemical / other
- `neuro.invasiveness` → noninvasive / minimally_invasive / invasive
- `neuro.maturity` → experimental / clinical_trial / approved_limited / approved_broad / consumer

### 4.3 Why this matters

The taxonomy serves as the backbone for:
- **RER search strategy** — search terms derived from technology names and synonyms
- **RER screening** — determining whether a paper is about neurotechnology
- **Corpus landscape analysis** — tagging papers by neurotech modality
- **Extraction framework** — structuring evidence by technology type
- **Database** — each technology entry maps to ontology dimensions
- **Presentations and publications** — defensible when challenged on "what counts"

---

## 5. References

1. Cinel, C., Valeriani, D., & Poli, R. (2019). Neurotechnologies for human cognitive augmentation: Current state of the art and future prospects. *Frontiers in Human Neuroscience*, 13, 13. https://doi.org/10.3389/fnhum.2019.00013
2. NIHR Innovation Observatory (2024). Horizon scanning report: Neurotechnology for mental health, healthy ageing and physical disability. https://io.nihr.ac.uk/wp-content/uploads/2024/09/Neurotechnology-Report_Sept-2024.pdf
3. Nuffield Council on Bioethics (2013). Novel neurotechnologies: Intervening in the brain. https://www.nuffieldbioethics.org/publication/novel-neurotechnologies-intervening-in-the-brain/
4. Nuffield Council on Bioethics (2024). Neurotechnology literature review. https://cdn.nuffieldbioethics.org/wp-content/uploads/Neurotechnology-Literature-Review-Final.pdf
5. OECD (2019). Recommendation on responsible innovation in neurotechnology. https://www.oecd.org/content/dam/oecd/en/topics/policy-sub-issues/emerging-technologies/neurotech-toolkit.pdf
6. Yuste, R., et al. (2017). Four ethical priorities for neurotechnologies and AI. *Nature*, 551, 159-163. https://doi.org/10.1038/551159a
7. Ienca, M., & Andorno, R. (2017). Towards new human rights in the age of neuroscience and neurotechnology. *Life Sciences, Society and Policy*, 13, 5. https://doi.org/10.1186/s40504-017-0050-1
8. UNESCO (2025). Recommendation on the ethics of neurotechnology. https://www.unesco.org/en/ethics-neurotech
