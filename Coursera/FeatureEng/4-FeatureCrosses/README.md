# Introducing 

In traditional machine learning, feature crosses don’t play much of a role, but in modern day ML methods, feature crosses are an invaluable part of your toolkit.In this module, you will learn how to recognize the kinds of problems where feature crosses are a powerful way to help machines learn.

## Introduction

> [![](https://img.youtube.com/vi/zSR-_a8P63M/0.jpg)](https://youtu.be/zSR-_a8P63M)

* Learn how to ...
    * Recognize where feature crosses are a powerful way to help machines learn
    * Implement feature crosses in TensorFlow
    * Incopoerate feature creation as part of your ML pipeline
    * Improve the taxifare model using feature crosses

---
## What is a Feature Cross?

> [![](https://img.youtube.com/vi/kxZfu2Anu6s/0.jpg)](https://youtu.be/kxZfu2Anu6s)

* The feature cross provides a way to combine features in a linear model
    * Using non-linear inputs in a linear learner

---
## Discretization

> [![](https://img.youtube.com/vi/jXkkcF-xQ5I/0.jpg)](https://youtu.be/jXkkcF-xQ5I)

---
## Memorization vs. Generalization

> [![](https://img.youtube.com/vi/R8evI4-EyJc/0.jpg)](https://youtu.be/R8evI4-EyJc)

* A feature cross memorize the input space
* Goal of ML is generalization
* Memorization works when you have lots of data
* Feature crosses are powerful

---
## Taxi Colors

> [![](https://img.youtube.com/vi/YRZkcp2ZIjI/0.jpg)](https://youtu.be/YRZkcp2ZIjI)

* Which of these cars is a taxi?
    * Assume that your input data looks like this
        * e.g., Red, Rome; White, Rome; Yellow, NYC; White, NYC; ...
    * The linear model has problems; the feature cross has no problem
* Feature crosses bring a lot of power to linear model
    * Feature crosses + massive data is an efficient way of learning highly complex spaces
    * Feature crosses allow a linear model to memorize large datasets
    * Optimizing linear models is a convex problem
    * Before TensorFlow, Google used massive scale learners

---
## Lab 5: Feature Crosses to Create a Good Classifier

> [![](https://img.youtube.com/vi/w5AV3NXa3FQ/0.jpg)](https://youtu.be/w5AV3NXa3FQ)
> [![](https://img.youtube.com/vi/8LujL7KG5uk/0.jpg)](https://youtu.be/8LujL7KG5uk)

* Please follow the details in [here](./Lab-5.md)

---
## Sparsity

> [![](https://img.youtube.com/vi/_u7UXnpOEt0/0.jpg)](https://youtu.be/_u7UXnpOEt0)

* Feature crosses combine discrete / categorical features
    * E.g., Cross `hour_of_day` with `day_of_week` to predict traffic
        * How many inputs would we have if we simply one-hot-encoded the hour of day and the day of week and provided it to a model?
            > Answer: 24 input nodes for hours in the day + 7 inputs for days of the week = 31
        * How many inputs do we now have for our model?
            > Answer: 24 x 7 inputs = 168 total inputs
* Feature crosses lead to sparsity
    * E.g., Cross `hour_of_day` with `day_of_week` to predict traffic
        * How many nodes in $x_3$ will be lit up for a single input from $x_1$ and $x_2$?
            > Answer: 1

### Quiz

* Which of these is a good feature cross?
    * Different cities in California have markedly different housing prices. Suppose you must create a model to predict housing prices. Which of the following sets of features or feature crosses could learn city-specific relationships between house characteristic and housing price?
        * A. Two feature crosses: [binned latitude X binned roomsPerPerson] and [binned longitude X binned roomsPerPerson]
        * B. One feature cross: [latitude X longitude X roomsPerPerson]
        * C. One feature cross: [binned latitude X binned longitude X binned roomsPerPerson]
        * D. Three separate binned features: [binned latitude], [binned longitude], [binned roomsPerPerson]
        > Answer: C.
        > Yes. Crossing binned latitude with binned longitude enables the model to learn city-specific effects of roomsPerPerson. Binning prevents a change in latitude producing the same result as a change in longitude. Depending on the granularity of the bins, this feature cross could learn city-specific or neighborhood-specific or even block-specific effects.

---
## Lab 6: Too Much of a Good Thing

> [![](https://img.youtube.com/vi/rCZhZlsNydc/0.jpg)](https://youtu.be/rCZhZlsNydc)
> [![](https://img.youtube.com/vi/Nj1EtL7SzC0/0.jpg)](https://youtu.be/Nj1EtL7SzC0)

* Please follow the details in [here](./Lab-6.md)

---
## Implementing Feature Crosses

> [![](https://img.youtube.com/vi/82LJIOneOac/0.jpg)](https://youtu.be/82LJIOneOac)

* Create feature crosses using TensorFlow
    ```python
    day_hr = tf.feature_column.crossed_column(
        [dayofweek, hourofday],
        24 * 7)
    ```
    * You can cross two or more categorical or bucketized columns
    * `24 * 7` is the number of hash buckets: `feature_cross % hash_bucket_size`
* Choosing the number of hash buckets is an art, not a science
* The number of hash buckets controls sparsity and collisions
    * Small `hash_buckets`, lots of collision
    * High `hash_buckets`, very sparse
* Some expericen: choose a number between $\frac{1}{2}\sqrt{n}$ and $2n$

---
## Embedding Feature

> [![](https://img.youtube.com/vi/KYxH8Nd9xAc/0.jpg)](https://youtu.be/KYxH8Nd9xAc)


---
## Module Quiz


---
## Where to Do Feature Engineering

> [![](https://img.youtube.com/vi//0.jpg)](https://youtu.be/)


---
## Feature Creation in TensorFlow

> [![](https://img.youtube.com/vi//0.jpg)](https://youtu.be/)



---
## Feature Creation in Dataflow

> [![](https://img.youtube.com/vi//0.jpg)](https://youtu.be/)


---
## Lab 7: Improve ML Model with Feature Engineering

> [![](https://img.youtube.com/vi//0.jpg)](https://youtu.be/)
> [![](https://img.youtube.com/vi//0.jpg)](https://youtu.be/)

* Please follow the details in [here](./Lab-7.md)

---