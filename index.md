---
title: Syllabus
layout: home
nav_order: 1
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

* 40% minor projects (20% each). The two minor projects are [implementing a discrete PPL]( {{ '/projects/discrete_language.html' | relative_url }}) 
  and [implementing a continuous language]({{ '/projects/continuous_language.html' | relative_url }}). 
* 20% participation.
* 40% [final course project]({{ '/projects/term_project.html' | relative_url }})

All graded material is turned in on <a href="https://canvas.northeastern.edu">Canvas</a>. Join our <a href="https://join.slack.com/t/northeastern-7ho2086/shared_invite/zt-233t6oo4g-_ROUSvI1xAM5LN0rwQZpIg">Slack</a>!

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
    <li><a href="{{ '/assets/cs7470-lecture-1.pdf' | relative_url}}">Lecture 1 Slides</a></li>
    <li><b>Reading:</b> <a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-1/lecture-1.pdf">Lecture 1 course notes</a></li>
    <li><a href="https://course.ccs.neu.edu/cs4410sp22/hw_warmup1_assignment.html">Recommended exercises if you have not programmed in OCaml before</a></li>
    <!-- <li><b>Supplemental Reading</b>: </li> -->
    </td>
</tr>


<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Foundations</center>
  </td>
</tr>



<tr>
    <td>Tues Sept 12</td>
    <td>
    <span class="lecture">Propositional Probability I: Semantics</span>
    <ul>
        <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-2/lecture-2.pdf">Lecture 2 notes</a></li>
        <li><b>Reading</b>: Chapter 2 of {% cite darwiche2009modeling %}</li>
        <li><b>Supplemental Reading</b>: Chapter 1 of {% cite biere2009handbook %}</li>
    </ul>
    </td>
</tr>

<tr>
    <td>Fri. Sept. 15</td>
    <td>
    <span class="lecture">Propositional Probability II: A propositional PPL</span>
    <ul>
        <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-3/lecture-3.pdf">Lecture 3 notes</a></li>
        <li><b>Reading</b>: Chapter 3 of {% cite darwiche2009modeling %}</li>
        <li><b>Supplemental Reading</b>: Chapter 8.1, 8.2 of {% cite  graham1989concrete %}. </li>
    </ul>
    </td>
</tr>


<tr>
    <td>Tues. Sept 19</td>
    <td>
        <span class="lecture">Propositional Probability III: Knowledge compilation</span>
        <ul>
            <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-4/lecture-4.pdf">Lecture 4 notes</a></li>
            <li><b>Reading</b>: {% cite darwiche2002knowledge %} </li>
            <li><b>Supplemental reading</b>: {% cite chavira2008probabilistic %}</li>
        </ul>
    </td>
</tr>

<tr>
    <td>Fri. Sept 22</td>
    <td>
        <span class="lecture">Propositional Probability IV: Binary decision diagrams</span>
        <ul>
            <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-5/lecture-5.pdf">Lecture 5 notes</a></li>
        </ul>
    </td>
</tr>


<tr>
    <td>Tues. Sept 26</td>
    <td>
        <span class="lecture"><b>No Class</b> (please attend <a href="https://neu-se.github.io/software-day-23/">Software Day</a>)</span>
    </td>
</tr>

<tr>
    <td>Fri. Sept 29</td>
    <td>
      <span class="lecture">Discrete probabilistic programming I: Syntax & semantics</span>
      <ul>
         <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-6/lecture-6.pdf">Lecture 6 notes</a></li>
      </ul>
    </td>
</tr>

<tr>
   <td>Tues Oct. 3</td>
   <td>
        <span class="lecture">Discrete probabilistic programming II: Compilation</span>
        <ul>
            <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-7/lecture-7.pdf">Lecture 7 notes</a></li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Oct. 6</td>
   <td>
        <span class="lecture">Discrete probabilistic programming III: Observation</span>
        <ul>
         <li><a href="https://github.com/neuppl/CS7470-Notes/blob/main/lecture-8/lecture-8.pdf">Lecture 8 notes</a></li>
        </ul>
   </td>
</tr>

<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Designing and Implementing a Continuous PPL</center>
  </td>
</tr>

<tr>
   <td>Tues Oct. 10</td>
   <td>
        <span class="lecture">Discrete sampling semantics</span>
        <ul>
            <li><b>Reading</b>: Chapter 2 up to section 2.4 of {% cite barthe2020foundations %}</li>
            <li><b>General reference on continuous probability</b>: {% cite axler2020measure %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Oct. 13</td>
   <td>
        <span class="lecture">Importance sampling & continuous languages</span>
        <ul>
        </ul>
   </td>
</tr>


<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Systems Week</center>
  </td>
</tr>


<tr>
   <td>Tues Oct. 17</td>
   <td>
        <span class="lecture">Systems Week</span>. See <a href="{{ '/systems.html' | relative_url }}">the Systems Week page</a>.
   </td>
</tr>
<tr>
   <td>Fri Oct. 20</td>
   <td>
        <span class="lecture">Systems Week</span>
   </td>
</tr>


<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Automatic Differentiation</center>
  </td>
</tr>

<tr>
   <td>Tues Oct. 24</td>
   <td>
        <span class="lecture">Automatic Differentiation I: Theory</span>
        <ul>
        <li><b>Reading</b>: {% reference baydin2018automatic %}</li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Oct. 27</td>
   <td>
        <span class="lecture">Automatic Differentiation II: Applications</span>
        <ul>
        <li><b>Reading</b>: </li>
        <li><b>Supplemental reading</b>: {% cite lew2023adev %} </li>
        </ul>
   </td>
</tr>

<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Static Analysis</center>
  </td>
</tr>

<tr>
   <td>Tues Oct 31</td>
   <td>
        <span class="lecture">Probabilistic Separation Logics I</span>
        <ul>
        <li><b>Reading</b>: {% cite li2023lilac %}  </li>
        <li><b>Supplemental reading</b>: {% cite o2019separation %}, <a href="https://www.cs.cmu.edu/~jcr/copenhagen08.pdf">this textbook draft</a>, {% cite reynolds2002separation %}</li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Nov. 3</td>
   <td>
        <span class="lecture">Probabilistic Separation Logics II</span>
        <ul>
        <li><b>Reading</b>: Continue {% cite li2023lilac %}</li>
        </ul>
   </td>
</tr>



<tr>
   <td>Tues Nov 7</td>
   <td>
        <span class="lecture">Weakest Pre-Expectations</span>
        <ul>
        <li><b>Reading</b>: {% cite morgan1996probabilistic %}. This is a difficult read; do your best.</li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Nov 10</td>
   <td>
        <span class="lecture"> Weakest Pre-Expectations II</span>
        <ul>
        <li><b>Reading</b>: {% cite morgan1996probabilistic %} </li>
        <li><b>Supplemental Reading</b>: {% cite olmedo2016reasoning %} </li>
        </ul>
   </td>
</tr>


<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Potpourri: A collection of modern topics in PPLs</center>
  </td>
</tr>

<tr>
   <td>Tues Nov. 13</td>
   <td>
        <span class="lecture">Verified Inference</span>
        <ul>
        <li><b>Reading</b>: {% cite beutner2022guaranteed %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Nov. 17</td>
   <td>
        <span class="lecture">Generating Functions</span>
        <ul>
        <li><b>Reading</b>: {% cite klinkenberg2020generating %} </li>
        </ul>
   </td>
</tr>


<tr>
   <td>Tues Nov. 21</td>
   <td>
        <span class="lecture">Non-Standard Semantics of PPLs</span>
        <ul>
        <li><b>Reading</b>: {% cite baudart2020reactive %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Nov. 24</td>
   <td>
        <span class="lecture">No Class (Fall Break)</span>
   </td>
</tr>

<tr>
   <td>Tues Nov. 28</td>
   <td>
        <span class="lecture">Advanced Semantics of PPLs</span>
        <ul>
        <li><b>Reading</b>: {% cite dash2023affine %} </li>
        </ul>
   </td>
</tr>

<tr>
   <td>Fri Dec. 1</td>
   <td>
        <span class="lecture">Discussion & Outlook</span>
   </td>
</tr>



<tr>
  <td colspan="2" class="divider" style = "background-color: #EBEDEF;">
    <center>Final Presentations</center>
  </td>
</tr>

<tr>
   <td>Tues Dec. 4</td>
   <td>
        <span class="lecture">Presentation Slot 1</span>
   </td>
</tr>

<tr>
   <td>Fri Dec. 8</td>
   <td>
        <span class="lecture">Presentation Slot 2</span>
   </td>
</tr>

</table>

[See the reading list for more reading]({{ '/reading_list.html' | relative_url }})

# Bibliography

{% bibliography --cited %}
