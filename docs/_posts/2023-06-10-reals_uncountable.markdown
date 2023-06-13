---
author_profile: true
read_time: true
comments: # true
share: true
related: true
layout: single
title:  "Proving that Reals are Uncountable (with Measure Theory)"
date:   2023-06-13 
tags: analysis measure_theory
classes: wide
---

I have been learning some basic measure theory this summer using the tail end Terence Tao's book *Analysis II*. 
I have to know some fundamental results for the analysis comprehensive exam, so I figured I'd take some time (when I still have it) to 
study up. 

In exercise 7.2.6, he asks you to furnish another proof that the reals are uncountable, using the concept of outer 
measure. If $\Omega \subseteq \mathbb{R}^n$, we define the outer measure as

$$
m^{\ast}(\Omega) = \inf_{(B_j)_{j \in J}}\bigg\{\sum_{j \in J}\text{vol}(B_j): (B_j)_{j \in J} \text{ is a countable cover of } \Omega \text{ by open boxes}\bigg\}.
$$

In loose terms, it's the smallest total volume we can get when we cover some subset of $\mathbb{R}^n$ with a countable number of open boxes, which 
here are defined as 

$$
B = \prod_{i=1}^n(a_i,b_i),
$$

which have volume $\text{vol}(B) = \prod_{i=1}^n(b_i-a_i)$.

Showing that the reals are uncountable using the concept of outer measure requires two steps:
1. Show that any countable set has outer measure zero
2. Show that $\mathbb{R}$ is does not have measure zero

To me, this approach is a bit easier to conceptualize than the usual diagonalization argument. It's certainly beautiful, but it always 
felt like magic and it didn't really paint a picutre. Here I feel we can paint a picture with our open cover and gain a bit more intuition 
for why the reals are so much larger than the rationals. Let's jump in!

*Proof.* I'll start with the first step, proving that any countable set in $\mathbb{R}$ has outer measure zero.
Let $A = \\{a_1, a_2, \dots\\}$ be a countable subset of $\mathbb{R}$.
Fix an arbitrary $\varepsilon>0$ and for each $a_i$, let's define

$$
B_i = (a_i - \varepsilon/2^{i+1},a_i + \varepsilon/2^{i+1}),
$$

so $\text{vol}(B_i) = \varepsilon/2^i$. This seems like a random construction, yes. But remember that ***we want the sum of the volumes of our boxes 
to be less than $\varepsilon$***. Our construction is useful since we know that 

$$
\sum_{n=1}^{\infty} \frac{1}{2^n} = 1.
$$ 

Clearly $(B_i)_{i=1,2,\dots}$ is a countable cover $A$ by open boxes, so now we can compute (with our series above) 

$$
m^{\ast}(A) \leq \sum_{i=1}^{\infty}\text{vol}(B_i) = \sum_{i=1}^{\infty}\frac{\varepsilon}{2^i} = \varepsilon.
$$

We can make $\varepsilon$ arbitrarily small (in other words we can take the limit $\varepsilon \to 0$), so we have that $m^{\ast}(A) = 0$.

Now to prove that $\mathbb{R}$ is uncountable, we just need to show that $m^{\ast}(\mathbb{R}) \neq 0$.
For any $R >0$, $R \in \mathbb{R}$, we know that $(-R,R) \subseteq \mathbb{R}$, so from the monotonicty of outer measure we have
$m^{\ast}(-R,R) \leq m^{\ast}(\mathbb{R})$.
Note that $m^{\ast}(-R,R) = 2R$, which can be arbitrarily large, but really all we need is for it to be non-zero, so 

$$
m^{\ast}(\mathbb{R}) \geq m^{\ast}(-2R) = 2R > 0.
$$

Since the outer measure of $\mathbb{R}$ is non-zero, we conclude it is uncountable.  **QED**

Now, we did take for granted the fact that $m^{\ast}(-R, R) = 2R$, which would take a some more work to do.
Maybe I'll work on that in another post, but I think it's more work than I want to do here.

<div style="display:none">
$
\newcommand{\emp}{\emptyset}
$
</div>

