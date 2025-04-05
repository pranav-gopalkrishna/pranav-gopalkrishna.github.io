[<< Back to **Machine Learning**](https://pranav-gopalkrishna.github.io/machine-learning)

**SUPERVISED LEARNING MODELS**

---

**Contents**:

- [Introduction](#introduction)
- [Model parameter](#model-parameter)
- [Function approximation models](#function-approximation-models)
- [Decision-making models](#decision-making-models)

---

# Introduction

A conceptual model is a sufficiently abstract and useful representation of an entity or system. Here, "abstract" means only relevant details are held and irrelevant details are omitted. Note that "relevance" and "sufficiency" is with respect to the given context and purpose. Hence, _a conceptual model is a useful essentialisation of an entity or a system_. A learning model is a conceptual model for which one or more parameters are to be optimised according to observed data. A supervised learning model is a learning model that needs unambiguous labels for the variables whose values it has to predict (target variables) given the values of a set of relevant (or potentially relevant) variables (feature/predictor variables).

# Model parameter
Given a context (which involves a purpose and a set of constraints), a parameter of a model is an attribute of the model that is variable in the given context. An attribute of the model that is constant in the given context is not a parameter for the given context. In short, a "parameter" is identified with respect to a given context, and an attribute is a parameter only if it is variable in the given context. For example, when the purpose is to optimise a neural network for the given data, the parameters are the network's weights and biases. However, when the purpose is to optimise the architecture of the neural network for the given domain, the parameters are the number of layers, the number of neurons per layer, the activation functions, etc. (which are taken as constant in the first case). Lastly, for ease of reference, note that a parameter may be simple (i.e. scalar) or composite (i.e. a tuple/vector of simple parameters).

# Function approximation models
These are supervised learning models whose goal is to approximate the function that describes relationship (omitting the effect of noise) between the independent and dependent attributes of the observed data points. To elaborate, in most cases, there exist practically unaccountable factors that affect the data points probabilistically; the learning model's goal is to omit the effect of such factors and focus on the relationship between the independent and dependent attributes.

---

Some function approximation learning models:

- Linear regression model
- Polynomial regression model
- Logistic regression model
- Mixture of Gaussians
- Neural network

# Decision-making models
These are supervised learning models whose goal is to optimise decision-making parameters, i.e. parameters that affect condition-based choices of actions or outcomes.

- Decision tree
- Random forest