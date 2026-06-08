---
layout: post
title: "The Law of Large Numbers"
date: 2026-06-08
categories: [Probability]
tags: [probability, statistics, law-of-large-numbers]
---

One of the most important ideas in probability and statistics is this:

> If we repeat a random experiment many times, the average result tends to get closer to the true expected value.

This idea is called the **Law of Large Numbers**.

## A simple example

Suppose we toss a fair coin.

Let $X_i$ be the result of the $i$-th toss:

$$
X_i =
\begin{cases}
1, & \text{if the result is heads} \\
0, & \text{if the result is tails}
\end{cases}
$$

Since the coin is fair, we have:

$$
\mathbb{E}[X_i] = \frac{1}{2}
$$

If we toss the coin only 10 times, we might get 7 heads or 3 heads. The observed proportion of heads can be quite far from $0.5$.

But if we toss the coin 10,000 times, the proportion of heads will usually be much closer to $0.5$.

The sample average after $n$ tosses is:

$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^{n} X_i
$$

The Law of Large Numbers says that as $n$ becomes large, $\bar{X}_n$ gets closer to the true expectation $\mathbb{E}[X]$.

In this example:

$$
\bar{X}_n \to \frac{1}{2}
$$

## The intuition

Suppose $X_1, X_2, \dots, X_n$ are independent and identically distributed random variables with finite expectation $\mu$.

The sample average is:

$$
\bar{X}_n = \frac{X_1 + X_2 + \cdots + X_n}{n}
$$

The Law of Large Numbers says that this sample average converges to:

$$
\mu = \mathbb{E}[X]
$$

as $n$ increases.

In simple words:

$$
\bar{X}_n \approx \mathbb{E}[X]
$$

when the number of observations is large enough.

## Why does this make sense?

Each individual observation can be noisy.

A coin toss can be heads or tails.  
A customer may buy something or not.  
A trading day may have profit or loss.  
A measurement may be above or below the true value.

But when we average many observations, random fluctuations tend to cancel each other out.

Some observations are unusually high.  
Some observations are unusually low.  
When there are enough of them, the average becomes more stable.

This is why an average based on many observations is usually more reliable than a single observation.

## The Weak Law of Large Numbers

One common version is the **Weak Law of Large Numbers**.

It says that for every $\epsilon > 0$:

$$
P(|\bar{X}_n - \mu| > \epsilon) \to 0
$$

as:

$$
n \to \infty
$$

This means that the probability of the sample average being far from the true mean goes to zero as the sample size grows.

In other words, with enough data, the sample average is very likely to be close to the true expectation.

## Why is the Law of Large Numbers important?

The Law of Large Numbers is one of the foundations of statistics and machine learning.

In many problems, we do not know the true value of something. Instead, we estimate it using data.

For example:

- To estimate the average height of students in a university, we survey a group of students.
- To estimate the click-through rate of an advertisement, we observe a sample of users.
- To estimate the true loss of a machine learning model, we compute the average loss on a dataset.
- To approximate a difficult integral, we can use Monte Carlo simulation.

In all of these examples, we rely on the same belief:

> The average over a large enough sample should be close to the true average.

The Law of Large Numbers gives mathematical support for this belief.

## Example: Monte Carlo estimation

Suppose we want to compute:

$$
\mathbb{E}[f(X)]
$$

But computing the expectation directly is difficult.

Instead, we can draw samples:

$$
X_1, X_2, \dots, X_n
$$

and approximate the expectation by:

$$
\frac{1}{n} \sum_{i=1}^{n} f(X_i)
$$

By the Law of Large Numbers, when $n$ is large:

$$
\frac{1}{n} \sum_{i=1}^{n} f(X_i) \approx \mathbb{E}[f(X)]
$$

This is the core idea behind Monte Carlo methods.

## What the Law of Large Numbers does not say

The Law of Large Numbers does not say that a small sample is always accurate.

It also does not say that the error decreases smoothly after every new observation.

For example, after 100 coin tosses, the proportion of heads may be close to $0.5$. But after the 101st toss, the proportion can still move slightly away from $0.5$.

The Law of Large Numbers is about long-run behavior, not perfect stability at every step.

It also does not tell us exactly how fast the sample average converges. To understand the distribution of the error around the true mean, we usually need the **Central Limit Theorem**.

## Law of Large Numbers vs Central Limit Theorem

The Law of Large Numbers answers the question:

> Does the sample average get close to the true expectation?

The Central Limit Theorem answers a different question:

> How does the sample average fluctuate around the true expectation?

The Law of Large Numbers says:

$$
\bar{X}_n \to \mu
$$

The Central Limit Theorem says that, under suitable conditions:

$$
\sqrt{n}(\bar{X}_n - \mu)
$$

has an approximately normal distribution.

So the Law of Large Numbers tells us why the sample average is reasonable. The Central Limit Theorem helps us quantify its uncertainty.

## Conclusion

The Law of Large Numbers is one of the most fundamental results in probability and statistics.

It explains why averaging many random observations can reveal a stable underlying pattern.

In short:

$$
\text{More data} \Rightarrow \text{a more stable sample average}
$$

More formally:

$$
\bar{X}_n \to \mathbb{E}[X]
$$

This is one reason statistics works: even though individual observations can be noisy, structure can emerge when we look at enough data.