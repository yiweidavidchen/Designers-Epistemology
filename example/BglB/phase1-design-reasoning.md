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

We have planned our mutant candidates. Now choose the substrates — probes to test the geometry and contacts of the BglB active site.
 
Assays will use colorimetric 96-well plates: 8 concentrations × 4 proteins (WT + 3 mutants) × 3 replicates per protein. Absorbance fitted by Michaelis-Menten to yield kcat and Km.
 
### Why pNP sugars?
 
I chose p-nitrophenol (p-NO2-Ph-OH) (abbreviation: pNP) as the leaving group for 3 reasons.
 
1. The signal is direct. pNP release produces a strong yellow color (λmax ~420 nm) readable by absorbance without secondary coupled reactions or additional reagents. One plate scan. Linear signal across a wide concentration range — important for accurate Michaelis-Menten fitting across an 8-point dilution series.
 
2. The aglycone is identical across the entire panel. Any differences in kcat or Km between pNP-Glc, pNP-Gal, pNP-Xyl, and the rest are attributable entirely to the sugar moiety and its interactions with the active site. Not to variation in the leaving group. This makes the panel interpretable as a clean readout of binding-site geometry.
 
3. pNP is a good leaving group. The strong electron-withdrawing nitro group on benzene stabilizes the departing phenolate, which is why this chemistry is so widely used for measuring glycosidase activity.
 
One honest limitation: pNP as the leaving group tells us nothing about aglycone specificity in the +1 subsite. This study focuses on the −1 subsite — where the sugar is bound. The +1 subsite remains unprobed.
 
### Why these specific sugars?
 
BglB is evolved to hydrolyze β-sugars. The −OH on the anomeric carbon is equatorial, not axial. So BglB is specific for β-sugars, not α-sugars. In our panel, the anomeric −OH is substituted with pNP across all substrates.
 
The sugars vary along two structural axes: the **C4 epimer axis** and the **ring size / C6 substituent axis**. This lets us dissect which residues are making contact at specific positions on the sugar.
 
OK, start selecting:
 
1. pNP-β-D-glucopyranoside (**pNP-Glc**) — the reference. BglB's natural substrate is cellobiose (Glc-Glc). The active site is most shaped for glucose. Isorna et al. (2007) used pNP-2-F-Glc in the crystal structure to trap the covalent intermediate, confirming the retaining mechanism. Enter the enzyme as a β-sugar, leave as a β-sugar. pNP-Glc is the pivot of the entire panel. WT BglB should yield the best kcat/Km here.
 
2. pNP-β-D-galactopyranoside (**pNP-Gal**) — same β configuration, same D sugar, same pNP leaving group, same 6C ring, same −OH at C2, C3, C6. The only difference from Glc: C4-OH is axial instead of equatorial. Probes the C4 subsite directly. Because only one −OH flips, I predicted the difference in catalytic efficiency between Glc and Gal would be small.
 
3. pNP-β-D-xylopyranoside (**pNP-Xyl**) — same β configuration, same D sugar, same pNP leaving group, but a 5C sugar. In pyranoside form, Xyl lacks the C6-hydroxymethyl group (−CH2OH) entirely. All other −OH configurations match Glc. Probes the C6 subsite. Because the structural difference is larger than Gal — an entire substituent missing rather than a single −OH flip — I predicted the Glc-to-Xyl drop in efficiency would be greater than the Glc-to-Gal drop.
 
Now the negative controls.
 
4. pNP-N-acetyl-β-D-glucopyranoside (**pNP-GlcNAc**) — same β configuration, same D sugar, same pNP leaving group, same stereochemistries as Glc, but C2-OH is replaced by a bulky acetamide group. The acetamide challenges E353 and surrounding residues around C2 to reach the anomeric carbon and form the transition state. I predicted little to no activity. Any signal would likely come from non-enzymatic hydrolysis: pNP and NAc are both strong electron-withdrawing groups (EWGs), making spontaneous hydrolysis a non-negligible background.
 
5. pNP-α-L-arabinopyranoside (**pNP-α-L-Ara**) — different anomeric configuration (α vs β), different sugar series (L vs D), though similar −OH arrangement if drawn in the same chair conformation. Too many differences from BglB's evolved specificity. I predicted no enzymatic activity. Background signal only.
 
Done. Five substrates. One reference. Two axes of structural variation. Two negative controls. Interpretable and executable.

<img width="1053" height="954" alt="image" src="https://github.com/user-attachments/assets/03be0810-68d3-4447-b26a-010e11d6ce7a" />

**And an early screenshot of substrate selection:**

<img width="1101" height="996" alt="image" src="https://github.com/user-attachments/assets/cd952f89-79de-4c6b-a6ea-4f7ab4ec2c8e" />


### Why not a fourth positive sugar?
 
A fourth positive sugar — pNP-β-D-fucopyranoside (**pNP-Fuc**) was a candidate — was considered and dropped. The primary purpose of Phase 1 was presentation at the URC conference, which imposed a real deadline in Feb 2026 for abstract submission. More importantly, the viable window for kinetic assays is only 2 days after protein purification. Assaying across more substrates within that window, with 8 concentrations × 4 proteins × 3 replicates per protein, was not executable for one person working alone without compromising either the data quality or their sanity.
 
> Scope decisions in research are not always about what is scientifically optimal. They are about what is executable given real constraints — time, labor, deadlines. Knowing when to stop adding variables and commit to what is interpretable and doable is part of the designer's judgment, not a failure of ambition.
 
pNP-Fuc and other sugars — pNP-Fuc probes the C6 methyl (-CH3) vs. hydroxymethyl (-CH2OH) distinction — are candidates for the expanded substrate panel in Phase 2, where the team has more hands and more time.
 
> Knowing when to step on the gas & when to step on the brake is a competency the designer develops under real resource constraints.

---
 
## Predictions Before the Data

### What I Was Confident About

1. The two catalytic glutamates (E164 & E353) would behave as negative controls. E164A and E353D would show the most severe drops in activity across all substrates — E164A more than E353D, because knocking out the acid/base entirely is more disruptive than shortening the nucleophile's reach by one methylene. This I was sure of.
 
2. The mutant × substrate interaction would exist. The whole point of the panel was to detect differential effects across substrates. If all mutants behaved identically across all substrates — if the interaction was flat — the experiment would have told us nothing about specificity.
 
3. pNP-Glc would be the best substrate for WT. It is the natural substrate. Everything else is a deviation from that.

4. pNP-GlcNAc and pNP-α-L-Ara would show little to no signal. Catalytic activity here is essentially a yes/no question. I designed a simple plate setup with only low and high concentrations of these two sugars. No full dilution series, no inclusion in statistical analysis.

### What I Was Uncertain About

1. The adjacent residues: N163, T352, N354. My hypotheses about their roles were mechanistically grounded but not strongly predictive. I could reason about what their side chains were doing in the WT structure, but I couldn't confidently predict whether removing or altering an H-bond would increase or decrease activity on a specific non-native substrate. The sign of the effect was uncertain even when the existence of an effect seemed likely.
 
2. The relative ordering of non-native substrates. I expected pNP-Glc > everything else for WT. But between pNP-Gal and pNP-Xyl, I had a directional expectation without strong mechanistic grounding — enzyme active site interactions are more complex than a simple structural comparison captures.
 
**My expectation**: the activity drop relative to pNP-Glc would be greater for Xyl than for Gal. A missing C6-CH2OH group is a larger structural deviation than a C4-OH flip. I also assumed that polar hydroxyl contacts contributed more to binding affinity than hydrophobic or stacking contacts — so fewer hydroxyls meant weaker binding. Three hydroxyls versus four: the substrate with fewer contacts should bind worse.
 
**The reasoning for each:**
 
When pNP-Gal encounters the active site, the C4-OH is axial instead of equatorial. I assumed the other contacts (C2, C3, C6) would find their corresponding positions readily, and the C4-OH would still engage its binding site, just less optimally positioned.
 
When pNP-Xyl encounters the active site, C2, C3, C4-OH can all find their positions, but there is a void at the C6 site. The active site geometry is fixed — BglB cannot compensate for the missing -CH2OH. The substrate would bind in a less optimal pose, with nothing to fill the C6 pocket.
 
Therefore: Gal retains more contacts than Xyl. Activity should drop less for Gal than for Xyl. 

	This was my prior. It was wrong.

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



