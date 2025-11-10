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
     

## MathGloss

MathGloss is a multi-source glossary of mathematical concepts, built primarily by Lucy Horowitz.
Explore it at [mathgloss.github.io/MathGloss/database](https://mathgloss.github.io/MathGloss/)
   
The project was first presented at a CICM 2023 workshop; see the preprint:

* MathGloss: [Building Mathematical Glossaries from Text](), L. Horowitz, V. de Paiva, 2023

(Video presentation: Lucy Horowitz, [MathGloss and Beyond](https://www.youtube.com/watch?v=GklBiBEfblg), Hausdorff Institute, July 15, 2024.)

MathGloss has since been used in:

* [Towards Multilingual Autoformalization and Informalization of Mathematics](https://sltc2024.github.io/abstracts/ranta.pdf), A. Ranta, 2024.

* [AutoMathKG: The Automated Mathematical Knowledge Graph Based on LLM and Vector Database](https://arxiv.org/abs/2505.13406), R. Bian et al., 2025

## MathAnnotator

MathAnnotator is a web-based tool for manually annotating mathematical concepts in text, developed with Larry Moss, Qiyue (Bert) Gao, and Pavel Kovalev.
Try it at [https://gaoq111.github.io/math_concept_annotation/](https://gaoq111.github.io/math_concept_annotation/).

   Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.

## MathNLI

MathNLI explores Natural Language Inference (NLI) over mathematical text.
It extends earlier work on NLI for everyday language, in collaboration with Katerina Kalouli, Larry Moss, Hai Hu, and Alex Webb ([Curing the SICK and Other NLI Maladies](https://direct.mit.edu/coli/article/49/1/199/113488/Curing-the-SICK-and-Other-NLI-Maladies), 2023).

Our new preprint:

* Math Natural Language Inference: This Should Be Easy!, V. de Paiva, Q. Gao, H. Hu, P. Kovalev, Y. Liu, L. S. Moss, Z. Qian, 2025 ([arXiv](https://arxiv.org/pdf/2507.23063))

has been presented at STARSEM 2025.
     
   
## MathLit

MathLit aims to process open-source mathematics textbooks—especially those recommended by the American Institute of Mathematics (AIM) Open Textbook Initiative—using NLP pipelines such as spaCy.

Current materials include:

* [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF), Hefferon

* [Abstract Algebra](), Judson

* [Discrete Mathematics: An Open Introduction](https://github.com/vcvpaiva/DMLevin), Levin


Meanwhile, a different kind of effort is presented by Andrea Ferreira in 

   *  [Compact Math Corpus](https://github.com/andreafer-uni/Compact-Math-Corpus).
     
See her NALOMA [preprint](https://naloma.github.io/2025/papers/paper-5.pdf) 
