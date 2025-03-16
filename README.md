# Network Mathematics.

Network Mathematics is a broad project to apply the modern tools of NLP and AI to the mathematical literature. That is to mathematics written in what is now called "informal" mathematics.

We're working on several subprojects: 

1. Parmesan, now called *Mathoscope*  is a math assistant website built mostly by Jacob Collard. See the math assistant at http://www.jacobcollard.com/parmesan2/
   The system uses corpora derived from TAC abstracts, the nLab and Tom Leinster's book "Basic Category Theory" BCT.
   
2. MathGloss is a multisource glossary of concepts in mathematics built mostly by Lucy Horowitz. (You can see the glossary at  https://mathgloss.github.io/MathGloss/database).
   The initial work was presented at a workshop associated with  CICM 2023, see also https://europroofnet.github.io/cambridge-2023/#horowitz. The preprint can be found at
   * [MathGloss: Building mathematical glossaries from text ](https://arxiv.org/abs/2311.12649), 2023 

3. MathAnnotator is a tool to help annotate math concepts in sentences. The tool is available at https://gaoq111.github.io/math_concept_annotation/.  Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.
  
4. We propose to NLP process, using spaCy, as many of the open-source maths books recommended by the AIM (American Institute of Mathematics)  in their [Open Textbook Initiative](https://textbooks.aimath.org/). This is work with Andrea Ferreira and others, see:
   *  [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF),  Hefferon
   *  [Abstract Algebra](https://github.com/andreago9/MathCorpus-AATA), Judson 
