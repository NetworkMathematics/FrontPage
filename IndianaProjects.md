## Indiana (Possible) Projects

1. ### MathWordNet
  
   Our LLM-extracted database of math terms needs a name (I'm suggesting MathWordNet) and more work.

   Our work, described in the spreadsheet in https://docs.google.com/spreadsheets/d/1jLzuvuaLIcRTIQPwQ65fL3o9gzasplJ52eEUFJhhMSk/edit?gid=1391563495#gid=1391563495
  has several problems.

   Let us try to describe the [plan](https://docs.google.com/document/d/1jodfe-GR7Iz6AfOXsdsDMnGaAU28xGsu8xiG1UUPXns/edit?tab=t.0#heading=h.qxoy9sgivi53) and what doesn't work.

   The plan was:
   * to extract mathematical concepts from the TAC abstracts corpus of 3K sentences, using several different LLMS. (just as in our NLI project described in   [Math Natural Language Inference: this should be easy!](https://aclanthology.org/2025.starsem-1.14.pdf))
   * Then collect the terms into a database to be distributed to the public.
   * These would be compared to terms in 3 human-curated math resources (Wikidata, nLab, PlanetMath), which would be counted as evidence for a term being a good mathematical concept.
   * the criteria for soundness of the mathematical concepts 'discovered' by the LLMs is their showing up in the human-curated resouces.
   * augmentation with the definition of the term is desired.
   
   Our first joint work on [LLM-extracted concepts](https://arxiv.org/pdf/2309.00642), like [Mathoscope](http://www.jacobcollard.com/mathoscope/), did not produce a glossary of mathematical concepts, which was our original goal. (While MathGloss did produce a small (<5K) database of math concepts.)
   
   A real glossary should be useful not only for NLI but also for math summarization, math question-answering, and to help formalization and informalization projects, amongst other applications.

   To quote from [Berlioz's phd thesis](https://d-scholarship.pitt.edu/43650/) (Pittsburgh 2022):

   "A major goal of the international math community is to obtain tools for the automated processing and   transformation of mathematical documents. These tools do not currently exist in a satisfactory form, and extensive research is oriented towards improving this.
   
   [The Formal Abstracts Project aims to provide mathematicians with software tools for stating their research results in a human/machine readable format amenable to  formal verification.]

    In order to achieve this goal, the Formal Abstracts Project has recognized the need for
   (1) a comprehensive vocabulary of mathematics, in order to state research results, and for
   (2) improved automated reasoning tools to aid in processing and formally verifying those statements."
   

   We agree with the aims of the formal abstracts project as stated above, but realize that the [Formal Abstracts project](https://github.com/formalabstracts/formalabstracts) has been dormant   (if not dead) for the last seven years. Still, it resonates with us that something like "a comprehensive vocabulary of mathematics" (CVM), enabling us to state research results, is necessary.

   Our spreadsheet in our new submission depends not only on running our prompts in several LLMs, but also on describing and proving correct the other parts of the pipeline.
   For instance, there might be mistakes when mapping terms to Wikidata, both of not finding concepts that are there and also of finding wrong concepts with the same name,   e.g. mapping into disambiguation pages in wikidata, or mapping "ring" algebraic structure to "ring" piece of jewelry.

   So we need to provide some metrics and measurements to show how good our database of terms is:
   1. need to show LLMs mostly get good math concepts;
   2. using the intersection of the outputs of LLMs is a good strategy (LLMs as judges)
   3. our pipeline is increasingly monotonic, i.e. adding more human-curated resources improves the quality of the proposed terms
   4. our terms have math definitions that make them unambiguous, as much as possible
   5. we do not have 'wrong' terms
   6. we have enough 'good' terms
  
   Something along the lines of the 6 items above would guarantee a reasonable "comprehensive vocabulary" (with definitions, this would be a comprehensive glossary) of mathematical terms.

    A posteriori verifications should also be done, comparing the terms obtained in our database with:
   1. The merger of all mathematical glossaries from Wikipedia  (a smaller and possibly much easier project, see below project #4)
   2. MathGloss almost 5K terms (without official definitions, the definition is implicitly the sum of the information in the human-curated resources HCR)
   3. Wolfram MathWorld 13k concepts, which can onlybe used indirectly through Wikidata, per license regulations.
  
2. ### Trouver+KnowTex+nLab (with Elif)

[KnowTex](https://github.com/ElifUskuplu/KnowTex) by [Elif Uskuplu](https://elifuskuplu.github.io/), Larry Moss and myself is a project to help people understand mathematical text by explaining its logical structure using graphs. 
The logical structure is explained by the authors of the mathematical text, and their use of LaTeX macros. The system is inspired by Massot's BluePrint for Lean, but does not require files in preText format, so it's easier on the human mathematician.

Lean's Blueprint describes the logical structure of a mathematical text, but it also maps it into Lean components (to help with formalization), so it's dedicated to a specific interactive theorem prover, Lean.  Massot generalized it, removing the component mapping to Lean, but kept the preText dependency.
(This is, by and large, a good dependency, as preText can  output several formats besides pdf, including Braille.) But it's not easy to transform a latex file into a preText file, and this is one of the advantages of KnowTex.

A very different approach is taken by [Trouver](https://github.com/hyunjongkimmath/trouver) by [Hyun Jong Kim.](https://sites.google.com/view/hyunjongkimmath/), a number theorist.
Trouver uses machine learning to 'discover' which bits of a mathematical text are definitions, which are results, which are explanations, examples, etc. 
For people like us, trying to map out the whole of mathematical knowledge, this is much better, as it can be applied to any math pdf you want. But it's also worse, from the point of view that there are no guarantees at all that machine learning is doing the correct thing. At least so far.

The idea of this preliminary project would be to put KnowTex and Trouver together, to get some metric for verification, using the nLab corpus.

 Why nLab is special here.
The nLab corpus sits in a unique middle position: 
* Informal but highly structured
* Definition-heavy
* Concept-centric rather than theorem-centric
* Rich in narrative explanation


nLab pages do not have explicit `\uses' markup (as KnowTex needs).
But they do have very strong rhetorical and structural cues.

This makes nLab a perfect testbed for automatic vs explicit structure.

A concrete comparative experiment:

* Step 1: Run trouver on nLab2020.
  
   Outputs:
   * inferred dependency graphs,
   * inferred concept/definition relationships,
   * noisy but automatic structure.

This gives us:
* machine-inferred structure.

* Step 2: Select a subset of nLab pages
For example: category theory basics, adjunctions, limits/colimits.

* Step 3: Hand-annotate a small gold subset using KnowTeX
       * Add \uses and \proves manually.

Treat this as editorial ground truth.
This gives us:

      * author-validated structure.

* Step 4: Compare!
  
   Now we can ask real research questions:
    * Which dependencies does Trouver reliably find?
    * Which does it systematically miss?
    * Where does it hallucinate edges?
    * Are narrative dependencies harder than proof dependencies?
    * Does symbol introduction help or hurt inference?

This comparison would be far more meaningful than evaluating Trouver against generic NLP metrics.

3. ### MathAnnotator for all texts

   Our 2023 preprint [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) has an annotator prototype [MathAnnotator](https://gaoq111.github.io/math_concept_annotation/), created by Bert Gao that only works for some people annotating math texts that we have processed before.

   It would be nice to provide a service where other people could annotate their own files and where we could benefit from their work, by aggregating the new concepts that they checked.
   
   This shouldn't be too difficult, if we insist on a limited number of pages, say 20 at max.

    It might require some bureaucratic work to pay for the use of the LLMs in question. We continue with our suggestion that the "Silver truth" is what the top LLMs agree on. And maybe we only want some verified people annotating (e.g. Hai's students plus us). This could be adevelopment from the first project, or independent of that.

4. ### Glossary from Wikipedia
      A simple project should be stitching together the 36 math glossaries from Wikipedia, available from https://en.wikipedia.org/wiki/Category:Glossaries_of_mathematics and collecting the definitions offered. This is not as easy as one might think, as repetitions will undoubtedly happen and choices will have to be made. But this might be good preparation for stitching together different human-curated resources, which also needs to be done.

      Similarly, but more difficult, try to ascertain the real size of the Maths Portal in Wikipedia.
      Calculations I have attempted.
     * From the query "https://tools.wmflabs.org/enwp10/cgi-bin/list2.fcgi?run=yes&projecta=
Mathematics", we obtain a page with 32K mathconcepts in Wikipedia, actually 32115 pages. (see the paper [Modelling the Way Mathematics Is Actually Done](https://dave.murray-rust.org/paper_store/corneli2017ModellingWay.pdf), 2017.)
     * (with Lucy Horowitz) Using SQL on Wikidata, nodes connected to "mathematical concept" (mathematical concept (Q24034552)) produced 300K concepts, within 5 hops. However, this is not a case of one hop better/more important/more relevant concept; almost the opposite. 

 5. ### Misc other projects

    Several other ideas could be written.
    * Extracting logical structure (using systems for NLP argumentation) to join in with our NLI project or with more general semantics of math text.     * Try to do something with math causality, as Bert and I were doing with Katrine Thoft.
    * Use David Wadden's  [Fact or Fiction](https://aclanthology.org/2020.emnlp-main.609/) approach to verify mathematical claims, potentially using their existing work on LLMs and consensus as a gold standard. 
    * Verify the quality of coreference in our "big" NLI corpus ~1200 pairs
    * Start using a corpus of arxiv preprints in CT
    * If we had our comprehensive vocabulary of mathematics(CVM) which kinds of questions would it help us answer? clearlythe questions of the form "What is X?" (whereX isa mathematical concept. and (not-so clearly, but possibly) questions of the form "How are X and Y related?"  where Xand Y are mathematical concepts.  More interesting  would be to be able to answer questions of the form "What is the analogous of theorem X for the subfield Y?". For example, "duality induced by negation in classical propositional logic is analogous to duality of finite-dimensional vector spaces". What else  would we hope to have answered? what would be the "low-hanging fruit" theorems?

    But 4 small projects seem enough to begin with.
