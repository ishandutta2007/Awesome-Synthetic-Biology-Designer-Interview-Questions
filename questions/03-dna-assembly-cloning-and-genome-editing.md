# 3. DNA Assembly, Cloning & Genome Editing

The practical molecular biology methods for actually building the designs conceived in the previous section.

---

### Q: Compare Golden Gate assembly and Gibson assembly as DNA assembly methods. What are the key tradeoffs between them? 🟡

**Answer:**
**Golden Gate assembly** uses type IIS restriction enzymes (which cut outside their recognition sequence, allowing the recognition sequence itself to be removed from the final assembled product) to cut and ligate multiple DNA fragments together in a single, one-pot reaction, with fragment order and orientation determined by designed, complementary overhangs — well-suited to modular, standardized part-based assembly (fitting naturally with the standardization concepts discussed in section 1), and allows highly efficient, scarless, one-pot assembly of many fragments simultaneously when parts are designed with a compatible overhang scheme upfront.

**Gibson assembly** uses an enzymatic mix (an exonuclease to create single-stranded overhangs, a polymerase to fill gaps, and a ligase to seal nicks) to join DNA fragments with designed overlapping end sequences, without requiring specific restriction sites — more flexible in that it doesn't require fragments to avoid specific restriction sites internally (which Golden Gate assembly generally requires, to prevent unwanted internal cutting), making it well-suited for assembling fragments from more varied, less pre-standardized sources.

Key tradeoffs: Golden Gate assembly is generally more efficient and scalable for repeated, standardized assembly of many different combinations from a well-characterized part library (e.g., high-throughput combinatorial assembly), but requires more upfront design discipline (avoiding internal restriction sites, designing a consistent overhang scheme); Gibson assembly is more flexible for one-off or less-standardized assembly tasks and can more easily accommodate arbitrary junction points, but is sometimes less efficient for assembling very large numbers of fragments in a single reaction compared to a well-optimized Golden Gate scheme.

**Follow-ups:**
- If you were setting up a high-throughput combinatorial library of genetic circuit variants for a screening campaign, which assembly method would you lean toward, and why?

---

### Q: What is CRISPR-Cas9-based genome editing, and what determines the specificity of where in the genome it makes a cut? 🟢

**Answer:**
CRISPR-Cas9 genome editing uses the Cas9 protein (a DNA-cutting enzyme) guided to a specific genomic target site by a short guide RNA (gRNA) sequence that base-pairs with the complementary target DNA sequence — once bound, Cas9 introduces a double-strand break at the target site, which the cell then repairs through one of its native DNA repair pathways (which can be exploited to introduce a desired edit, insertion, or gene disruption).

Specificity is primarily determined by: **the guide RNA's sequence complementarity to the intended target genomic site** (a longer, more unique matching sequence generally provides higher specificity), and **the presence of a compatible PAM (protospacer adjacent motif) sequence** immediately next to the target site, which is a specific short sequence motif required by the particular Cas enzyme variant being used for it to engage and cut at that location — a genomic site lacking an appropriately positioned PAM sequence generally cannot be targeted by a given Cas9 variant regardless of how well the guide RNA sequence would otherwise match.

**Follow-ups:**
- What is an "off-target effect" in CRISPR editing, and what design considerations would you use to minimize the risk of unintended edits at unintended genomic locations?

---

### Q: What's the difference between using CRISPR-Cas9 for gene knockout versus precise gene editing/knock-in, in terms of which cellular DNA repair pathway is being leveraged? 🟡

**Answer:**
After Cas9 introduces a double-strand break, the cell repairs it via one of (broadly) two pathways: **non-homologous end joining (NHEJ)**, which directly rejoins the two broken DNA ends, often introducing small insertions or deletions (indels) at the repair junction due to the imprecise nature of this repair process — this is commonly leveraged for simple **gene knockout** applications, since an indel within a coding sequence frequently causes a frameshift that disrupts the gene's function; or **homology-directed repair (HDR)**, which uses a homologous DNA template (either the cell's own sister chromatid, or, for engineering purposes, a supplied synthetic donor template) to repair the break with high fidelity, guided by sequence homology to the template — this is leveraged for **precise editing or knock-in** applications, since supplying a donor template with a desired sequence change flanked by homology arms allows a specific, intended edit to be introduced at the break site rather than a random indel.

A key practical consideration: HDR is generally much less efficient than NHEJ in most cell types and conditions (NHEJ tends to dominate as the cell's default repair pathway), so achieving efficient precise editing via HDR often requires additional strategies (e.g., timing interventions to cell cycle phases where HDR is more active, or suppressing NHEJ pathway components) to shift the balance toward the desired repair outcome.

**Follow-ups:**
- Why might HDR-based precise editing be particularly inefficient in non-dividing or slowly-dividing cell types, and what does this imply for choosing an editing strategy in such contexts?

---

### Q: What is multiplexed genome editing, and what additional challenges does it introduce compared to editing a single genomic locus at a time? 🔴

**Answer:**
Multiplexed genome editing refers to introducing multiple, simultaneous genetic edits at different genomic loci within the same cell/organism in a single engineering effort (e.g., using multiple guide RNAs targeting different sites simultaneously), rather than editing one locus at a time in sequential rounds.

Additional challenges: **increased risk of unintended interactions between simultaneous edits** — e.g., off-target effects or repair outcomes at one locus could be influenced by the cellular repair machinery being simultaneously engaged at multiple other break sites; **more complex verification requirements**, since confirming that all intended edits were achieved correctly (and that no unintended edits occurred) across multiple loci simultaneously is more laborious and computationally/analytically demanding (often requiring whole-genome or targeted multi-locus sequencing) than verifying a single edited locus; **potential for reduced overall editing efficiency per locus** compared to single-locus editing, since cellular repair and CRISPR machinery capacity may be a limiting, shared resource across simultaneous editing events; and **combinatorial complexity in troubleshooting** — if a multiplexed editing attempt doesn't produce the expected combined phenotype, diagnosing which specific edit(s) succeeded, failed, or interacted unexpectedly is considerably harder than troubleshooting a single-locus edit.

**Follow-ups:**
- How would you design a verification/sequencing strategy to confirm that a multiplexed editing experiment achieved all intended edits correctly, in a way that's practical at reasonable cost and throughput?

---

### Q: How would you troubleshoot a cloning/assembly experiment that's consistently producing no colonies, or colonies that don't contain the correct construct, after several attempts? 🟡

**Answer:**
- **Verify each individual component before troubleshooting the combined assembly** — confirm that individual DNA fragments (via gel electrophoresis or sequencing) are actually the expected size/sequence, and that basic reagents (competent cells, antibiotics for selection) are functioning as expected using a known-good positive control, before assuming the problem lies in the assembly reaction itself.
- **Check for common, "boring" causes first**, similar to the debugging discipline discussed in the Computational Biologist companion repo — e.g., a common source of "no colonies" results is simply an expired or improperly stored reagent (competent cells, antibiotic), or an incorrect antibiotic selection marker mismatch, rather than a genuine design flaw in the assembly.
- **Consider whether the assembled construct itself may impose a fitness cost or toxicity on the host** — some genetic constructs (e.g., strongly overexpressing a toxic protein, or a construct that disrupts an essential host function) can be genuinely difficult or impossible to maintain in a standard cloning host, producing few or no viable colonies not due to a technical assembly failure but because successfully assembled cells simply don't survive/grow — this may require a different cloning strategy (e.g., a tightly repressed inducible system, or a different, more tolerant host strain).
- **Re-examine the assembly design itself** for potential issues (e.g., unintended internal restriction sites for a Golden Gate assembly, insufficient homology arm length/uniqueness for a Gibson assembly, or secondary structure in overlap regions that could impair efficient annealing) once more mundane causes have been ruled out.

**Follow-ups:**
- You confirm all individual components and reagents are correct, and rule out toxicity, but the assembly still consistently fails. What would you investigate next about the assembly design itself?
