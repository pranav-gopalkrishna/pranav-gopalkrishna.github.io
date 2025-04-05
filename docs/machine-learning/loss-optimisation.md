<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Machine Learning**](https://pranav-gopalkrishna.github.io/machine-learning)

**LOSS OPTIMISATION**

---

**Contents**:

- [Loss function](#loss-function)
- [Gradient descent](#gradient-descent)
  - [Step-size for gradient descent](#step-size-for-gradient-descent)
  - [Convergence, divergence and oscillation of the loss function](#convergence-divergence-and-oscillation-of-the-loss-function)
  - [Issues with gradient descent](#issues-with-gradient-descent)
  - [Training epochs and batch-size](#training-epochs-and-batch-size)

---

# Loss function
**_Also called "cost function"_**

_First, some definitions_...

**Loss, cost and error**:

The terms "loss", "cost" and "error" are closely related, each referring to inaccuracy. However, each term also emphasises a particular aspect of inaccuracy. "Loss" refers to the loss of accuracy (with respect to an ideal model) when using the given model. Also, naturally, "loss" is used to refer to a value returned by a loss function. "Cost" refers to the penalty the model received due to inaccuracy. "Error" refers to inaccuracy in a more direct sense. For the sake of clarity, I shall use the term "inaccuracy", and I shall use "loss", "cost" and "error" where emphasis is needed on a particular aspect of the model's inaccuracy. However, note that the term "error" may be more widely used in other literature.

**Absolute and local minimum of a function**:

The absolute minimum of a function is its minimum value; the absolute minimum is also called the global minimum. A local minimum of a function $f$ of a variable $x$ is the minimum value of $f$ within some neighbourhood of $x$-values. Note also that $f$ may hit its absolute and/or local minima at more than one $x$-value. Furthermore, note that $f$ may have only one absolute minimum, or it may have one or more local minima but no absolute minimum, or it may have no minima at all. Finally, note that by definition, an absolute minimum is also a local minimum for any neighbourhood of $x$-values.

---

_Back to the discussion_...

An objective function is a metric that measures the performance of a learning model. A loss function is an objective function that measures the deviation of the learning model's outputs — also called predicted outputs — from the expected outputs; in other words, it measures the level of inaccuracy in the learning model's outputs. Importantly, note that "inaccuracy" does not mean "distance" (although they are synonymous in some contexts). To elaborate, the loss function is a measure of inaccuracy and not necessarily a measure of distance (though it can be in some contexts), since unlike a measure of distance, a loss function may be asymmetric, where the direction of deviation from the expectation is relevant. Furthermore, a symmetric loss function is also not necessarily a measure of distance (though it can be in some contexts), since it may not satisfy the triangle inequality (which must be satisfied by a measure of distance, as shown here: [_Distance Functions, Metrics_ from **mathresearch.utsa.edu**](https://mathresearch.utsa.edu/wiki/index.php?title=Distance_Functions,_Metrics)).

As a measure of inaccuracy, the loss function must be such that if the learning model gives the expected output, the loss function returns zero since there is no inaccuracy. Evidently, a loss function must be minimised to optimise the model's performance, with the absolute minimum of the loss function being zero. Furthermore, the loss must be proportional to the significance in the deviation of predicted outputs from expected outputs. "Significance" is not necessarily about numerical distance; it may be so, such as in regression, but, depending on the problem, it can also be about other metrics, such as a binary "true-or-false" value (e.g. in classification), the ordinal distance (e.g. in grading) or a domain-specific consideration (e.g. in musical key recognition, where, for instance, predicting the relative minor of the expected key is a less significant inaccuracy than predicting the major third).

# Gradient descent
_First, some definitions_...

**Simple and composite parameters**:

As an aside, note that a parameter may be simple (i.e. a scalar quantity) or composite (i.e. a vector quantity, i.e. an ordered set of simple parameters). In particular, when I say "learning model's parameter", the parameter in question may be simple or composite. In case of a composite parameter, it would be as valid to speak of the learning model's _parameters_ (plural) as it would be to speak of the learning model's _parameter_ (singular). However, for clarity, I shall stick to the singular, taking it for granted that it may be simple or composite. Furthermore, the meaning of "value" for a parameter depends on the parameter's nature; for a simple parameter, "value" refers to a scalar, while for a composite parameter, "value" refers to a vector.

**Derivative and gradient**:

A derivative represents the rate at which a function changes with respect to one variable. Hence, in a multi-variable function, the partial derivative of the function with respect to a given variable is a scalar that gives the rate of change (increase or decrease) in the function's value due to change in the variable's value. The gradient of a function is a vector of all the function's partial derivatives with respect to each variable. Hence, in a single-variable function, the gradient is just the derivative, but in a multi-variable function, the gradient is a vector that gives the direction of the steepest rate of increase of the function, i.e. it gives the direction in which each of the function's variables must be changed _together_ to achieve the steepest increase in the function's value. Thus, evaluating the gradient at a point (i.e. at a given tuple of values of the function's variables) gives the direction at that point, and its magnitude gives the rate of steepest ascent at that point.

In more precise terms, given a multi-variable function $f$, the gradient of $f$, denoted as $\nabla f$, is the vector of the first-order partial derivatives of $f$. In other words, if $f$ is defined by the variables $x_1, x_2 ... x_k$, then $\nabla f = (\frac{\delta f}{\delta x_1}, \frac{\delta f}{\delta x_2} ... \frac{\delta f}{\delta x_k})$. At a given point $(x_1, x_2 ... x_k)$ $=$ $(c_1, c_2 ... c_k)$ (where $c_1, c_2 ... c_k$ are constants), the gradient $\nabla f$ is such that $(x_1, x_2 ... x_k) + \alpha \nabla f$ gives a new point...

$$
(x_1 + \alpha \frac{\delta f}{\delta x_1}, x_2 + \alpha \frac{\delta f}{\delta x_2} ... x_k + \alpha \frac{\delta f}{\delta x_k})
$$

... which, when $f$ is plugged into it, gives the steepest increase in $f$ for a sufficiently small constant $\alpha$. The phrase "sufficiently small constant" is used because a gradient of a function only gives the direction of steepest ascent at the given point; in practice, this gives the direction of steepest ascent for a small neighbourhood around the given point. Thus, a gradient can reliably inform only about the steepest ascent of the function's value _for a small neighbourhood around a given point, i.e. for a small range of values of the function's variables_.

---

_Back to the discussion_...

The observed input and output data are constant with respect to the learning model; after all, they are reference points to which the learning model must adapt its parameters. Thus, in the context of optimising a learning model, the observed data is constant and the learning model's parameter is a variable, which means the predicted output, being a function of the learning model's parameter, is also a variable.

For convenience, let $W$ denote the learning model's parameter, and let $L$ denote the loss function. Now, $L$ is a function of the predicted output, which in turn is a function of $W$. Hence, if $L$ is differentiable with respect to $W$, then the gradient of $L$, i.e. $\nabla L$ can also be evaluated. If $L$ is a single-variable function, i.e. if $W$ is a simple parameter, then the gradient $\nabla L$ is just the derivative $\frac{dL}{dW}$, i.e. the rate of change in the loss function's value due to change in the variable's value. If $L$ is a multi-variable function, i.e. if $W$ is a composite parameter such that $W = (W_1, W_2 ... W_k)$, then the gradient $\nabla L$ is the vector of partial derivatives $(\frac{\delta L}{\delta W_1}, \frac{\delta L}{\delta W_2} ... \frac{\delta L}{\delta W_k})$. Hence, in either case, using the gradient $\nabla L$, we can know how to change $W$ so as to increase or decrease $L$; adding the gradient leads to increase, subtracting it leads to decrease. Thus, gradients can be used to optimise $W$ so as to minimise $L$.

Furthermore, we know that $L$ has its absolute minimum as zero. Thus, for at least some neighbourhood of points (i.e. values of $W$) around the point at the minimum, $L$ has gradients leading away from zero, which means for the same inverval of points, the negative gradients lead toward zero, i.e. toward the minimum. I say "for at least some neighbourhood", because more complex loss functions may have local minima on either side of the absolute minimum. Nonetheless, using $\nabla L$, $L$ is decreased by subtracting a sufficiently small multiple of $\nabla L$ from $W$. Hence, the idea is to use the gradient to descend toward to minimum of the loss function, thus the name "gradient descent". The logic of gradient descent is intuitive when applied to $W$ when $W$ is a simple parameter (i.e. a scalar variable), but its logic does not rely on $W$ being a simple parameter and thus also applies to $W$ when $W$ is a composite parameter (i.e. a vector variable).

The phrase "sufficiently small multiple of $\nabla L$" is used for same reason as given in the note on derivatives and gradients. To put it briefly, the gradient can reliably inform only about the steepest ascent of the function's value _for a small neighbourhood around a given point, i.e. for a small range of values of the function's variables_. Now, also note that if $L$ has one or more mimima (local and/or absolute), then, while the gradients point to some minimum, this minimum may be local or absolute. Hence, gradient descent has two key areas of uncertainty: (1) whether the step-size works for gradient descent, and (2) whether the minimum reached is local or absolute.

## Step-size for gradient descent
To resolve the issue of step-size, note that if a function has an absolute minimum, then it may be assumed that the greater the derivative, the further the variable's value is from its value at the function's minimum; here, it is reasonable to change the variable with a greater step-size. On the other hand, it may be assumed that the smaller the derivative, the closer the variable's value is from the function's value at the minimum; here, it is reasonable to change the variable with a smaller step-size. Hence, keeping the step-size proportional to the partial derivatives of the function with respect to each variable is a reasonable approach. In other words, we shall keep the step-size proportional to the gradient.

However, the raw values of the partial derivatives may prove to be too great, thus more likely to overshoot the absolute minimum, or too small, thus more likely to get stuck at a local minimum. Hence, a constant can be used to scale the gradient to a size that works; in the context of optimising the parameter $W$ by minimising the loss function $L$, this constant is called the learning rate. To understand the name, note that within a range of values, increasing or decreasing the learning rate would increase or decrease the speed at which $L$ converges to its minimum, which corresponds to the speed at which the learning model learns to perform with more accuracy. However, in the basic form of gradient descent, the choice of this constant may need trial-and-error.

In summary, for a good learning rate $\alpha$ , $L$ is minimised by updating $W$ as follows (the same mathematical form would apply for $W$ as a simple parameter and a complex parameters): $W \leftarrow W - \alpha \nabla L$. Here, $\nabla L$ ensures proportionality with the magnitude of the gradient, whereas $\alpha$ ensures that the step-size is sufficiently small. Together, they become $\alpha \nabla L$, i.e. they become the step-size that is proportional to the gradient but that is scaled so that is more likely to converge to the absolute minimum. Importantly, $\alpha$, being the scaling factor, must be positive, i.e. $\alpha > 0$.

## Convergence, divergence and oscillation of the loss function
If the gradient descent overshoots the minimum, then gradient descent is so designed that in the next iteration, it reverses its direction so that it is again directed toward the minimum. Even so, it can still overshoot the minimum again, leading to a sort of swinging effect. If an overshoot is such that the magnitude of the new position's gradient is lesser than that of the old position, then, since the step-size is proportional to the gradient (and thus proportional to the magnitude of the gradient), the next overshoot (if it happens) would be smaller due to a smaller step-size. Here, the "swings" of the gradient descent tend to get ever smaller, thus tending to converge to the minimum.

Evidently, then, if the overshoot is such that the magnitude of the new position's gradient is greater than that of the old position, the "swings" of the gradient descent tend to get ever larger, thus tending diverging to infinity. Lastly, if overshoot is such that the magnitude of the new position's gradient is equal than that of the old position, the "swings" tend to oscillate, thus tending never to converge or diverge.

## Issues with gradient descent
In its basic form, gradient descent has the following issues: (1) there is no rigorous way to choose a good learning rate (let alone the optimal learning rate), and (2) even with the optimal learning rate, gradient descent can at most ensure convergence to a local minimum and has no way of ensuring convergence to the absolute minimum. Issue (2) implies that the results of gradient descent can be sensitive to the gradient descent's initial point (i.e. initial value of $W$). Hence, a way to mitigate issue (2) is to re-run gradient descent for many unique re-initialisations of $W$ and then choose the all-time best value of $W$. However, there are modifications to the basic idea of gradient descent that help mitigate one or more of gradient descent's issues:

- Momemtum-based gradient descent (helps overcome local minima)
- Adapative gradient descent (adapts learning rate automatically)

## Training epochs and batch-size
Given a dataset $D = \Set{(x_1, y_1), (x_2, y_2) ... (x_n, y_n)}$ of inputs $x = (x_1, x_2 ... x_n)$ and outputs $y = (y_1, y_2 ... y_n)$, an epoch is the step that consists of updating the learning model's parameter for each input-output pair exactly once; in other words, optimising for an epoch is learning from each data point exactly once. Thus, an epoch is a unit of measurement for the amount of learning updates. The batch-size is the number of data points whose gradients are averaged before updating the learning model's parameter using the average gradient. A batch-size of one means the learning model updates its parameter for each data point separately, whereas a batch-size of $b>1$ means the learning model updates its parameter for $b$ data points together.

Averaging the gradients of a number of data points means that noise or insignificant crests and troughs in the loss function are glossed over, thereby making the gradient descent more stable and less prone to unnecessary or unhelpful updates. However, if the batch-size is too large, then gradient descent is likely to average over gradients of disparate data points such that the contribution of these data points on learning is glossed over, leading to poor (if any) convergence to minimum loss. Hence, smaller batch-sizes can lead to faster but noisier updates, while larger batch sizes provide smoother updates but may slow down convergence to minimum loss. Thus, batch size must be wisely chosen so as to avoid unnecessary updates and, at the same time, consider the contribution of disparate data points on learning. In practice, **mini-batch gradient descent** is often used, where the batch-size is set to a value larger than one but smaller than the total number of data points; this balances the trade-offs between noisy updates and computational efficiency.