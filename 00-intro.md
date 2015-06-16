---
layout: page
title: LaTeX
subtitle: Introducing LaTeX
minutes: 
---

> ## Learning Objectives {.objectives}
>
> * Obtain an overview of what is involved in using LaTeX.
> * Understand what sorts of projects LaTeX is best suited to.

LaTeX is a free, open source and cross-platform typesetting system.
It was originally released in the mid-1980s by Leslie Lamport
as a way of automating many aspects of Donald Knuth's TeX programming language.
The word "LaTeX" is a portmanteau of "Lamport TeX".
Note that *TeX* is from the Greek word *τέχνη*, pronounced "techneh";
thus, LaTeX should be pronounced "Lah-Tech" or "Lay-Tech", never "lateks".

A document made in LaTeX will usually be treated like a software project.
Each section or chapter is put in a different file containing a mix of 
plain text and markup commands;
the user interacts with these files using a text editor or an
integrated development environment (IDE).
To see what the final product looks like you tell the
IDE to build a "pretty" version, usually output as a PDF.
(This step is referred to as "compiling".)

An example LaTeX document is:

~~~ {.tex}
\documentclass[12pt]{article}
\title{Hello world}
\date{}
\begin{document}
\maketitle
\LaTeXe\ is a free, open source and cross-platform typesetting system.
It was originally released in the mid-1980s by Leslie Lamport
as a way of automating many aspects of Donald Knuth's \TeX\ programming language.
The word ``\LaTeX'' is a portmanteau of ``Lamport \TeX{}''.
Note that ``\TeX'' is from the Greek word $\tau\epsilon\chi\nu\eta$, pronounced "techneh";
thus, \LaTeX\ should be pronounced ``Lah-Tech'' or ``Lay-Tech'', never ``lateks''.

A simple equation describes the curvature of spacetime due to mass and energy:

\begin{equation}
  R_{\mu \nu} - {1 \over 2}g_{\mu \nu}\,R + g_{\mu \nu} \Lambda = {8 \pi G \over c^4} T_{\mu \nu}
\end{equation}
\end{document}
~~~

If the document is in a file called `example.tex`, we compile it like so:

~~~ {.bash}
$ pdflatex example.tex
~~~

This will generate a PDF called `example.pdf`, which should look a bit like:

![](fig/00-example.png)

Due to the overhead in setting up a new LaTeX project,
people usually consider it contraindicated for small,
uncomplicated documents with no special typesetting requirements.
For these you'll usually be better off with markdown or a conventional word processor.

LaTeX comes into its own when you either have special typesetting requirements
or a large, complicated document.
As a rule of thumb, consider using LaTeX for any document
longer than a novella or more complicated than a technical report.

> ## A first LaTeX document {.challenge}
>
> Check whether you can compile the above example.
>
> If you try compiling and get an error, it might look like LaTeX freezes up,
> but it's just waiting for you to tell it how to proceed.
> If this happens, enter the letter "X" and press enter to terminate compilation.
