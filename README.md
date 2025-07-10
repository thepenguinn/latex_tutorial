# History

# Why?

# Document structure

A LaTeX document can consist of several files or can be of merely a single file.
In this tutorial we will be looking at a single file document. So let's see the
typical structure of a LaTeX document.

```latex
\documentclass[a4paper]{article}
% preamble

\begin{document}
% document

\end{document}
```

As we can see every LaTeX document will have a structure similar to the above.
There will be a `\documentclass` declaration at the top and a `document` environment.
Everything between `\begin{document}` and `\end{document}` consist of the actual
thing that will be rendered to the output (ie, to the pdf). And everything above
`\begin{document}` and below `\documentclass{}` consist of the preamble. The preamble
consists of things like package imports, formatting declarations, macro declaration etc.

## Commands

Every command in LaTeX starts with a `\` backslash. And can take arguments in curly
brackets, and optional arguments in side square bracket. By the way a command in
LaTeX is also called a `macro`.

```latex
\macro[optional arguments with comma separated]{first argument}{second argument}
```

## Comments

Comments in LaTeX are started with a percentage sign.

```latex
% Hai, this is a comment in LaTeX.
```

## Documentclass

Every LaTeX document has a `\documentclass` declaration at the top.

```latex
\documentclass[a4paper]{article}
```

In LaTeX there are several types (or classes) of documents. Some of them are:

- article
- book
- report
- memoir
- beamer

The `\documentclass` macro specifies the class of the document. Each of these classes
determines the commands that are available and the way the final document is rendered.

# Basic formatting

# Label and refer

# Including images

# Tables

# Drawing

# Plotting

# Miscellaneous
