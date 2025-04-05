**STUDY SUMMARY**

---

**Contents**:

- [Areas of study](#areas-of-study)
  - [Artificial intelligence (AI)](#artificial-intelligence-ai)
  - [Computer science (CS)](#computer-science-cs)
  - [Mathematics (Ma)](#mathematics-ma)
  - [Statistics (St)](#statistics-st)
- [Summary of AI](#summary-of-ai)
- [Summary of CS](#summary-of-cs)
- [Summary of Ma](#summary-of-ma)

---

# Areas of study
## Artificial intelligence (AI)

- Machine learning (ML)
- Search methods (SeM)
- Interative agents (IA)
- Procedural content generation (PCG)

## Computer science (CS)

- Programming (Pr)
- Design and analysis of experiments (DAA)
- Digital computing fundamentals (DCF)
- Computer architecture and organisation (COA)
- Database management system (DBMS)
- Web development (WD)

## Mathematics (Ma)

- Calculus (Ca)
    - Differentiation (Di)
    - Integration (In)
    - Differential equations (DE)
- Real analysis (RA)
- Complex analysis (CA)
- Linear algebra (LA)
- Number theory (NT)

## Statistics (St)

- Descriptive statistics (DSt)
- Inferential statistics (ISt)
    - Hypothesis testing (HT)
    - Estimation (Es)
- Sampling methods (SaM)
- Linear regression (LR)

# Summary of AI
AI is the study of the automation of cognition and decision-making. It is an area within CS because it deals with computation, information and automation. Hence, AI extends CS to higher-level cognition and/or decision-making, and CS is the practical basis for AI. ML and SeM are the areas within AI that concern with automating cognition; ML is the study of automating a system's use of observations to improve its ability to deal with a given task, whereas SeM is the study of automating the exploration of a solution space. ML and SeM can be the basis for a decision-making system, but on their own, they are concerned more with cognitive tasks, e.g. classification, prediction, planning, etc. IA is the area within AI that concerns with automating decision-making. It may use ML and SeM, but it extends to other methods that combine perception of some form with decision-making of some form (e.g. behaviour trees, steering, etc.). PCG is the area within AI that concerns with automating content creation, which involves decision-making and possibly cognition. PCG based only on decision-making relies on algorithms and possibly random number generation (RNG), e.g. cellular automata, grammars, gradient noise, etc. PCG based on SeM and ML relies on learning from examples, feedback and/or the optimisation some metric by which solutions can be measured, e.g. generative adversarial networks (GANs), neural style transfer (NST), etc.

# Summary of CS
CS is the study of the automation of information processing, which means CS consists of computation and computation-driven action (note that computation refers to the evaluation of any well-defined arithmetic or logical statement). CS thus has the following major areas: (1) the study of how information is processed by a computer, (2) the study of how to define instructions and the order of their execution, and (3) the study of how to manage stored information.

These areas are covered as follows: For (1), DCF covers the mathematics and logical design for computation, and COA covers the design and details of the higher-level modules of a computer system and their relationships. For (2), programming covers the practicalities of implementing algorithms (an algorithm is a finite sequence of instructions that together perform a well-defined task within a finite amount of time), whereas DAA covers the theory behind the design of algorithms and the measurement of their performance. For (3), DBMS covers the theoretical and practical aspects of storing data in a well-organised and accessible system (i.e. a "database").

These areas together form the practical basis for the application and optimisation (in terms of performance) of AI architectures and algorithms. In particular, DBMS provides a basis for handling data, a key ingredient in ML, while programming provides a basis for handling the actual implementation of AI architectures and algorithms. DAA provides a basis to design and measure the performance of search algorithms (a key part of AI) and procedural generation algorithms.

# Summary of Ma
Ma is the science of measurement, i.e. the science that deals with quantities and their relationships. ML problems can often be broken down into quantitative problems, wherein measurements performed on or drawn from the data serve as the basis for analysing and interpreting the data. Hence, Ma becomes a crucial conceptual basis to solve ML problems. For neural networks in particular, which is essentially a way to approximate a complex function using a sequence of parallel linear operations followed by non-linear transformations, Ma becomes a means to represent and explain the network and its processes, such as the arrangement of weights (represented using matrices) and updation of weights.

In the case of more complex architectures such as convolutional neural networks, the transformation of the initial data into another more useful form (e.g. a form after feature extraction) is represented and explained using mathematical ideas such as convolution. In data analytics and data science, which combines statistics with computer science, mathematics contributes to both the statistical side and the computational side, since statistics is mathematics applied to data, and computation brings with it algorithmic and optimisation problems that can often be understood, analysed and solved using mathematics (e.g. evaluating an algorithm's performance, measuring the effect of a proposed data storage and retrieval architecture, etc.).