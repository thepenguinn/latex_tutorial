---
title: LaTeX Tutorial
author: Daniel
---

# LaTeX Document

`latex` or `tex` source files ends with `.tex` extension.

## Document Structure

```latex

\documentclass[a4paper, 11pt]{article}
% preamble <- a comment by the way.

% Package imports, command declarations, format declarations etc goes here.
\begin{document}
% document

% Everything that needs to be rendered will goes here.
\end{document}
```
---
## Comments

Comments in LaTeX starts with a percent (`%`) sign.

```latex

% Hai, this is a comment in LaTeX.

% More comments.

```
---

## Commands

In LaTeX `commands` are also know as `macros`.

```latex
% Optional ---+-----------+
% Arguments   |           |
%             |           |
%             v           v
\documenclass[a4paper, 11pt]{article}
%                            ^     ^
%                            |     |
%                            |     |
%                            +-----+--- Arguments
```

- They are just like `functions` in other programming languages.
- You can define `custom` commands / macros on your own (more on that later...).

---

## Document Class

Every LaTeX document has a `\documentclass` declaration at the top.

```latex
\documentclass[a4paper, 11pt]{article}
%                             ^     ^
%                             |     |
%                             +-----+-- Document Class
```

There are several types:

- article
- book
- report
- memoir
- beamer

---

## Importing Packages

You can import various packages using `\usepackage{}` in LaTeX like so:


```latex

\documentclass[a4paper, 11pt]{article}

\usepackage[margin = 0.4in]{geometry} % Importing geometry package

\begin{document}

% Document content goes here.

\end{document}

```
---

## Environments

### Example

Environments in LaTeX starts with `\begin{}` and ends with `\end{}`.

```latex
%                 +--------+-------------+
%                 |        |             |
%                 v        v             |
\begin{tabularx} {\textwidth} {ccc} %    |
%                              ^ ^       |
%                              | |       |
%                              +-+-------+--- More Arguments
% Content specific to the
% environment goes inside here.
\end{tabularx}
```
---

### Another Example

```latex
\begin{figure} [h]
%              ^ ^
%              | |
%              +-+-------------+--- Optional arguments

% Content specific to the
% environment goes inside here.

\end{figure}

```

> `NOTE`
> We'll see these environments later.

---

## Chapters, sections and more...

```latex

\chapter{Name of the chapter}

\section{Name of the section}

\subsection{Name of the sub-section}

\subsubsection{Name of the sub-sub-section}

\paragraph{Start of the paragraph}

```

> `NOTE`
> Some of these functions are scoped depending on the `document class`

---

# Text Formatting

## Bold face

```latex
\textbf{This text is in bold.}
```
## Italic face

```latex
\textit{This text is in italics.}
```
> `NOTE`
> There's also `\emph{}` to emphasize text. But if you want the text to be always in italics, use `\textit{}`.

## Small caps face

```latex
\textsc{This text is in small caps.}
```
---

## Teletype face

```latex
\texttt{This text is in teletype.}
```

## Underline

```latex
\underline{This text is in bold.}
```

> `NOTE`
> You can also combine these. Like so:

```latex
\textbf{\textit{Text in bold and itlalics}}

```
---

## Quotes

`'` and `"` corresponds to the closing quotes. For the opening quotes you need to use
the grave sign.

```latex
``This is a Quote in LaTeX."
`This is also a Quote in LaTeX.'
```

---

# Labels and References

You can `\label` and `\ref` things in LaTeX.

```latex
\section{Introduction} \label{intro}

Introduction about something...

\section{Some other section} \label{someOtherSection}

As said earlier in section \ref{intro}...

```

> `NOTE`
> Anything in can be `labeled` and `referred` in LaTeX. So you don't have to worry about numbering
> anything in your life ever again.

---

# Including Images

## graphicx Package

Inorder to include images in your document, you need to use the `graphicx` package.
You can simply import the package by using:

```latex
% In the preamble
\usepackage{graphicx}
```

## Usage

After that, you can simply use `\includegraphics{}` macro to import the images, like so.

```latex
% Inside the document environment
\includegraphics[]{path-to-image}
```

---

## Tweaking Images

Once you included the image, you might want to scale or set the width and height of
the image. For that you can use some of the optional arguments `\includegraphics{}`
take. Like:

```latex
\includegraphics[
    width = \textwidth,
    height = 0.5\textheight,
    keepaspectratio,
] {path-to-image}
```

More optional arguments:

- scale
- angle
- clip

---

## Figure Environment

```latex
\begin{figure} [h] % <---------------------------------------------------+
                                                                       % |
    \centering % <------------------------- Centers the entire figure    |
                                                                       % |
    \includegraphics [ % <-------------+                                 |
        width = \textwidth,          % |                                 |
        height = 0.5\textheight,     % |                                 |
        keepaspectratio,             % |                                 |
    ] {path-to-image} % <--------------+--- Including image              |
                                                                       % |
    \caption{Caption to your image.} % <--- Caption to the figure        |
    \label{someImage} % <------------------ Internal labeling            |
                                                                       % |
\end{figure} % <---------------------------------------------------------+--- Entire figure environment
```
---

## Supported Formats

- .png
- .pdf
- .webm
- .jpg
- .eps

> `NOTE`
> You cannot directly import `.svg` using includegraphics. So you might need to convert
> it into `.pdf` or some other supported formats.

---

# Lists

## Enumerated Lists

These are `numbered` list.

```latex
\section{Shopping List}

\begin{enumerate}
    \item Bread.
    \item Butter.
    \item Popcorn.
    \item Lemons.
\end{enumerate}
```
---

## Itemized Lists

These are `unnumbered` or `bullet` list.

```latex
\section{Shopping List}

\begin{enumerate}
    \item Butter.
    \item Popcorn.
    \item Lemons.
    \item Bread.
\end{enumerate}
```

> `NOTE`
> You can also nest these environments.

---

# Mathematics

## Inline Maths

```latex
So here's the Pythagoras theorem: $a^{2} = c^{2} + c^{2}$.

Sum over a period: $\sum_{i = 0}^{N} i$.

Trigonometric functions: $\sin(x) \times \cos(x)$.

Integrals: $\int_{a}^{b} f(x) \: dx$.

Fractions: $\frac{a}{b}$ or $\dfrac{a}{b}$. % (you need amsmath package for \dfrac)
```
---

## Equation Environment

```latex
\section{Sum of natural numbers}

\begin{equation}
    % No empty lines allowed
    f(x) = \sum_{i = 1}^{x} i
    \label{eqn}
\end{equation}

From eqn. \ref{eqn} we can see that $f(x)$ calculates the sum of first
$x$ natural numbers.

```
---

## Align Environment

`align` environment aligns by the equal sign (`=`).

```latex
Let x be 3. Then eqn. \ref{eqn} becomes,

\begin{align}
    % no empty lines
    f(3) &= \sum_{i = 1}^{3} i \\
         &= 1 + 2 + 3
\end{align}

```

> `NOTE`
> Make sure you don't leave empty lines in these environments, otherwise you will get
> compile errors.

---

# Code Listing

## Inline Code

### Using \texttt

```latex
In order to use numpy, you can simply import it as \texttt{import numpy as np}.
More normal text.
```

### With Code Highlighting

For code highlighting you can use `minted` package.

```latex
\usepackage{minted} % in the preamble

\mintinline{language} {code} % inside the document
```
---

## Code Blocks

### Using verbatim environment

```latex
\begin{verbatim}

#include<stdio.h>

int main() {
    printf("Hello World!\n");
    return 0;
}

\end{verbatim}
```
---

### With Code Highlighting

You can use `minted` environment for highlighted code blocks.

```latex
 %             +-+-------+--- Language
 %             | |
 %             v v
\begin{minted} {c}

#include<stdio.h>

int main() {
    printf("Hello World!\n");
    return 0;
}
\end{minted}
```

---

# Hyperlinks

Inorder to use hyperlinks in the document, you need to use `hyperref` package.

You can import it as:

```latex
\usepackage{hyperref}
```

Then you can include links as:

```latex
%  Url ---+---------------------------------+  +----------------+--- Text
%         |                                 |  |                |
%         |                                 |  |                |
%         v                                 v  v                v
See \href{https://en.wikipedia.org/wiki/LaTeX}{\textbf{Wikipedia}} for a general info.
```
