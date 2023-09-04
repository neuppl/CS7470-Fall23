---
title: Resources
layout: default
nav_order: 3
---

# Background Reading

Probabilistic programming covers a broad collection of topics in programming
languages, probability, and artificial intelligence. Here are some general
resources (mostly textbooks) for filling in background in these areas.
Most of these are books on my bookshelf.

There are a few textbooks on probabilistic programming that I recommend:

* {% reference barthe2020foundations %}
  - This book is open-access and available [here](https://www.cambridge.org/core/books/foundations-of-probabilistic-programming/819623B1B5B33836476618AC0621F0EE)
  - It is very programming-languages oriented -- it has nice chapters on semantics, 
    program logics for couplings, etc.
* {% reference van2018introduction %}
  - This book is very statistical machine-learing oriented, and focuses heavily on 
    inference.

## Programming Languages

* Good introductory texts: 
  - {% reference pierce2002types %}
  - {% reference harper2016practical %}
  - {% reference pierce2004advanced %}
* Denotational semantics
  - {% reference gunter1992semantics %}

## Probability

* Probability introductions
  - Chapter 2 of {% cite murphy2012machine %}
  - Chapter 8 of {% cite graham1989concrete %}
* Measure-theoretic probability
  - Good introductions: {% cite axler2020measure %}
  - General references: {% cite tao2011introduction %} {% cite kallenberg1997foundations %}
  - Advanced and comprehensive references: {% cite fremlin2000measure %}
* Inference
  - Excellent starting points: {% cite murphy2012machine %} {% cite pml1Book %} {% cite murphy2022probabilistic %} 
  - Probabilistic graphical models: {% cite darwiche2009modeling %} {% cite koller2009probabilistic %}

# Similar Courses

Sometimes it is useful to see how similar things are taught in other contexts or at 
other universities. Here are some links:

* A prior offering at Northeastern: https://www.khoury.northeastern.edu/home/sholtzen/CS7480Fall21/
* https://web.cs.ucla.edu/~guyvdb/teaching-service/cs267a/2018f/
* http://danroy.org/teaching/2015/STA4516/
* http://probcomp.csail.mit.edu/9.S915/
* https://github.com/hongseok-yang/probprog17
* https://www.cs.ubc.ca/~fwood/CS532W-539W/

# Bibliography

{% bibliography --cited %}
