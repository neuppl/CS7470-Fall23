---
title: "Project #1: Discrete Language"
parent: "Projects"
layout: default
---

1. TOC
{:toc}

# Project overview

The goal in this project is to implement your own discrete probabilistic
programming language. The skeleton code for the project is available on GitHub:

[https://github.com/neuppl/disc](https://github.com/neuppl/disc)

**Due date**: The project is due **Tuesday Oct. 3** at 11:59PM EST. If you require an extension, email 
the instructor.

**Rubric**: The project will be evaluated according to following rubric:

* 70% Correctness
  - A score of 100% is given for this category if all included tests in the GitHub repository are passed.
  - If not all tests pass, partial credit will be assigned according to the percentage of tests that are passed.
* 30% Final writeup
  - Include solutions to the modeling exercises. These are graded on a pass/no-pass scale.
  - Please give us some feedback for future iterations on this project.

**What to turn in**: On Canvas, turn in the following:

* A `.zip` file containing your project. We should be able to unzip this file and run `dune build` in order to build.
* A `.pdf` file containing your solutions to the modeling exercises. 

# Syntax

The `disc` language is a simple PPL that consists purely of Boolean random 
values.
The syntax is given as two inductively defined terms: expressions `e` 
and programs `p`. A program is simply a designated start expression. 
It has the following syntax:

```
e ::=
   | x <- e; e
   | observe e; e
   | flip q                         // q is a rational value
   | if e then e else e
   | return e
   | true | false
   | e && e | e && e | ! e |
   | ( e )

p ::= e
```

So for instance, we can write the following program in `disc`:

```
x <- flip 0.6; 
y <- flip 0.3;
observe x || y;
return x
```

This program flips two coins and observes the outcome of at least one of them to
be true, then returns the posterior probability of coin `x` being true. The 
resulting posterior is:

$$
\frac{0.6 \times 0.3 + 0.6 \times 0.3}{0.6 \times 0.3 +0.6\times0.3+0.4\times0.3} \approx 0.8333333.
$$

# Semantics
The semantics for the probabilistic terms associates each term with an 
unnormalized probability distribution
It has the type $[[e]] : \texttt{Bool} \rightarrow [0, 1]$,
and has the following inductive definition:

$$
[\![\texttt{flip}~\theta]\!](v) = 
\begin{cases}
\theta& \quad \text{if }v = T\\
1-\theta& \quad \text{if }v = F\\
\end{cases}
$$

$$
 [\![\texttt{return}~e]\!](v) = 
 \begin{cases}
 1\quad& \text{if }v = [\![e]\!]\\
 0\quad&  \text{otherwise}\\
 \end{cases}
$$

$$
[\![x \leftarrow e_1; e_2]\!](v) = \sum_{v'} [\![{e_1}]\!](v') \times [\![{e_2[x \mapsto v']}]\!](v)
$$

$$
[\![\texttt{observe}~e_1; e_2]\!](v) = 
\sum_{\{v' \mid [\![{e_1}(v') = T\}]\!]} [\![{e_2}]\!](v)
$$

The semantics for non-probabilistic terms is standard. The semantic evaluation has type 
$[[e]]: \texttt{Bool}$ for closed terms.

These semantics give an unnormalized distribution. The main semantic object of interest is 
the normalized distribution, which is given by the *normalized semantics*:

$$
[\![e]\!]_D(T) = \frac{[\![e]\!](T)}{[\![e]\!](T) + [\![e]\!](F) },
$$

defined analogously for the false case.

# Inference

You will be required to implement two inference algorithms for this project: (1) exact inference 
by enumeration, and (2) knowledge compilation based inference.

## Enumeration

For this section we will be implementing exact inference via exhaustive enumeration. We will 
be filling in the `lib/enumerate.ml` file. Your solution should implement the `infer` function 
in this file.
Enumeration can be described as a big-step relation $e \Downarrow (\alpha, \beta)$ where $\alpha$ 
is the unnormalized true probability and $\beta$ is the unnormalized false probability.
The adequacy requirement that this relation should satisfy is, if $e \Downarrow (\alpha, \beta)$, then:

$$
[\![ e ]\!]_D(T) = \frac{\alpha}{\alpha + \beta}
$$

This relation is described inductively:

$$\frac{}{\texttt{flip}~\theta \Downarrow (\theta, 1-\theta)}$$

$$
\frac{e_1 \Downarrow (\alpha_1, \beta_1) \quad e_2[x \mapsto T] \Downarrow (\alpha_2, \beta_2) \quad e_2[x \mapsto F] \Downarrow (\alpha_3, \beta_3)}
{x \leftarrow e_1; e_2 \Downarrow (\alpha_1\alpha_2 + \beta_1\alpha_3, \alpha_1\beta_2 + \beta_1\beta_3 )}
$$

$$
\frac{}
{\texttt{observe}~F; e_2 \Downarrow (0, 0)}
$$

$$
\frac{e_1 \Downarrow (\alpha, \beta)}
{\texttt{observe}~T; e_2 \Downarrow (\alpha, \beta)}
$$


## Knowledge compilation
For this section we will be implementing exact inference via knowledge compilatio;n. We will 
be filling in the `lib/kc.ml` file. Your solution should implement the `infer` function 
in this file.
Enumeration can be described as a big-step relation $e \Downarrow (\varphi, \gamma, w)$ where $\varphi$ 
and $\gamma$ are Boolean formulae and $w$ is a weight function.
The invariant that these Boolean formulae should satisfy is that, for $e \Downarrow (\varphi, \gamma, w)$ 
the following holds:

$$
[\![ e ]\!]_D(T) = \frac{\texttt{WMC}(\varphi \land \gamma, w)}{\texttt{WMC}(\gamma, w)}
$$

The compilation relation is as follows:

$$\frac{\texttt{fresh }\ell}{\texttt{flip}~\theta \Downarrow (\ell, T, [\ell \mapsto \theta, \overline{\ell}\mapsto 1-\theta])}$$


* TODO: Finish the rules above
* TODO: Link to some docs for using our knowledge compilation library

# Modeling exercises

Now we will use `disc` to model and reason about a simple network reliability example.

## Network Reliability

![Alt text](network.png)

The directed graph above gives an abstract view of a
computer network. The goal in a network like this is to deliver a packet
-- piece of data -- from one router to another by passing it through
intermediate routers in the graph. Each node is a router, and each directed edge
is a link from one router to another. Packets always begin at $A$.

In the real world there is often some uncertainty in the behavior of such a
network. Assume that each link has a failure probability given by its
annotation; for instance, the probability that a packet traversing the link $A
\rightarrow C$ fails to be delivered is 0.2. Furthermore, assume that, when
given multiple options, a router will choose uniformly at random which
router to forward to; for instance, if the packet is at node $A$, then at the
next step it will have a 50% chance of being at node $C$ and a 50% chance of
being at node $B$. Use your `disc` implementation and exact inference to
answer the following questions about this network's behavior:


  1. What is the probability that a packet successfully reaches $H$? Include
    your `disc` file in the report.
  2. If packet reached $H$, what is the probability that the packet reached
    $C$? Include your `disc` file in the report.
  3. If the packet did not reach $F$ or $G$, what is the probability that it
    reached $D$?
  4. Suppose I can fix a single edge to never drop a packet. Which edge
    should I fix to maximize the probability that a packet reaches $H$, and what
    is the probability that $H$ is reached in this new fixed network?

## Exercise 2

TODO?

# Extensions

For your final course project you may choose to extend `disc` in some way. Here are some suggestions 
for how to improve or extend `disc`:

* Develop and benchmark compiler optimizations.
* Extend `disc` to handle bounded and possibly unbounded loops.