# Network Mathematics.

Network Mathematics is a broad project to apply the modern tools of NLP and AI to the mathematical literature. That is to apply to mathematics written in what is now called "informal"  style, the tools of AI that would allow it to become "formal mathematics", mathematics as understood by "proof assistants" and "theorem provers".

We're working on several subprojects: 

1. Parmesan, now called *[Mathoscope](http://www.jacobcollard.com/mathoscope/)*,  is a math assistant website built mostly by Jacob Collard. 
   The system uses corpora derived from [TAC abstracts](https://github.com/ToposInstitute/tac-corpus), the [nLab](https://github.com/ToposInstitute/nlab-corpus), and Tom Leinster's book "Basic Category Theory" [(BCT)](https://github.com/ToposInstitute/CT-corpus).
   
   
3. [MathGloss](https://mathgloss.github.io/MathGloss/) is a multisource glossary of concepts in mathematics built mostly by Lucy Horowitz. (You can see the glossary at  https://mathgloss.github.io/MathGloss/database).
   The initial work was presented at a [workshop associated with  CICM 2023](https://europroofnet.github.io/cambridge-2023/#horowitz). The preprint can be found at
   * [MathGloss: Building mathematical glossaries from text ](https://arxiv.org/abs/2311.12649), 2023.
  
   MathGloss is also used in  [Towards Multilingual Autoformalization and Informalization of Mathematics](https://sltc2024.github.io/abstracts/ranta.pdf) by A. Ranta.

4. MathAnnotator is a tool to help annotate math concepts in sentences. The tool is available at https://gaoq111.github.io/math_concept_annotation/.  Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.
  
5. MathLit: we propose to NLP process, using spaCy or any other off-the-self system, as many of the open-source maths books recommended by the AIM (American Institute of Mathematics)  in their [Open Textbook Initiative](https://textbooks.aimath.org/). This is work with Andrea Ferreira and others, see:
   *  [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF),  Hefferon
   *  [Abstract Algebra](https://github.com/andreago9/MathCorpus-AATA), Judson
   *  [Discrete Mathematics: An Open Introduction](https://github.com/vcvpaiva/DMLevin), Levin
   *  [Compact Math Corpus](https://github.com/andreafer-uni/Compact-Math-Corpus)
