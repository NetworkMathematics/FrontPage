# KnowTex Roadmap

* [KnowTex](https://github.com/ElifUskuplu/KnowTex) by [Elif Uskuplu](https://elifuskuplu.github.io/), Larry Moss, and myself is a project to help people understand mathematical text by explaining its logical dependency structure using graphs. 
The logical structure is explained by the authors of the mathematical text, and their use of LaTeX macros. 

The system is inspired by [Massot](https://www.imo.universite-paris-saclay.fr/~patrick.massot/en/)'s BluePrint for Lean, but does not require files in preText format, so it's easier for the human mathematician.

Lean's Blueprint describes the logical structure of a mathematical text, but it also maps it into Lean components (to help with formalization), so it's dedicated to a specific interactive theorem prover, Lean.  
Massot generalized it, removing the component mapping to Lean, but kept the preText dependency.
(This is, by and large, a good dependency, as preText can  output several formats besides pdf, including Braille.) But it's not so easy to transform a latex file into a preText file, and this is one of the advantages of KnowTex.

* [Trouver](https://github.com/hyunjongkimmath/trouver) by [Hyun Jong Kim.](https://sites.google.com/view/hyunjongkimmath/), a number theorist is a very different approach.
I thought Trouver used machine learning to 'discover' which bits of a PDF mathematical text are definitions, which are results, which are explanations, examples, etc. I thought it transformed the whole latex into plain text and used classifiers for learning which bit was what.
But after seeing its use on the Kim Algebra book, I think I had it all wrong.

For people like us, trying to map out the whole of mathematical knowledge, this would be much better, as it could be applied to any math pdf you want, you don't need to have the latex source. But it's also worse, because if you classified a chunk as a definition, there would be no guaranties that another  chunk, exactly the same, would be classified as a definition again and connect to the first one. There is no notion of logical dependency between the chunks, that from the ML perspective are just atoms. the whole graph that Trouver creates is simply a fancy version of looking at the Table of Contents of the book itself. It does not have more information than "this chunk appears in this chapter". 
(Also from the point of view that there are no guarantees at all that machine learning is doing the correct thing. At least so far.)

I thought we could put KnowTex and Trouver together, to get some metric for verification, using the nLab corpus.

Why the nLab is good corpus for this:
* Informal but highly structured
* Definition-heavy
* Concept-centric rather than theorem-centric
* Rich in narrative explanation

Of course, the nLab pages do not have explicit `\uses' markup (as KnowTex needs).
But they do have very strong rhetorical and structural cues.

This makes nLab a perfect testbed for automatic vs explicit structure, but only if we can get the automatic structure, which Trouver does not provide.

A concrete comparative experiment:
* Step 1: Run trouver on nLab2020.
   Outputs:
   * inferred dependency graphs, (not really)
   * inferred concept/definition relationships, (not really)
   * noisy but automatic structure. (not really)

But IF we could get a "machine-inferred structure"

* Step 2: Select a subset of nLab pages
(For example: category theory basics, adjunctions, limits/colimits.)
  * Hand-annotate a small gold subset of nLab using KnowTeX (this would also be problematic, given that nLab is not written in latex)
  * Add \uses and \proves manually.
  * Treat this as editorial ground truth: This would give us author-validated structure.

* Step 4: Compare!
  
   Now we can ask real research questions:
    * Which dependencies does Trouver reliably find?
    * Which does it systematically miss?
    * Where does it hallucinate edges?
    * Are narrative dependencies harder than proof dependencies?
    * Does symbol introduction help or hurt inference?

This comparison would be far more meaningful than evaluating Trouver against generic NLP metrics.
