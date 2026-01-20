## Indiana Possible Projects

1. ### MathWordNet
  
   Our LLM-extracted database of terms needs a name (I'm suggesting MathWordNet) and more work.

   Our work, described in the spreadsheet in https://docs.google.com/spreadsheets/d/1jLzuvuaLIcRTIQPwQ65fL3o9gzasplJ52eEUFJhhMSk/edit?gid=1391563495#gid=1391563495
   is not working for several reasons.

   Let us try to describe the [plan](https://docs.google.com/document/d/1jodfe-GR7Iz6AfOXsdsDMnGaAU28xGsu8xiG1UUPXns/edit?tab=t.0#heading=h.qxoy9sgivi53) and what doesn't work.

   The plan was:
   * to extract mathematical concepts from the TAC abstracts corpus of 3K sentences, using several different LLMS, just as in our NLi project in
   [Math Natural Language Inference: this should be easy!](https://aclanthology.org/2025.starsem-1.14.pdf).
   * then collect the terms into a database to be distributed to the public.
   * These would be compared to terms in 3 human-curated math resources (Wikidata, nLab, PlanetMath), which would be counted as evidence for a term being a good mathematical concept.
   
   That work, like [Mathoscope](http://www.jacobcollard.com/mathoscope/), did not produce a glossary of mathematical concepts, though, which was our original goal.
   
   Such a glossary should be useful not only for NLI but also for math summarization, math question-answering, and to help formalization and informalization projects, amongst other projects.

   To quote from [Berlioz's phd thesis](https://d-scholarship.pitt.edu/43650/) (Pittsburgh 2022): "A major goal of the international math community is to obtain tools for the automated processing and
   transformation of mathematical documents. These tools do not currently exist in a satisfactory form, and extensive research is oriented towards improving this.
   [The Formal Abstracts Project aims to provide mathematicians with software tools for stating their research results in a human/machine readable format amenable to
   formal verification. In order to achieve this goal, the Formal Abstracts Project has recognized the need for
   (1) a comprehensive vocabulary of mathematics, in order to state research results, and for
   (2) improved automated reasoning tools to aid in processing and formally verifying those statements."

   We agree with the aims as stated above, but realize that the [Formal Abstracts project](https://github.com/formalabstracts/formalabstracts) has been dormant
   (if not dead) for the last seven years. Still, it resonates with us that something like "a comprehensive vocabulary of mathematics", enabling us to state research results, is required.

   But our spreadsheet depends not only of running our prompts in several LLMs, but also in describing and proving correct the other parts of the pipeline.
   For instance, there might be mistakes when mapping terms to Wikidata, both of not finding concepts that are there and also of finding wrong concepts with the same name,
   e.g. mapping into disambiguation pages in wikidata, or map "ring" algebraic structure to "ring" piece of jewelry.

   So we need to provide some metrics and measurements to show:
   1. LLMs mostly get good maht concepts;
   2. using the intersection of the outputs of LLMs is a good strategy (LLMs as judges)
   3. our pipeline is increasingly monotonic, adding more human-curated resources improves the quality of the proposed terms
   4. our terms have math definitions that make them unambiguous as much as possible
   5. we do not have wrong terms
   6. we have enoughgood terms
  
   Something along the lines of the 6 items above would guarantee a reasonable "comprehensive vocabulary" (with definitions a comprehensive glossary of mathematical terms).

    A posteriori verifications should also be done, comparing the terms obtained from our database with:
   1. the merger of all mathematical the glossaries from Wikipedia  (a smaller and possibly much easier project)
   2. MathGloss almost 5Kterms without definitions
   3. Wolfram MathWorld 13k concepts
  
2. #Trouver+KnowTex+LLMs

   
