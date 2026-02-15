# KnowTex Roadmap

* [KnowTex](https://github.com/ElifUskuplu/KnowTex) by [Elif Uskuplu](https://elifuskuplu.github.io/), Larry Moss, and myself is a project to help people understand mathematical text by explaining its logical dependency structure using graphs. 
The logical structure is explained by the authors of the mathematical text, and their use of LaTeX macros. 

The system is inspired by [Massot](https://www.imo.universite-paris-saclay.fr/~patrick.massot/en/)'s [Lean BluePrint](https://github.com/PatrickMassot/leanblueprint), but does not require files in preText format, so it's easier for the human mathematician.

Lean's Blueprint describes the logical structure of a mathematical text, but it also maps it into Lean components (to help with formalization), so it's dedicated to a specific interactive theorem prover: [Lean](https://lean-lang.org/). 

Massot generalized the Blueprint, removing the component that does mapping to Lean, but kept the preText dependency.
(This is, by and large, a good dependency, as preText can  output several formats besides pdf, including Braille.) 
But it's not very easy to transform a latex file into a preText file, and this is one of the advantages of KnowTex.

## Trouver: Reassessment (January 2026)

[Trouver](https://github.com/hyunjongkimmath/trouver) by [Hyun Jong Kim](https://sites.google.com/view/hyunjongkimmath/) turned out not to produce meaningful dependency graphs. After testing it on the Kim Algebra book, we found that its output reflects table-of-contents structure only ("this chunk appears in this chapter"), not logical dependencies between definitions and theorems. There is no notion that a given definition is used in a given theorem. The earlier plan to combine KnowTeX and Trouver for comparative evaluation on the nLab corpus has been dropped.

However, Kim's ML classifier for categorizing text into definitions, theorems, explanations, etc. may still be useful as a complementary signal in the future. Valeria is in contact with Kim about this.

## New Direction: Automatic Dependency Inference

The main limitation of KnowTeX is that authors must manually insert `\uses` and `\proves` commands. Our new priority is to build a separate preprocessing tool (`knowtex-infer`) that takes a raw LaTeX file and outputs an annotated copy with auto-generated `\uses` commands. The original KnowTeX.py stays unchanged for manual use.

### Planned heuristics (rule-based, no ML):

- Scan `\ref` / `\eqref` inside theorem bodies and proofs to infer dependencies
- Distinguish statement-level vs. proof-level dependencies (matching KnowTeX's dashed/solid edge convention)
- Use environment ordering as a fallback signal when no `\ref` exists
- (Stretch) Terminology matching: flag likely dependencies when a defined term appears in a later statement without a `\ref`

Auto-inserted commands will be marked with `% auto-generated` so authors can review before running KnowTeX.

**Target: working prototype by mid-March 2026.**

## LeanArchitect (Avigad et al.)

The new [LeanArchitect](https://arxiv.org/pdf/2601.22554) paper automates blueprint metadata within the Lean ecosystem. KnowTeX occupies a complementary space: LaTeX-native, proof-assistant-agnostic, aimed at authors who write informal mathematics. The next version of the paper should position KnowTeX alongside LeanArchitect explicitly, noting that the two tools can work together (e.g., a KnowTeX dependency graph can guide a subsequent Lean formalization effort).

## Case Studies and Evaluation

We will apply KnowTeX (with and without the inference tool) to at least 4 texts:

- 2 textbooks (open-source books)
- 2 research papers (shorter, different scale)

For evaluation:
- A human expert prepares gold-standard `\uses` annotations for each text
- We run `knowtex-infer` on unannotated versions
- Report precision and recall

## Open Questions

- Which additional books/papers for case studies?
- Annotation granularity for gold standard: only Definitions/Theorems/Lemmas, or also Remarks/Examples?
- Do we want to explore Kim's ML classifier as a future signal for `knowtex-infer`?
