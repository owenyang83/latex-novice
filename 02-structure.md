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
LaTeX fixes this with the ability to quickly switch between different document types,
keep track of sectioning, manage cross-references, and much more.
Unlike TeX, LaTeX does not require any knowledge of programming.

We will now have a look at the basic structure required to set up any LaTeX project.

Every LaTeX document can be thought of as having two parts:

* Preamble
* Body

The preamble is where we tell LaTeX what sort of document we're writing, 
and which non-default resources we'd like to use.
It is also a good place to customise the way we use LaTeX.
For example, we can define our own command words,
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

Other document classes are available if you install them.
How best to do this partly depends on your operating system.

In fact, some of the non-default classes are used much more often than the ones listed above.
For example, to make a presentation in LaTeX, most people will use *beamer* rather than Slides;
and when people use LaTeX for writing long books, *memoir* is a popular document class.
However, in these lessons, we'll focus on the built-in article and report classes.

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

As you can see, this is a bit longer and more complicated than the simplest plain TeX document.
It pays off, though, because now some infrastructure is in place that lets
us get to work on non-trivial projects.

> ## A first LaTeX document {.challenge}
> 
> At the end of the previous lesson on plain TeX,
> you created a small document that tested your knowledge
> of dashes, quotation marks and other special characters.
> 
> Now rewrite that document as a LaTeX document,
> then compile it using `pdflatex` (instead of `pdftex`).

To walk through the creation of a larger project,
we'll now begin to build up a template that you can use later.

First we'll look at how to add a title.
It is possible to write a title page from scratch, and this is the only way to
do it if there is a particular style you want to achieve.
However, for most cases it is possible to use much simpler built-in commands.

This needs to be done in two steps.
First in the preamble we specify some fields using the `\title`, `\author` and `\date` command words.
All these fields are optional.
Then in the document body we use the `\maketitle` command word.

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{J. Smith}
\begin{document}
\maketitle
\end{document}
~~~

This compiles into a document that looks like this:

![](fig/02-.png)

A lot of the time when we generate an article, we don't want the date in the title.
Let's suppress it by adding an empty date to the preamble:

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{J. Smith}
\date{}
\begin{document}
\maketitle
\end{document}
~~~

Now we'll add a standard essay structure with an introduction,
a body and a conclusion, and some filler text so you can see how it all hangs together.

~~~ {.tex}
\documentclass{article}
\title{Hello World}
\author{J. Smith}
\date{}
\begin{document}
\maketitle

\part{Introduction}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit sem, diam accumsan.
Tortor quis, porta mus mattis consequat curae venenatis est, natoque lobortis fusce ad.
Dui sollicitudin.


\section{}

Lorem ipsum dolor sit.
Suspendisse proin primis scelerisque risus hymenaeos aliquet dictum eros scelerisque.
Primis et praesent tellus, tortor.


\section{}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit pede.
Mauris feugiat aliquet odio arcu ridiculus litora, adipiscing pellentesque integer, dignissim diam scelerisque id, litora consectetuer tincidunt.
Sagittis non, natoque a, scelerisque dis, diam diam bibendum.


\part{Body}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit orci netus elementum eros duis integer id, ante.
Pellentesque feugiat nibh eu.
Eget posuere consequat.


\section{}

Lorem ipsum.
Urna iaculis amet, erat.
Amet posuere pede, nisl, risus felis, class a, aliquam tempus, sit id arcu.


\section{}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit per.
Risus phasellus praesent erat auctor cursus, morbi felis pharetra donec, ad nisi habitasse.
Augue.


\part{Conclusion}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit eu lorem elementum.
Aptent vulputate ad, mollis nec, odio.
Laoreet ve, faucibus bibendum, felis enim duis.


\section{}

Lorem ipsum.
Ridiculus.
Ornare a, vestibulum sem, fusce vivamus nam, nostra.


\section{}

Lorem ipsum dolor sit amet, consecteteur adipiscing elit in. Ridiculus. Eros.


\end{document}
~~~

![](fig/02-.png)

