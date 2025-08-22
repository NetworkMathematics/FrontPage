# Network Mathematics.

Network Mathematics is a broad project to apply the modern tools of NLP and AI to the mathematical literature. That is to apply to mathematics written in what is now called "non-formal"  style, the tools of AI that would allow it to become "formal mathematics", mathematics as understood by "proof assistants" and "theorem provers".

We're working on several subprojects: 

1. Parmesan, now called *[Mathoscope](http://www.jacobcollard.com/mathoscope/)*,  is a math assistant website built mostly by Jacob Collard. 
   The system uses corpora derived from [TAC abstracts](https://github.com/ToposInstitute/tac-corpus), the [nLab](https://github.com/ToposInstitute/nlab-corpus), and Tom Leinster's book "Basic Category Theory" [(BCT)](https://github.com/ToposInstitute/CT-corpus). We have a [COLING paper]() and three preprints on this work, using the old name.
   * [Mathematical Entities: Corpora and Benchmarks](https://arxiv.org/pdf/2406.11577) J Collard, V de Paiva, E Subrahmanian
   * [Parmesan: mathematical concept extraction for education](https://arxiv.org/pdf/2307.06699) J Collard, V de Paiva, E Subrahmanian, 2023
   * [Extracting mathematical concepts from text](https://arxiv.org/pdf/2208.13830), J Collard, V De Paiva, B Fong, E Subrahmanian, 2022
   
3. [MathGloss](https://mathgloss.github.io/MathGloss/) is a multisource glossary of concepts in mathematics built mostly by Lucy Horowitz. (You can see the glossary at  https://mathgloss.github.io/MathGloss/database).
   The initial work was presented at a [workshop associated with  CICM 2023](https://europroofnet.github.io/cambridge-2023/#horowitz). The preprint can be found at
   * [MathGloss: Building mathematical glossaries from text ](https://arxiv.org/abs/2311.12649), 2023.
  
   MathGloss was used in  [Towards Multilingual Autoformalization and Informalization of Mathematics](https://sltc2024.github.io/abstracts/ranta.pdf) by A. Ranta.

4. MathAnnotator is a tool to help annotate math concepts in sentences. This is work with Larry Moss, (Bert) Qiyue Gao, and Pavel Kovalev.
   The tool is available at https://gaoq111.github.io/math_concept_annotation/.  Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.
     
6. MathNLI is a project to use Natural Language Inference over mathematical texts. This builds on work with Larry Moss, Hai Hu, and Katerina Kalouli on NLI for everyday language.
   * Our new preprint [Math Natural Language Inference: this should be easy!](https://arxiv.org/pdf/2507.23063) by V de Paiva, Q Gao, H Hu, P Kovalev, Y Liu, LS Moss, Z Qian is now on the arxiv
   
7. MathLit: we propose to NLP-process, using spaCy or any other off-the-shelf system, as many of the open-source maths books recommended by the AIM (American Institute of Mathematics)  in their [Open Textbook Initiative](https://textbooks.aimath.org/) as possible. This is work with Andrea Ferreira and others, see:
   *  [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF),  Hefferon
   *  [Abstract Algebra](https://github.com/andreago9/MathCorpus-AATA), Judson
   *  [Discrete Mathematics: An Open Introduction](https://github.com/vcvpaiva/DMLevin), Levin
   *  [Compact Math Corpus](https://github.com/andreafer-uni/Compact-Math-Corpus), new [preprint](https://naloma.github.io/2025/papers/paper-5.pdf)! Aug 2025
