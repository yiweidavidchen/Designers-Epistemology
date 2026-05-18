# Designers-Epistemology
A research mentorship framework for developing the designer's posture — understanding through inhabitation, theory through need, and learning through real stakes.

**For developing the designer's posture.**

> Understanding is not possession of facts. Understanding is the ability to make decisions under uncertainty within a problem space.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) 

Use freely with attribution.

---

## What This Is

Designer's Epistemology is a mentorship and research education framework built on a single premise: 

**The gap between knowing about a problem and inhabiting a problem is the gap between map-reading and navigation.**

Conventional education front-loads theory, then asks students to apply it. This framework inverts that order. The problem comes first. Theory is introduced at the moment a student needs it to move forward — not before, not after. Understanding is verified not by testing recall but by whether a student can construct a coherent narrative about their own decisions.

The framework emerged from direct experience in computational enzyme design research — specifically from the observation that the designer's posture (the ability to reason about a perturbation, anticipate outcomes, and reconstruct thinking when results are unexpected) cannot be transmitted through lectures. It has to be acquired through inhabitation of real problems with real stakes.

It applies to any domain structured around design under uncertainty. Enzyme engineering is the worked example here. The underlying architecture generalizes.

---

## Core Principles

### 1. Inhabitation over observation
The student must be *inside* the problem, not studying it from outside. They need skin in the game — a design they committed to, a hypothesis they defended, a choice they made that can be wrong. Observation produces knowledge about a problem. Inhabitation produces judgment.

### 2. Productive friction
Difficulty is the medium of learning, not an obstacle to it. The mentor's primary skill is calibrating discomfort — hard enough that the student has to think, not so hard that they can't find footing. The threshold is different for every student and every moment.

### 3. Just-in-time theory delivery
Theory is introduced when the student needs it to move forward. The problem creates the cognitive hook. The theory slots into a real question the student is already holding — and is therefore retained. Front-loaded theory, delivered before the need exists, is largely inert.

### 4. Narrative as verification
A student who understands something can construct a coherent causal story about it. Not recite facts — but explain why they made each decision, what they expected, what the result meant for their original reasoning, and where their model broke down. If the narrative breaks down, that is where understanding breaks down.

### 5. Theory as tool, not prerequisite
The mentor maintains a tiered resource map for each conceptual domain — entry point, working depth, deep dive — and deploys resources with a directed question rather than a lecture. The resource is given. The question is given. The understanding is not given.

---

## The Six Movements

These are not strictly linear. Students loop back. Different students move through them at different rates. The mentor tracks position, not pace.

---

### Movement I — Encounter
The student meets the raw problem without scaffolding.

The mentor presents a real problem — not a textbook version. For enzyme design: *here is a wild-type enzyme with a known function. Here is an application where you'd want something different. What would you do?*

The student is not expected to know. The point is to surface what they don't know, and to make them feel the shape of the problem — its constraints, moving parts, interconnected pressures. Let them feel the weight of genuine uncertainty. That is the data.

**Mentor's role:** Ask questions that expand the problem space. *What else would matter? Who else is affected? What could go wrong?*
No AI. No papers. Just the student's existing mental model exposed to the problem.

---

### Movement II — Self-directed search
The student goes and finds what humans have figured out.

They read papers. They search databases. They talk to people. They find failed experiments and successful ones. They build a map of existing knowledge — without AI assistance.

The friction is intentional. Reading primary literature is hard. Sources contradict each other. That difficulty forces source evaluation and active model-building. The student has to decide what to trust and what to integrate.

**Mentor's role:** Check in on what they found, not just what they learned. *Where did you look? What surprised you? What didn't make sense?* Redirect without answering.

**Deliverable:** A personal synthesis — not a literature review. A map: *here is what I now think I know, here is what is still unclear, here is what I think matters most.*

---

### Movement III — AI-augmented dialogue
The student uses AI as a thinking partner, not an answer machine.

They bring in AI now — but they come to it with their own model already formed. This is the critical difference. A student with no prior model receives answers they cannot evaluate. A student with a model gets a conversation — they can push back, notice gaps, test their reasoning against the AI's framing.

**Mentor's role:** Teach the student how to interrogate AI output. *Does that match what you found? Where does it diverge? Why might it be wrong?* Model this posture in early sessions.

**What to avoid:** Using AI to replace Movement II. If a student skips straight to AI, they skip the development of evaluative judgment. Their AI dialogue will be shallow and uncritical.

*Note: AI restriction in Movement II is conditional, not absolute. The operational test — can the student articulate why they would accept or question what the AI told them? If not, they went to AI too early.*

---

### Movement IV — Design under commitment
The student commits to a specific design with explicit reasoning.

They decide: which mutants, which substrates, which controls, which conditions, and why. They predict outcomes. They identify failure modes. They write down what each possible result would mean.

The commitment is the point. Not because they will be right — most first designs are partially wrong — but because committing forces precision. You cannot troubleshoot a vague intention. You can troubleshoot a specific choice.

**Mentor's role:** Do not correct bad designs in advance. Ask questions that expose the reasoning: *What would it mean if you saw no activity? What if activity exceeded wild-type? Have you considered whether the protein will fold?* Let them find weaknesses themselves where possible.

**Deliverable:** A reasoning document. Not a formal protocol — a thinking record. *What am I doing, why, and what do I expect?*

---

### Movement V — Execution and troubleshooting
The student does the work and encounters reality.

Things go wrong. Proteins misfold. Assays give unexpected results. Controls fail. A collaborator's data conflicts with yours. This is not a problem with the educational model — this *is* the educational model. The troubleshooting conversation is where the deepest learning happens.

**Mentor's role:** Shift from Socratic questioning to genuine collaborative thinking. You are now a peer with more experience, not a teacher with answers. *I don't know either — what would help us figure it out?* Share your own uncertainty. Model the designer's posture under failure.

**What to protect:** The student's ownership of the problem. Even when you know the answer, let them arrive at it.

---

### Movement VI — Narrative construction
The student builds the story that gives the work meaning.

What happened? What does it mean? Who cares, and why? How does this connect to bigger questions? What would you do differently? What does this open up?

This is not a presentation. It is a reckoning. The student reconciles what they expected with what happened and constructs a coherent account that does not paper over the gaps. A good narrative here is honest about failure and clear about what was learned.

**Mentor's role:** Push for causality — *why did that happen?* Push for significance — *why does this matter beyond the experiment?* Push for honesty — *what would you have done differently with hindsight?*

**Deliverable:** Format is flexible — poster, written report, peer talk, or a conversation with the mentor. Coherence of reasoning matters more than format.

---

## Theory Injection Map (BglB Worked Example)

The mentor maintains a mental or written map of conceptual domains the student will encounter, with resources at three depths and a directed question for each entry point.

Each entry follows the pattern:
> **Give the resource. Give the question. Do not give the understanding.**

| Domain | Entry Point Resource | Directed Question |
|---|---|---|
| Amino acid side chain chemistry | Lehninger Ch. 3 or equivalent; PyMOL visualization of residue | *Look at what that side chain actually looks like at pH 7. What does removing it change about anything nearby?* |
| Active site electrostatics | Warshel 2006 review on electrostatic effects in enzymes | *If you change the charge at this position, what happens to the transition state stabilization? How would you know?* |
| Hydrogen bond networks | Foldit/PyMOL H-bond display of WT active site | *Trace every hydrogen bond your target residue participates in. What breaks if you mutate it? What might compensate?* |
| Michaelis-Menten assumptions | Fersht *Structure and Mechanism in Protein Science* Ch. 4 | *Under what conditions does the Michaelis-Menten model break down? Is your experiment inside those conditions?* |
| Substrate binding geometry | PDB structure of BglB with substrate analog; Ligplot+ | *Where does the substrate sit relative to the catalytic residues? What does your mutation change about that geometry?* |
| Thermal stability and ΔTm | Niesen et al. 2007 (DSF protocol paper) | *Your mutant has a lower Tm. What are the possible explanations? Which ones would change your interpretation of the kinetics?* |
| Interpreting kinetic curves | Cornish-Bowden *Fundamentals of Enzyme Kinetics* | *Your Km went up and kcat stayed the same. Tell me in mechanistic terms what that means. Now tell me three things that could cause it.* |
| Statistical interpretation | Motulsky *Intuitive Biostatistics* | *Your p-value is 0.04. What can you actually conclude? What can you not conclude?* |

*This map is a starting point, not a complete inventory. Expand it as you encounter new conceptual walls with mentees.*

---

## Assessment Philosophy

This framework does not assess outcomes. It assesses reasoning.

The reasoning document — maintained across all six movements — is the primary assessment artifact. What you are reading for:

- **Coherence:** Does the narrative hold together? Do causes connect to effects?
- **Honesty:** Does the student know where their gaps are? Do they engage with failure or paper over it?
- **Precision:** Are commitments specific enough to be testable? Are predictions falsifiable?
- **Evolution:** Does the reasoning document show genuine updating in response to results, or does it defensively preserve the original model?

Grade for commitment and genuine engagement. Not for being right.

---

## Context and Scope

This framework is best suited to:

- **1v1 or 1v2 mentorship in a research lab setting** — the ideal starting condition. Small enough to track each person's conceptual position in real time, grounded in real experiments with real stakes.
- **College research courses where commitment matters more than performance** — the six movements translate to a quarter or semester with appropriate scaffolding.
- **D2D network and similar research training contexts** — wherever students are doing genuine design work and need to develop judgment, not just technique.

It is not currently designed for large lecture courses, K-12 settings, or domains without a real design problem at the center. Those adaptations may be possible but are outside the current scope.

---

## Status

**Version 0.1 — framework in active development.**

The philosophy is coherent. The implementation is being validated through practice. This document will evolve as the framework is stress-tested against real mentees making real mistakes.

Contributions, critiques, and forks are welcome. If you run a version of this in your own lab or teaching context, open an issue and describe what broke. That is the most useful data.

---

## Author

Developed from research experience in computational enzyme design (Siegel Lab, UC Davis) and mentorship within the D2D network.

Influenced by: Ad Astra School's project-based learning model, problem-based medical education, and the direct observation that the designer's posture cannot be transmitted — only acquired.

---

*The Roman emperor doesn't plan the perfect empire from a scroll. He governs, sees what breaks, and adapts.*
