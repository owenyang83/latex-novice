---
layout: page
title: LaTeX
subtitle: LaTeX document and project structure
minutes: 
---

> ## Learning Objectives {.objectives}
>
> * Understand the parts of a LaTeX document.
> * Be able to make a title.
> * Be able to use sectioning commands.
> * Be able to generate a table of contents.
> * Understand the difference between "starred" and "unstarred" sectioning commands.
> * Be able to insert other text files into a LaTeX document.
> * Understand the difference between inputting and including files.
> * Understand the different parts of LaTeX output.

Although TeX is suitable for small, uncomplicated projects,
it does not automate many tasks without additional work.
LaTeX on the other hand does not require any programming ability.
It already knows how to switch between different document types,
keep track of sectioning, manage cross-references, and much more.

We will now have a look at the basic structure required to set up any LaTeX project.

Every LaTeX document can be thought of as having two parts:

* Preamble
* Body

The preamble is where we tell LaTeX what sort of document we're writing, 
and which non-default resources we'd like to use.
It is also a good place to customise the way we use LaTeX.
For example, you can define your own command words,
or modify the behaviour of existing commands.

Only one thing is required for the preamble:
you must use the `\documentclass` command word to tell LaTeX what sort of
document we're writing.
By default, LaTeX offers five possible document classes:

* article
* report
* letter
* book
* slides

For example, to begin an article, you would make the first line of your document:

~~~ {.tex}
\documentclass{article}
~~~

Other document classes are available if you install them;
how best to do this partly depends on your operating system.
In fact, some of the non-default classes are used much more often than the ones
listed above.
For example, to make a presentation in LaTeX,
most people will use *beamer* rather than slides;
and when people use LaTeX for writing long books,
*memoir* is a popular document class.
However, in these lessons, we'll focus on the article and report classes.

The body is where you place the content of your document.
The body is always between a `\begin{document}` and an `\end{document}`.
If you don't have a `\begin{document}` and an `\end{document}`,
your LaTeX compiler will let you know that there is an error.

Putting it all together, the simplest possible LaTeX document is:

~~~ {.tex}
\documentclass{article}
\begin{document}
hello world
\end{document}
~~~

As you can see, this is a bit longer and more complicated than the simplest
plain TeX document.
It pays off, though, because now some infrastructure is in place that lets
us get to work on a realistic document.

First of all, we want a title.
In the preamble, we use the `\title` and `\author` command words.
Then in the body we use the `\maketitle` command word:

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{Waggleton P. Tallylicker}
\begin{document}
\maketitle
\end{document}
~~~

Compiling it shows something like this prominently:

![](fig/02-helloworld.png)

A lot of the time when we generate an article, we don't want the date in the title.
You can suppress it by adding an empty date to the preamble:

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{Waggleton P. Tallylicker}
\date{}
\begin{document}
\maketitle
\end{document}
~~~

Okay, we have an impressive title, but still no content.
Let's add a standard essay structure with an introduction, a body and a conclusion.

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{Waggleton P. Tallylicker}
\date{}
\begin{document}
\maketitle

\section{Introduction}

The existing literature does not adequately answer the question of,
``What even is internets?''


\section{Body}

We propose a solution that involves drinking large volumes of coffee.


\section{Conclusion}

There are still open problems that require more work.


\end{document}
~~~

![](fig/02-sections.png)
