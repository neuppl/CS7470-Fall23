---
title: Reading List
layout: default
nav_order: 2
---



# Annotated reading list

This page contains a collection of interesting probabilistic programming papers
organized by topic that are relevant to the course. This bibliography is not
meant to be exhaustive of all useful papers; it is meant to contain a good
starting point for each of the major topic areas. These papers are a mix of
classic papers and papers that I want to read. Feel free to peruse these papers
for project ideas. These papers are sorted chronologically within each category.

Another excellent resource is the following textbook:

{% reference barthe2020foundations %}

1. TOC
{:toc}

# Semantics

These papers are concerned with the question of "what does a probabilistic program mean"? Some of the earliest papers in probabilistic programming asked this question, and it remains a core topic of interest within probabilistic programming today. Today, much of the challenge within this area focuses on giving meaning to languages with rich features: higher-order functions, continuous random variables, and continuous conditioning.
 

<table>

<tr>
    <td>{% reference lawvere1962category %}</td>
    <td>
        A well-known unpublished note from Lawvere that initiated the study of categorical probability.
    </td>
</tr>
<tr>
    <td>{% reference kozen1979semantics %}</td>
    <td>
        The first paper to formalize the notion of a probabilistic program.
    </td>
</tr>
<tr>
    <td>{% reference giry1986 %}</td>
    <td>
    Introduced the "Giry monad"
    </td>
</tr>
<tr>
    <td>{% reference 10.1145/503272.503288 %}</td>
    <td>
        Develops a core probabilistic programming calculus using the probability monad. A good first read.
    </td>
</tr>


<tr>
    <td>{% reference 10.5555/3329995.3330072 %}</td>
    <td>
        Introduced the quasi-Borel space as a categorical foundation for higher-order continuous PPLs
    </td>
</tr>


<tr>
    <td>{% reference 10.1145/3374208 %}</td>
    <td>
        Develops Hakaru, a language that nicely handles conditioning in the continuous setting.
    </td>
</tr>



</table>


# Probabilistic Verification

These papers are concerned with the question of verifying correctness properties of probabilistic programs and systems. Example of applications include verifying differential privacy and verifying the correctness of randomized algorithms.


<table>
<tr>
    <td>
        {% reference kozen1983probabilistic %}
    </td>
    <td>
    The first example of a program logic for probabilistic programs.
    </td>
</tr>
<tr>
    <td>
        {% reference morgan1996probabilistic %}
    </td>
    <td>
    Introduced probabilistic predicate transformers and weakest pre-expectations.
    </td>
</tr>
<tr>
    <td>{% reference 10.1145/2933575.2934554 %}</td>
    <td>
        One of the earlier papers on verifying probabilistic properties via coupling.
    </td>
</tr>
<tr>
    <td>
        {% reference vasilenko2022safe %}
    </td>
    <td>
    An interesting application of refinement types to verifying properties of probabilistic programs.
    </td>
</tr>


</table>

# Verified Inference

These papers are concerned with the question of "how do we determine whether or
not a probabilistic programming system is correctly implemented"? It is
notoriously difficult to implement inference algorithms correctly, and
increasingly important decisions are being made based on the outcome of
inference computations, making this a very important area for research in modern
PPLs.


<!-- <table>
<tr>
    <td>
        {% reference kozen1983probabilistic %}
    </td>
    <td>
    </td>
</tr>
</table>
 -->

# Automatic Differentiation

What does automatic differentiation have to do with probabilistic programs? It
turns out the two are intimately related: automatic differentiation can inform
how we explore the search space during probabilistic inference. This is critical
for scaling inference on certain kinds probabilistic programs. Beyond inference,
automatic differentiation has can facilitate other kinds of probabilistic 
programming tasks like maximum-likelihood learning.

<!-- <table>
<tr>
    <td>
        {% reference kozen1983probabilistic %}
    </td>
    <td>
    The first example of a program logic for probabilistic programs.
    </td>
</tr>
</table> -->
