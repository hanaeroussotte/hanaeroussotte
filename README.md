# Hanae Roussotte

PharmD · biostatistician, preclinical R&D · I build reasoning systems over biological
evidence that know what they are not entitled to conclude.

I work at the join between statistical modelling and AI for drug discovery: knowledge graphs
that carry provenance, rule-based inference with inspectable proofs, and evaluation discipline
for systems whose failure mode is a confident wrong answer.

My project repositories are private. I am happy to share them on request.

---

### `te-knowledge-graph` — evidence-traceable reasoning over transposable-element regulation

A biological knowledge graph in which transposable elements are first-class entities, with a
forward-chaining rule layer on top. Every answer carries an evidence tier and a proof back to
a primary record; where the evidence does not support an answer, the system returns nothing
rather than a plausible sentence.

From one DNMT1 knockdown measurement and two Gene Ontology records — with no DNMT3A or TET2
data of any kind — it derives opposite signs on the 5mC axis for both genes. That direction
matches what was measured in 68 PBMC samples in the GeroScience paper below.

9,366 provenance-tracked edges · 6 rules run to fixpoint · 4 of 14 demo genes return a
refusal · a citation gate that drops any generated sentence citing an edge ID that does not
resolve.

### `mva-variant-prediction` — rank diagnostic explanations, not variants

Phenotype-driven prioritisation for a singleton whole genome, built for the MVA Hackathon 2026
on a real undiagnosed child's data. A candidate is a gene, the allele configuration actually
observed, and the specific disease that configuration can produce — scored on how much of the
presentation it explains.

The first version ranked a CADD-49, ClinVar-Pathogenic variant first and was wrong, because
the disease that allele can cause explained one of eight presenting features. Evaluated on 80
held-out synthetic cases with the pipeline frozen before the cases were generated and ClinVar
labels masked: 12–0 and 11–0 on paired McNemar, with no case regressing in either direction.

---

**Publication.** Hasan M, *et al.* Retrotransposable element derepression distinguishes
DNMT3A-mutant from TET2-mutant clonal haematopoiesis. *GeroScience*, 2026.
[doi:10.1007/s11357-026-02510-6](https://doi.org/10.1007/s11357-026-02510-6) — author 4 of 30,
credited with the data analysis and the Methods.
