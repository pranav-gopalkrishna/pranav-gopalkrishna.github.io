[<< Back to **Machine Learning**](https://pranav-gopalkrishna.github.io/machine-learning)

**ESSENTIALS OF ML**

---

**Contents**:

- [Introduction](#introduction)
- [Categories of ML tasks](#categories-of-ml-tasks)
- [Categories of ML approaches](#categories-of-ml-approaches)
  - [Supervised learning](#supervised-learning)
  - [Unsupervised learning](#unsupervised-learning)

---

# Introduction
ML is the science of automating the use of observations/data to improve a system's generalised ability to perform a task (and not just improve its immediate or short-term performance of the task). Hence, ML is concerned with making adaptations to improve its ability to deal with a sufficiently broad range of potential circumstances within the scope of the task. In short, ML is the science of automating learning within some context.

Learning has two defining questions: (1) what to learn, and (2) how to learn it. The answer to these questions are given by two elements: (1) the task, and (2) the approach. The task is a goal to be achieved. The approach is broad structure/framework (e.g. a set of principles, a set of heuristics, a model, etc.) based on which actions are taken. Hence, since ML is a form of learning, an application of ML is also defined by these two elements, namely the task and the approach. Let us now break these abstract elements into useful categories.

# Categories of ML tasks
Three broad categories of tasks that ML deals with are: (1) alteration, (2) abstraction and (3) adaptation. Let us start with alteration. Suppose the solution for a given task is represented by a [conceptual model](https://pranav-gopalkrishna.github.io/machine-learning/definitions.html#conceptual-model) defined by a set of parameters. Such a model identifies the key factors and features of the purposeful context, which are represented by the model's parameters, but the concrete natures of these factors and features, i.e. the concrete values these parameters, are unknown. Hence, the task amounts to altering the model's parameters based on what is observed/known.

Now, moving onto abstraction. Abstraction is the process of isolating parts of an input (e.g. an observation, a set of data points, etc.) from the input as a whole. This process is vital in distinguishing between parts of a whole, which in turn is vital in identifying how these parts relate to each other logically and causally and thereby make the whole what it is. Hence, this process is also vital in isolating the essentials of a context, e.g. the essential factors of an outcome, the essential features of a class of entities, etc. Hence, abstraction is indispensable to learning beyond the level of direct sense-perception and observation.

**NOTE**: _In alteration, the abstract solution is built into the approach before automating it, via the choice of model. However, the task of abstraction in ML is the automation of abstraction itself, which is not necessarily the automation of modelling but rather the automation of one or more of the steps needed for modelling. For example, abstraction could group data points into categories, which in turn could be used to recognise them as variables in a model._

Finally, we come to adaptation. Adaptation is the generalisation of alteration, which means adaptation is the process of a system/entity changing its approach to a task based on feedback (e.g. effects, rewards, punishments, etc.) on its actions from the environment. This change of approach could be in a narrower scope, as in alteration, or it could be broader, dealing not only with the values of a set of parameters of a model but with the choice of parameters or models themselves. Hence, we see that adaptation is the essence of learning from experience.

**NOTE**: _Since learning beyond direct sense-perception and observation needs abstraction, adaptation is often preceded by some form of abstraction, which may be done either by a human or by an automated system of abstraction or both (to varying degrees)._

# Categories of ML approaches
Learning could be approached with more or less clarity about the data used for learning, which corresponds to (1) [annotating](https://pranav-gopalkrishna.github.io/machine-learning/definitions.html#annotation) the data, and (2) not annotating the data. Also, learning could be approached with more or less clarity about the feedback on a learning system's performance, which corresponds to (1) giving feedback, (2) giving no feedback or (3) letting the task environment give the feedback. With these metrics, learning approaches can be categorised as follows: (1) supervised learning (annotated data with feedback given), (2) unsupervised learning (non-annotated data with no feedback given), and (3) reinforcement learning (letting the environment give the feedback; the data may be annotated or not).

Note that these categories are not arbitrary. Supervised learning is based on the need for automating the more monotonous aspect of problem-solving, i.e. alteration, while allowing humans to solve the more complex aspect. This approach leverages both the computational power of computers and the creative and intellectual power of human beings. Unsupervised learning is based on the need for processing a large amount of data for which annotation can be infeasible or even humanly impossible. Reinforcement learning is the approach that directly addresses the task of adaptation.

**NOTE**: _Can we have hybrid approaches? Indeed, we can. For example, we can use unsupervised learning to annotate data, which we can then supply to a supervised learning system. As another example, reinforcement learning can involve aspects of supervised learning (e.g. the use of annotated data, and the use of exact performance metrics derived from environmental feedback, as in deep Q-learning)._

## Supervised learning
"Supervised" refers to the facts that (1) the task is based on well-defined relationships (e.g. relationships of dependence between variables) and (2) the data used for learning is [annotated](https://pranav-gopalkrishna.github.io/machine-learning/definitions.html#annotation) (both facts implying that the learning is "supervised" by a third party). Examples of applications of supervised learning are:

| Input(s) | Output(s) |
| --- | --- | --- |
| Wages  | Revenue |
| Image | Label |
| Wind Speed, Cloud Cover, Temperature | Chance of Rain |
| Email | Spam/Not-Spam Tag |
| Song | Genre |

In general, a model us used to estimate the function mapping inputs to outputs, i.e. the target function; the **choice of model** deserves a discussion of its own. Given the model, the target function is estimated by optimising the model's parameters based on some metric of distance between observed and predicted outputs; the **choice of metric** also deserves a discussion of its own.

**NOTE**:

- Inputs are also called features, attributes, predictors or [covariates](https://www.statology.org/covariate/)
- Outputs are also called response variables or target variables
- If output is quantitative, problem is of regression
- If output is categorical, problem is of classification
- If output is ordinal, problem is of ordinal regression
- Metric used to optimise performance is called "objective function"

## Unsupervised learning
"Unsupervised" refers to the facts that (1) the task does not define any relationships between data points and (2) the data used for learning is not [annotated](https://pranav-gopalkrishna.github.io/machine-learning/definitions.html#annotation) (both facts implying that the learning is not "supervised" by another party). Relationships between data points may be implicit or explicit in the ML's output, i.e. the ML has to make decisions based on the observed similarities and differences, and these decisions would at least presuppose, if not posit, the relationships between the data points. Such problems may be of the following broad kinds, which shall be further explored later:

- Clustering (C)
- Association Rule Learning (ARL)
- Dimensionality Reduction (DR)

Examples of such problems:

| Data | Goal | Problem Type |
| --- | --- | --- |
| Images | _Grouping similar images_ | C |
| Customer Purchases | _Relating an item's sale to another's_ | ARL |
| Predictors | _Identify irrelevant predictors_ | DR |