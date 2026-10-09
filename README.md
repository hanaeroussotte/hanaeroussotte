# Hanaé Roussotte

**PharmD · Biostatistician in preclinical R&D · Computational biology for drug discovery**

I'm a pharmacist working as a biostatistician, and I'm most interested in finding new drug targets: following a disease from its molecular origin to what we see in patients, and working out where we could intervene.

That's where I started, but it's not where I want to stop. With the tools now available, I'm excited to see how far, and how precisely, we can push biology. I'm particularly interested in agentic approaches to genomics, and in creative ways of getting new findings out of existing data.

The projects below are my first attempts. Several more are in progress, so this page will keep growing.

Repositories are private for now. I'm happy to share them on request.

---

### `te-knowledge-graph` — tracing how transposable elements drive inflammation

A biological knowledge graph in which transposable elements are entities in their own right, not an afterthought, with a rule-based reasoning layer on top. Every answer comes with its level of evidence and a proof that leads back to the original record. If the evidence doesn't support an answer, the system declines to give one.

One result I like: starting only from a DNMT1 knockdown and two Gene Ontology records, with no DNMT3A or TET2 data at all, the graph infers that losing DNMT3A *raises* transposable-element expression while losing TET2 *lowers* it — opposite directions, for two genes nobody perturbed. That matches what we measured in 68 patient samples in the GeroScience paper below.

- 9,366 edges, each with its source recorded
- 6 inference rules, run until no new conclusions appear
- 4 of the 14 demo genes return a refusal rather than an answer
- a citation check that removes any generated sentence citing a link that doesn't exist in the graph

### `mva-variant-prediction` — ranking diagnoses, not variants

Phenotype-driven prioritisation for a single whole genome, built for the MVA Hackathon 2026 on data from a real undiagnosed child. Each candidate is a gene, the alleles actually observed, and the specific disease those alleles can cause, scored on how much of the child's presentation it explains.

My first version got it wrong. It ranked a variant first because it was highly damaging and labelled pathogenic, but the disease it causes explained only one of the eight presenting features. Fixing that became the core of the method.

Evaluated on 80 held-out synthetic cases, with the pipeline frozen before the cases were generated and ClinVar labels masked.

---

**Publication**
Hasan M, et al. *Retrotransposable element derepression distinguishes DNMT3A-mutant from TET2-mutant clonal haematopoiesis.* GeroScience, 2026. [doi:10.1007/s11357-026-02510-6](https://doi.org/10.1007/s11357-026-02510-6). I contributed the data analysis and the Methods.
