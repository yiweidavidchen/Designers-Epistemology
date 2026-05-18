# Phase 1 Design Reasoning — BglB Substrate Specificity
 
**Project:** β-Glucosidase B (BglB) substrate specificity via active-site mutagenesis

**Phase:** Catalytic and catalytic-adjacent residues.

**Residues targeted:** E164, E353, N163, T352, N354. *(Here I use Foldit numbering. PDB numbering = Foldit numbering + 3)*

**Substrate panel:** pNP-Glc, pNP-Gal, pNP-Xyl, pNP-α-L-Ara, pNP-GlcNAc

**Author:** Yiwei Chen

**Lab:** Justin Siegel Lab, UC Davis
 
---
 
## Why These Residues

I began to design BglB not because I wanted to optimize the catalytic speed of a hydrolase by random and nonparametric guessing of mutations — typically a polar to another polar, a hydrophobic to another hydrophobic, an aromatic to another aromatic. My first goal upon entering the Siegel Lab was not studying BglB at all. It was a de novo design of a Suzuki coupling enzyme, a Diels-Alder enzyme, or an ozonolysis enzyme. Through conversations with grad students and postdocs, I soon realized the difficulty of that imagination as an undergraduate.
 
I needed to work on enzyme specificity first — before designing enzymes myself and facing hundreds of possible structures and uncertainties. I needed to work on the most controllable sets of uncertainties before taking on computational enzyme design challenges and designing novel mechanisms that could impact the world.
 
In November 2025, I came across Isorna et al.'s detailed 2007 research on BglB's crystal structure, active site mechanism, and computational analysis. I looked at the reaction mechanism with a covalent intermediate inside the active site.
 
Glu164 is the acid/base residue. It toggles protons among water molecules and itself. It is a juggler.
 
Glu353 is the nucleophile. It attacks the anomeric carbon, forms a covalent intermediate with the sugar ring, and holds it there. Then OH⁻ attacks, the sugar leaves. Not an attacker — a grappler.
 
Sounds interesting.
 
I hypothesized that mutating both Glu's (proven by evolution) would equally make catalytic efficiency worse. Changing them destroys enzyme activity. But I still mutate them to show control effects.
 
Mutating only catalytic residues would be limiting, because the residues next to them often accommodate particular spatial positions for better and more flexible reactions. Adjacent residues are the "context." Catalytic residues are the "arguments." The argument without context is ambiguous — it acts, but without specificity. The context constrains what the argument can mean.
 
So I thought about adjacent residues as the "context." Only the residues +1 or −1 relative to the two glutamates. I didn't consider +2 or −2 because: (1) that greatly expands the scope; (2) harder to analyze positional effects on the substrate, so less immediate than +1 or −1; (3) only considering catalytic and catalytic-adjacent was already a limitation — the binding-site residues that probe the substrates' hydroxyls and the ring oxygen also touch the substrate, so there's diminishing return in spending all resources on the catalytic side alone.
 
OK, start residue selection:
 
**Asn163** — a neutral polar residue with an amide side chain. Both hydrogen bond donor and acceptor. And both an adjacent residue and a probe of C2-OH. Good. Excellent candidate to study specificity.
 
**Pro165** — a neutral secondary amine residue with a very rigid structure that could define the fold of the protein. Dangerous to mutate. Will either add too much or too little information to interpretation. Don't choose this.
 
**Thr352** — a neutral polar residue with a secondary alcohol. Both somewhat polar and hydrophobic. Chirality guides H-bond network directionality — relevant for specificity. Good.
 
**Asn354** — adjacent residue. From PyMOL, it looks a bit distant from the substrate. Good to keep. Hypothesis: secondary contact, maintains an H-bond network. Good.
 
Done. Don't move further. Don't add too many variables. Make the study controllable.
 
Adding variables would compromise interpretability.
 
OK, start mutant selection:
 
My rule: because the study was concentrated on substrate specificity, subtle changes would carry more information than big changes that would potentially destroy enzyme activity entirely.
 
I thought mutations in the catalytic machinery would lead to more intense changes in catalytic efficiency, because it governs turnover.
 
**E164:**
- *E164D* — a methylene group difference. Shorter reach, to see if a delayed transition state would work smoothly with Glu353. Expected lower catalytic activity.
- *E164A* — mutate to Ala, a small nonpolar residue. To see how a knockout of the acid/base residue would damage protonation of the leaving group. Potential negative control. Surrounding residues in the active site could also toggle protons, but more indirectly and with more random steps.
- Don't mutate to Asn/Gln. Amides are good at being diplomats but not commanders.

**E353:**
- *E353D* only. Test the reach of the nucleophile. Mutating to others would not add direct mechanistic information.

**N163:**
- *N163H* — change to a bigger ring with ability to toggle protons. A more deliberate middleman than carboxylates. pH-dependent ionizable. Might immediately grab a proton from E164, damaging activity.
- *N163Q* — a methylene longer. Extended H-bond. Might intervene with substrate recognition.
- *N163T* — a less polar one. More hydrophobic. Chirality adds uncertainty about the extent to which activity changes.

**T352:**
- *T352A* — alanine scanning, knockout. Remove H-bonding.
- *T352V* — hydrophobic substitution of similar size. Remove H-bonding.
- *T352N* — longer H-bonding network.
- (T352S was also planned but not executed: conservative, shorter chain, more accessible H-bonding.)

**N354:**
- *N354Q* — conservative. Longer H-bonding network.
- *N354S* — smaller H-bond donor.

OK. 11 mutants + WT. Executable with 2 rounds of protein production and assaying. Saves time.

**An early screenshot of mutant selection:**

<img width="835" height="1118" alt="image" src="https://github.com/user-attachments/assets/4279cebb-601f-4a19-b325-65d35e8202c0" />


---
 
## Why These Substrates

---
 
## Predictions Before the Data

### What I Was Confident About

### What I Was Uncertain About

---
 
## What the Data Actually Showed
 
---
 
## The pNP-Xyl Finding

### What I Expected
 
### What I Saw
 
### Why It Was Unexpected
 
### How I Reconstructed My Thinking
 
---
 
## What Phase 1 Opened That Phase 1 Couldn't Answer

---
 
## What I Would Have Designed Differently

---
 
## What This Document Is For

This is not a methods section. It is not a results section. It is a record of how a specific person reasoned through a specific design problem — including the wrong turns.
 
Future students reading this should not use it as a template for what to predict. They should use it as evidence that the unexpected result is normal, that reconstructing your reasoning around new data is the work, and that the designer's posture means staying inside the problem when it gets hard rather than retreating to what you already knew.
 
The pNP-Xyl finding is not an anomaly to be explained away. It is the curriculum.



