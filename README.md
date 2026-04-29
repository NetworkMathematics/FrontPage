# Network Mathematics

![a joke map of math](https://github.com/NetworkMathematics/FrontPage/blob/main/Mathematistan.jpg "Mathematistan")

## Building the Data Infrastructure for Mathematical Knowledge

The Network Mathematics project addresses a central gap in the scientific data ecosystem: the absence of a unified, open, machine-readable hub connecting and structuring mathematical knowledge.

Mathematics underpins every area of science, yet its knowledge remains fragmented across disconnected resources. High-quality efforts such as [Code4Math](https://code4math.org/), [Lean Mathlib](), [nLab](), L-Functions and Modular Forms Database [(LFMDB)](), [Stacks Project](), [OEIS](), and many others, provide essential pieces of the puzzle, but they operate in isolation. Formal libraries, computational databases, and expository texts each capture different aspects of mathematics, with no shared semantic layer linking them.

Network Mathematics is a call to build that layer.

The project develops methods to extract, represent, and interconnect mathematical concepts, statements, and arguments as a structured network derived from existing corpora. It combines:

* large-scale natural language processing of mathematical texts,
* knowledge graph construction capturing dependencies and conceptual structure, and
* category-theoretic principles to organize and relate these structures in a coherent way.

The aim is not to replace existing systems, but to make them interoperable: to connect informal exposition, formal proof libraries, and specialized databases into a shared, machine-accessible framework.

This need is already being recognized internationally. The [Mathematical Research Data Initiative (MaRDI)](https://www.mardi4nfdi.de/about/mission), part of Germany’s NFDI program, is developing research data infrastructure for mathematics. The Hausdorff Institute Trimester Program on [Prospects of Formal Mathematics](ww.mathematics.uni-bonn.de/him/programs/past/him-trimester-program-prospects-of-formal-mathematics) has further highlighted the convergence of formalization, computation, and mathematical practice as a defining direction for the field.

What is still missing is a unifying semantic layer that connects these efforts and makes their knowledge usable at scale.

In this emerging ecosystem, Code4Math provides a vital community hub linking mathematicians, developers, and open-source projects. Network Mathematics complements this by providing the data backbone: a structured, interoperable representation of mathematical knowledge on which tools, visualizations, and AI systems can be built.

A first step in this direction is [MathGloss](https://mathgloss.github.io/MathGloss/), an open, structured glossary of mathematical concepts designed as a seed dataset. The broader goal is to scale from glossaries to full corpora, capturing not only definitions but also the logical, conceptual, and argumentative structure of mathematics.

The opportunity is clear.
Just as curated datasets enabled breakthroughs in structural biology, a coordinated effort to build open, structured mathematical knowledge infrastructure can unlock the next generation of AI-assisted discovery across science.

Network Mathematics is an invitation to build this infrastructure—collaboratively, openly, and at scale.

## What have we done so far?

Network Mathematics is an ambitious project that applies modern tools from Natural Language Processing (NLP) and Artificial Intelligence (AI) to the mathematical literature. The goal is to bridge the gap between informal mathematics—as written in papers, textbooks, and lecture notes—and formal mathematics, as represented in proof assistants and theorem provers. In short, we aim to help machines read and reason about mathematics written in natural language.
(Some early thoughts about the project can be found in older [blog posts](https://github.com/NetworkMathematics/FrontPage/blob/main/blogposts.md).)

We are developing several interconnected subprojects, see below. For a brief overview, see the [slides](https://github.com/NetworkMathematics/FrontPage/blob/main/NetMath2.pdf) (March2026).

## 1. Mathoscope (formerly Parmesan)

Mathoscope is a mathematical assistant and knowledge graph project under development since 2021. It draws on corpora derived from Theory and Applications of Categories (TAC) abstracts, the nLab, and books, including Tom Leinster’s Basic Category Theory.
The project has been presented in a COLING paper and three preprints under its original name, Parmesan:

* [Mathematical Entities: Corpora and Benchmarks](https://aclanthology.org/2024.lrec-main.966.pdf), J. Collard, V. de Paiva, E. Subrahmanian, LREC-COLING, 2024
* [Parmesan: Mathematical Concept Extraction for Education](https://arxiv.org/abs/2307.06699), J. Collard, V. de Paiva, E. Subrahmanian, 2023
* [Extracting Mathematical Concepts from Text](https://aclanthology.org/2022.wnut-1.2/), J. Collard, V. de Paiva, B. Fong, E. Subrahmanian, W-NUT, 2022

Videos: [LREC](https://www.youtube.com/watch?v=n_5U5Dyy-8M&t=14s) |   [W-NUT](https://www.youtube.com/watch?v=-ZhZjMn1Zpk)

The data from the project is  distributed into github repos:
* [Mathoscope](https://github.com/ToposInstitute/mathscope), 
* [TAC-corpus](https://github.com/ToposInstitute/tac-corpus), 
* [nLab_corpus](https://github.com/ToposInstitute/nlab-corpus), and 
* [Parmesan_benchmarks](https://github.com/ToposInstitute/parmesan_benchmarks).

Ongoing: Working now (Mar 2026) on a (smallish) knowledge graph from Mathoscope. 
Jacob to  provide data and first write-up with the new name.
     

## 2. MathGloss

MathGloss is a multi-source glossary of mathematical concepts, built primarily by Lucy Horowitz.

Explore it by yourself at [mathgloss.github.io/MathGloss/database](https://mathgloss.github.io/MathGloss/)!
   
Some presentations:  
* The project was first presented at a CICM 2023 workshop, see the preprint [Building Mathematical Glossaries from Text](https://arxiv.org/abs/2311.12649), L. Horowitz, V. de Paiva, 2023
* Video presentations: Lucy Horowitz, [MathGloss and Beyond](https://www.youtube.com/watch?v=GklBiBEfblg), Hausdorff Institute, July 15, 2024.
* Valeria de Paiva: [AI tools for Better Math](https://www.youtube.com/watch?v=C7NBGlJb2DQ),  Hausdorff Institute, Jul 2024.
* Lucy Horowitz (slides at [ALIGN2025](https://sites.google.com/view/align2025/welcome)): [Extending MathGloss](https://drive.google.com/file/d/1J780ImPxonODvDGyeU1Z77jWv-AKMLLb/view) Oct, 2025.

MathGloss has been used in (at least):
* [Towards Multilingual Autoformalization and Informalization of Mathematics](https://sltc2024.github.io/abstracts/ranta.pdf), A. Ranta, 2024.
* See also [Symbolic Informalization: Fluent, Productive, Multilingual](https://aitp-conference.org/2025/abstract/AITP_2025_paper_4.pdf), AITP 2025.
* [AutoMathKG: The Automated Mathematical Knowledge Graph Based on LLM and Vector Database](https://arxiv.org/abs/2505.13406), R. Bian et al., 2025

Ongoing: Need to produce a new write-up as MathGloss has grown from ~1700 concepts to almost 5K.

## 3. MathAnnotator

MathAnnotator is a web-based tool for manually annotating mathematical concepts in text, developed with Larry Moss, Qiyue (Bert) Gao, and Pavel Kovalev.
Try it at [https://gaoq111.github.io/math_concept_annotation/](https://gaoq111.github.io/math_concept_annotation/).

   Our preprint is:
   * [Extracting Mathematical Concepts with Large Language Models](https://arxiv.org/pdf/2309.00642) CEUR Workshop Proceedings (CEUR-WS.org), 2023.

## 4. MathNLI

MathNLI explores Natural Language Inference (NLI) over mathematical text.
It extends earlier work on NLI for everyday language, in collaboration with Katerina Kalouli, Larry Moss, Hai Hu, and Alex Webb ([Curing the SICK and Other NLI Maladies](https://direct.mit.edu/coli/article/49/1/199/113488/Curing-the-SICK-and-Other-NLI-Maladies), 2023).

Our new preprint:

* [Math Natural Language Inference: This Should Be Easy!](https://arxiv.org/pdf/2507.23063), V. de Paiva, Q. Gao, H. Hu, P. Kovalev, Y. Liu, L. S. Moss, Z. Qian, 2025 (arXiv)

has been presented at [STARSEM 2025](https://starsem2025.github.io/schedule) by Yikang Liu. The poster is [here](https://github.com/NetworkMathematics/FrontPage/blob/main/MathNLI%20Poster-1.pdf). The data is in this [repo](https://github.com/MathNLI/MathNLI).
     
   
## 5. MathLit

MathLit aims to process open-source mathematics textbooks—especially those recommended by the American Institute of Mathematics (AIM) [Open Textbook Initiative](https://textbooks.aimath.org/)—using NLP pipelines such as spaCy or UDpipe.

Current materials include:

* [Linear Algebra](https://github.com/andreago9/MathCorpus-LAHefferonPDF), Hefferon

* [Abstract Algebra](), Judson

* [Discrete Mathematics: An Open Introduction](https://github.com/vcvpaiva/DMLevin), Levin


Meanwhile, a different kind of effort is presented by Andrea Ferreira in 

   *  [Compact Math Corpus](https://github.com/andreafer-uni/Compact-Math-Corpus).
     
See her NALOMA [preprint](https://naloma.github.io/2025/papers/paper-5.pdf) 

## 6. KnowTex

KnowTex (created by [Elif Uskuplu](https://elifuskuplu.github.io/)) is a python package that helps us graph the logical structure  of mathematical papers.
The system was presented in the workshop ALIGN2025, slides are [here](https://drive.google.com/file/d/1Nl6Fgl88tLSnqWFPGdcb814WMOytv_TX/view?usp=sharing) and the code is [here](https://github.com/ElifUskuplu/KnowTex).

Our arxiv preprint [KnowTex: Visualising Mathematical Dependencies](https://github.com/NetworkMathematics/FrontPage/blob/main/KnowTexProject-1.pdf), Jan 2026.


