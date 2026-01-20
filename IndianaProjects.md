## Indiana Possible Projects

1. ### MathWordNet
  
   Our LLM-extracted database of terms needs a name (I'm suggesting MathWordNet) and more work.

   Our work, described in the spreadsheet in https://docs.google.com/spreadsheets/d/1jLzuvuaLIcRTIQPwQ65fL3o9gzasplJ52eEUFJhhMSk/edit?gid=1391563495#gid=1391563495
   is not working for several reasons.

   Let us try to describe the [plan](https://docs.google.com/document/d/1jodfe-GR7Iz6AfOXsdsDMnGaAU28xGsu8xiG1UUPXns/edit?tab=t.0#heading=h.qxoy9sgivi53) and what doesn't work.

   The plan was:
   * to extract mathematical concepts from the TAC abstracts corpus of 3K sentences, using several different LLMS, just as in our NLi project described in   [Math Natural Language Inference: this should be easy!](https://aclanthology.org/2025.starsem-1.14.pdf)
   * then collect the terms into a database to be distributed to the public.
   * These would be compared to terms in 3 human-curated math resources (Wikidata, nLab, PlanetMath), which would be counted as evidence for a term being a good mathematical concept.
   
   That work, like [Mathoscope](http://www.jacobcollard.com/mathoscope/), did not produce a glossary of mathematical concepts, though, which was our original goal.
   
   Such a glossary should be useful not only for NLI but also for math summarization, math question-answering, and to help formalization and informalization projects, amongst other projects.

   To quote from [Berlioz's phd thesis](https://d-scholarship.pitt.edu/43650/) (Pittsburgh 2022):

   "A major goal of the international math community is to obtain tools for the automated processing and   transformation of mathematical documents. These tools do not currently exist in a satisfactory form, and extensive research is oriented towards improving this.
   
   [The Formal Abstracts Project aims to provide mathematicians with software tools for stating their research results in a human/machine readable format amenable to  formal verification.]

    In order to achieve this goal, the Formal Abstracts Project has recognized the need for
   (1) a comprehensive vocabulary of mathematics, in order to state research results, and for
   (2) improved automated reasoning tools to aid in processing and formally verifying those statements."
   

   We agree with the aims as stated above, but realize that the [Formal Abstracts project](https://github.com/formalabstracts/formalabstracts) has been dormant   (if not dead) for the last seven years. Still, it resonates with us that something like "a comprehensive vocabulary of mathematics", enabling us to state research results, is required.

   Our spreadsheet depends not only on running our prompts in several LLMs, but also on describing and proving correct the other parts of the pipeline.
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
   1. the merger of all mathematical glossaries from Wikipedia  (a smaller and possibly much easier project)
   2. MathGloss almost 5K terms (without official definitions, the definition is implicitly the sum of the information in the human-curated resources HCR)
   3. Wolfram MathWorld 13k concepts, which can onlybe used indirectly through Wikidata, per license regulations.
  
2. ### Trouver+KnowTex+nLab

[KnowTex](https://github.com/ElifUskuplu/KnowTex) by [Elif Uskuplu](https://elifuskuplu.github.io/), Larry Moss and myself is a project to help people understand mathematical text by explaining its logical structure using graphs. 
The logical structure is explained by the authors of the mathematical text, and their use of LaTeX macros. The system is inspired by Massot's BluePrint for Lean, but does not require files in preText format, so it's easier on the human mathematician.

Lean's Blueprint describes the logical structure of a mathematical text, but it also maps it into Lean components (to help with formalization), so it's dedicated to a specific interactive theorem prover, Lean.  Massot generalized it, removing the component mapping to Lean, but kept the preText dependency.
(This is, by and large, a good dependency, as preText can  output several formats besides pdf, including Braille.) But it's not easy to transform a latex file into a preText file, and this is one of the advantages of KnowTex.

A very different approach is taken by [Trouver](https://github.com/hyunjongkimmath/trouver) by [Hyun Jong Kim.](https://sites.google.com/view/hyunjongkimmath/), a number theorist.
Trouver uses machine learning to 'discover' which bits of a mathematical text are definitions, which are results, which are explanations, examples, etc. 
For people like us, trying to map out the whole of mathematical knowledge, this is much better, as it can be applied to any math pdf you want. But it's also worse, from the point of view that there are no guarantees at all that machine learning is doing the correct thing. At least so far.

The idea of this preliminary project would be to put KnowTex and Trouver together, to get some metric for verification, using the nLab corpus.

 Why nLab is special here.
The nLab corpus sits in a unique middle position: * Informal but highly structured
* Definition-heavy
*Concept-centric rather than theorem-centric
* Rich in narrative explanation


nLab pages do not have explicit \uses markup (as KnowTex needs).
But they do have very strong rhetorical and structural cues.

This makes nLab a perfect testbed for automatic vs explicit structure.
