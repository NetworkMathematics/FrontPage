# Network Mathematics.

Network Mathematics is an ambitious project that applies modern tools from Natural Language Processing (NLP) and Artificial Intelligence (AI) to the mathematical literature. The goal is to bridge the gap between informal mathematics—as written in papers, textbooks, and lecture notes—and formal mathematics, as represented in proof assistants and theorem provers. In short, we aim to help machines read and reason about mathematics written in natural language.
(Some early thoughts about the project can be found in older blog posts.)

We are developing several interconnected subprojects:

## Mathoscope (formerly Parmesan)

Mathoscope is a mathematical assistant and knowledge graph project under development since 2021. It draws on corpora derived from Theory and Applications of Categories (TAC) abstracts, the nLab, and Tom Leinster’s Basic Category Theory.
The project has been presented in a COLING paper and three preprints under its original name, Parmesan:

* Mathematical Entities: Corpora and Benchmarks, J. Collard, V. de Paiva, E. Subrahmanian, 2024

* Parmesan: Mathematical Concept Extraction for Education, J. Collard, V. de Paiva, E. Subrahmanian, 2023

* Extracting Mathematical Concepts from Text, J. Collard, V. de Paiva, B. Fong, E. Subrahmanian, 2022

Videos: [LREC](https://www.youtube.com/watch?v=n_5U5Dyy-8M&t=14s) |   [W-NUT](https://www.youtube.com/watch?v=-ZhZjMn1Zpk)
     

   
   
2. [MathGloss](https://mathgloss.github.io/MathGloss/) is a multisource glossary of concepts in mathematics built mostly by Lucy Horowitz. (You can see the glossary at  https://mathgloss.github.io/MathGloss/database).
   The initial work was presented at a [workshop associated with  CICM 2023](https://europroofnet.github.io/cambridge-2023/#horowitz). The preprint can be found at
   * [MathGloss: Building mathematical glossaries from text ](https://arxiv.org/abs/2311.12649), L Horowitz, V de Paiva, 2023.
  
(video presentation at Hausdorff Institute, Lucy Horowitz, Jul 15, 2024 [MathGloss and Beyond](https://www.youtube.com/watch?v=GklBiBEfblg))
  
   MathGloss was used in
   * [Towards Multilingual Autoformalization and Informalization of Mathematics](https://sltc2024.github.io/abstracts/ranta.pdf) by A. Ranta.
   * [AutoMathKG: The automated mathematical knowledge graph based on LLM and vector database](https://arxiv.org/abs/2505.13406) by R. Bian et al.

3. MathAnnotator is a tool to help annotate math concepts in sentences. This is work with Larry Moss, (Bert) Qiyue Gao, and Pavel Kovalev.
   The tool is available at https://gaoq111.github.io/math_concept_annotation/.
   Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.
     
4. MathNLI is a project to use Natural Language Inference over mathematical texts. This builds on work with Katerina Kalouli, Larry Moss, Hai Hu, and Alex Webb on NLI for everyday language, see [Curing the SICK and other NLI maladies](https://direct.mit.edu/coli/article/49/1/199/113488/Curing-the-SICK-and-Other-NLI-Maladies), 2023.
   * Our new preprint [Math Natural Language Inference: this should be easy!](https://arxiv.org/pdf/2507.23063) by V de Paiva, Q Gao, H Hu, P Kovalev, Y Liu, LS Moss, Z Qian is now on the arxiv
   
5. MathLit: we propose to NLP-process, using spaCy or any other off-the-shelf system, as many of the open-source maths books recommended by the AIM (American Institute of Mathematics)  in their [Open Textbook Initiative](https://textbooks.aimath.org/) as possible. This is work with Andrea Ferreira and others, see:
   *  [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF),  Hefferon
   *  [Abstract Algebra](https://github.com/andreago9/MathCorpus-AATA), Judson
   *  [Discrete Mathematics: An Open Introduction](https://github.com/vcvpaiva/DMLevin), Levin
   *  [Compact Math Corpus](https://github.com/andreafer-uni/Compact-Math-Corpus), new [preprint](https://naloma.github.io/2025/papers/paper-5.pdf)! Aug 2025
