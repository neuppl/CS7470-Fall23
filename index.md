---
title: Syllabus
layout: home
---

# CS 7470: Topics in Programming Languages: Foundations of Probabilistic Programming

* Instructor: <a href="https://www.khoury.northeastern.edu/home/sholtzen/">Steven Holtzen</a>, `s.holtzen@northeastern.edu`
* Session: Fall 2023
* Meeting time: Tuesday/Friday 9:50 am - 11:30 am (EST)
* Location: Ryder Hall 433 (email Steven for remote participation link)
* Office hours by appointment

Probabilistic programming languages (PPLs) use the syntax and semantics of
programming languages to define probabilistic models. PPLs enable a diverse
audience – data scientists, systems designers, medical doctors, etc. – to design
and reason about probabilistic systems. PPLs are becoming a central topic in
artificial intelligence and programming languages research, with increasing
interest from industry and academia in designing and applying PPLs.

The goal of this course is to introduce the core ideas of probabilistic
programming languages: probabilistic inference, semantics, program analysis,
language design, and applications. The course will consist of formal lectures as
well as research presentations by students surveying the modern landscape of
developments in probabilistic programming. There will be a minor project
involving implementing a probabilistic programming language, and a self-directed
term project that aims to deeply explore some of the core ideas of probabilistic
programming.

### Evaluation & graded material

The course grade will be determined by the following graded material:

* 40% minor projects (20% each). The two minor projects are [implementing a discrete PPL](/projects/discrete_language/) 
  and [implementing a continuous language](/projects/continuous_language/). 
* 60% [final course project](/projects/term_project/)

All graded material is turned in on <a href="https://canvas.northeastern.edu/">Canvas</a>.

# Schedule

<table>
<thead>
    <tr>
        <th style="width:5%">Date</th><th style="width: 100%">Topic</th>
    </tr>
</thead>

<tr>
    <td>Fri Sept 8</td>
    <td>
    <span class="lecture">Introduction & Overview</span>
    <!-- <li><b>Supplemental Reading</b>: </li> -->
    </td>
</tr>

<tr>
    <td>Tues Sept 12</td>
    <td>
    <span class="lecture">Propositional Logic: Syntax, Semantics, and Satisfiability</span>
    <ul>
        <li><b>Reading</b>: Chapter 2 of {% cite darwiche2009modeling %}</li>
        <li><b>Supplemental Reading</b>: Chapter 1 of {% cite biere2009handbook %}</li>
    </ul>
    </td>
</tr>

<tr>
    <td>Fri. Sept. 15</td>
    <td>
    <span class="lecture">Discrete Probability</span>
    <ul>
        <li><b>Reading</b>: Chapter 3 of {% cite darwiche2009modeling %}</li>
        <li><b>Supplemental Reading</b>: Chapter 8.1, 8.2 of {% cite  graham1989concrete %}. </li>
    </ul>
    </td>
</tr>

<tr>
    <td>Tues Sept. 19</td>
    <td>
        <span class="lecture">Exact Inference & Weighted Model Counting</span>
        <ul>
            <li><b>Reading</b>: {% cite chavira2008probabilistic %}</li>
            <li><b>Supplemental reading</b>: {% cite gomes2021model %} </li>
        </ul>
    </td>
</tr>

<tr>
    <td>Fri. Sept 22</td>
    <td>
        <span class="lecture">Programming Languages: Abstract Syntax & Semantics</span>
        <ul>
            <li><b>Reading</b>: Chapter 3: "Untyped Arithmetic Expressions" in {% cite pierce2002types %} </li>
            <li><b>Supplemental reading</b>: Chapter 5 of {% cite harper2016practical %}; Lecture 3 notes from <a href="https://www.cs.cornell.edu/courses/cs6110/2013sp/">this course</a></li>
        </ul>
    </td>
</tr>

<tr>
    <td>Tues. Sept 26</td>
    <td>
        <span class="lecture">Discrete Probabilistic Programming Language: Syntax & Semantics</span>
        <ul>
            <li><b>Reading</b>: Course notes</li>
            <li><b>Supplemental reading</b>: {% cite holtzen2020scaling %} </li>
        </ul>
    </td>
</tr>

<tr>
    <td>Fri. Sept 29</td>
    <td>
        <span class="lecture">Discrete Probabilistic Programming Language: Exact Inference</span>
        <ul>
            <li><b>Reading</b>: Course notes</li>
        </ul>
    </td>
</tr>

<tr>
   <td>Tues Oct. 3</td>
   <td>
        <span class="lecture">Introduction to Continuous Probability</span>
        <ul>
            <li><b>Reading</b>: Course notes</li>
            <li><b>General reference</b>: {% cite axler2020measure %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Oct. 6</td>
   <td>
        <span class="lecture">Continuous Inference I: Monte-Carlo Methods</span>
        <ul>
            <li><b>Reading</b>: Chapter 11 of {% cite pml2Book %} </li>
            <li><b>Supplemental reading</b>: {% cite ramsey2002stochastic %}, Chapter 1 in {% cite barthe2020foundations %} </li>
        </ul>
   </td>
</tr>


<tr>
   <td>Tues Oct. 10</td>
   <td>
        <span class="lecture">Continuous Probabilistic Programming Languages: Syntax & Importance Sampling Semantics</span>
        <ul>
            <li><b>Reading</b>: Course notes</li>
            <li><b>Supplemental reading</b>: {% cite ramsey2002stochastic %}, Chapter 1 in {% cite barthe2020foundations %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Oct. 13</td>
   <td>
        <span class="lecture">Continuous Inference II: Markov-Chain Monte Carlo</span>
        <ul>
            <li><b>Reading</b>: Chapter 12 of {% cite pml2Book %} (note: this chapter is massive, focus on the earlier parts) </li>
        </ul>
   </td>
</tr>


</table>

<!-- <iframe style = "width: 100%; height: 800px;" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vT6gFuy0-U7RyA3s7Gpgb4tx7ZvyxagMezyrlUYf4NbJpd4Wg2Swp2TIrH4qEt6eT-wPp7v40MJjPTJ/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe> -->

# Bibliography

{% bibliography --cited %}
