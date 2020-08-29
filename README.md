![Latex Logo](https://i.ibb.co/H2bZ2DJ/LATEX.png)

# LATEX-Cheatsheet

This repo contains small code snippets (with explanation) that highlight the fundamentals of [LaTex](https://www.latex-project.org/) typesetting system.

## Table of Contents :book:

1. [Introduction](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#introduction)
2. [Paper Types](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#paper-types)
3. [Layout](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#layout)
4. [Packages](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#packages)
5. [Custom Commands](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#custom-commands)
6. [Document Environment](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#document-environment)
7. [Using Pictures](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#using-pictures)
8. [Spacing](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#spacing)
9. [Lists](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#lists)
   - [Bulleted](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#bulleted-lists)
   - [Numbered](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#numbered-lists)
   - [Definition](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#definition-lists)
10. [Tabbing](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#tabbing)
11. [Tables, Type Emphasis & Fonts](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#tables-type-emphasis--fonts)
12. [Accent Characters](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#accent-characters)
13. [More Type Emphasis](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#more-type-emphasis)
14. [Math Formulae](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#math-formulas)
15. [Text Boxes & Justification](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#text-boxes--justification)
16. [Referencing Content](https://github.com/Sammy-Nyakabau/LATEX-Cheatsheet#referencing-content)
---
### Introduction

> LaTeX is a high-quality typesetting system; it includes features designed for the production of technical and scientific documentation. LaTeX is the de facto standard for the communication and publication of scientific documents.

- Commands start with a `\name [optional arguments] {required arguments}`

---

### Paper Types

- Document will be printed on a4 paper, using the 12pt default font
- We can define that we want to use the report class template
- Other classes : article, book, letter, slides and others
- In the preamble we define document wide rules
- **Paper type** : _letterpaper_ (11 x 8.5 in), _a4paper_ (29.7 x 21 cm), _legalpaper_ (14 × 8.5 in), _a5paper_ (21×14.8 cm), _executivepaper_ (10.5×7.25 in), and _b5paper_ (25×17.6 cm)

#### Example | Paper Types

```tex
\documentclass[a4paper,12pt]{book}
```

---

### Layout

- Layout types are listed as optional arguments in the `/documentclass` command
- Layout Types:
  - **twocolumn** : 2 column pages
  - **legno** : Puts equation numbers on the left side
  - **flegn** : Left align equations versus center
  - **twoside** : Print on both sides of paper sss
  - **openright** : If twoside is used chapters begin on right hand page
  - **landscape** : If listed it displays in landscape

#### Example | Layout Types

```tex
\documentclass[a4paper,12pt, landscape, twocolumn]{book}
```

---

### Packages

- You can import packages to add functionality
- Get more info on any package by typing `texdoc PackageName` in the terminal or command line

#### Examples | Packages

- Define that we want to use English hyphenation
- http://mirrors.rit.edu/CTAN/macros/latex/required/babel/base/babel.pdf
- Page 20 for list of languages

```tex
\usepackage[english]{babel}
```

- Use Helvetica instead of the normal sans serif font

```tex
\usepackage[scaled=.92]{helvet}
```

- Others :

  - mathpazo (Palatino (Roman))
  - mathptmx (Times (Roman))
  - avant (Avant Garde (Sans Serif))
  - courier (Courier (Typewriter))
  - chancery (Zapf Chancery (Roman))
  - bookman (Bookman (Roman) Avant Garde (Sans Serif) Courier (Typewriter))
  - newcent (New Century, Avant Garde, Courier)
  - charter (Charter (Roman))

- Other Packages

```tex

% Improve justification document wide

\usepackage{microtype}

% Used to create filler text

\usepackage{blindtext}

% Used to include pictures

\usepackage{graphicx}

% Used to wrap text around pictures

\usepackage{wrapfig}

% Used to compact lists

\usepackage{enumitem}

% Used to customize the page layout of your LaTeX documents

\usepackage{fancyhdr}

% Improve output of math formulas

\usepackage{amsmath}

% Used to create an index

\usepackage{index}
\makeindex

```

---

### Custom Commands

- You can define your own commands
  - Anytime you type `\NTT\` New Think Tank will show

  ```tex
  \newcommand{\NTT}{New Think Tank}
   ```
  - Or, New Think Tank in **bold** 

  ```tex
  \newcommand{\NTTB}{\textbf{New Think Tank}}
   ```
  - We can add styling to whatever text is passed

  ```tex
  \newcommand{\typew}[1]{\texttt{#1}}

  % Using custom command 
  Style to \typew{typewriter}.
   ```

---

### Document Environment

- This block is called the environment
  - Prints the title, author and date
    ```tex
    \begin{document}
    \title{\Large{\textbf{LaTeX Cheatsheet}}}
    \author{Sammy Nyakabu}
    \date{today}

    \maketitle
    \let\cleardoublepage\clearpage
    ```

 

- Print a table of contents using info in section headings
  - Run Typeset twice to create it
    ```tex 
    \tableofcontents
    ```
  - Use roman numeral page numbering
    ```tex 
    \pagenumbering{roman}
    ```
  - Start numbering with page 2
    ```tex 
    \setcounter{page}{2}
    ```
 
- Clear default headers & footers
  ```tex 
  \pagestyle{fancy}
  ```

- Draw a decorative line at the top & bottom of the page
  ```tex 
  \fancyhf{}
  ```

- Styling the Header and the Footer
  ```tex 
  \renewcommand{\headrulewidth}{2pt}
  \renewcommand{\footrulewidth}{1pt}
  
  % Use different headers for even & odd pages
  
  % leftmark : Chapter title, number, LE - left side on even pages
  
  % Uppercase by default
  
  \fancyhead[LE]{\leftmark}
  
  % rightmark : Chapter title, number, RO - right side on odd pages
  
  % Make lowercase
  
  \fancyhead[RO]{\nouppercase{\rightmark}}
  
  % Use the same footer for pages
  
  \fancyfoot[LE,RO]{\thepage}
  ```

- Define the page style for all pages going forward
  ```tex 
  \chapter{Chapter Name}
  \blindtext
  \section{A Section}
  ``` 

- Squeeze another line on to the previous page
  ```tex 
  \enlargethispage{\baselineskip}
  ``` 
 
- Add a page break and stretch text to fill the page
  ```tex 
  \pagebreak
  ``` 

- Add a page break, but don't stretch text
  ```tex 
  \newpage
  ``` 
---

### Using Pictures

- Define where we want the image placed
  -  h : Here, t : Top of page, b : Bottom, p : Separate Page
      ```tex 
      \begin{figure}[ht]
      \centering
      ```
  -  Include picture and define width (height automatically scales)
  - Also scale=0.5 (Scales by half)
  - angle=90 (Rotate 90 degrees)
    ```tex 
    \includegraphics[width=8cm]{pic.png}
    \end{figure}
    ```
 
- Wrapping text around an image
  - Group the text and image
    ```tex
    \begingroup
    ```
 
  - Set space above and below float to 0
    ```tex
    \setlength{\intextsep}{0pt}
    ```

  - Set distance between columns
    ```tex
    \setlength{\columnsep}{15pt}
    ```
 
  - Text wraps around images
  - Position image to the right with r
  - Also can use l : Left, i : Inside Edge and o : Outside Edge
  - `0.45\textwidth` : Size image width relative to the text width
    ```tex
    \begin{wrapfigure}{r}{0.45\textwidth}
    \centering
    % Place image
    
      \includegraphics[width=\linewidth]{pic.png}
      % I can assign a label I can refer to later
      \caption{Pretty Picture}\label{fig:prettypic}
    \end{wrapfigure}
    
    \blindtext
    
    \endgroup
    ```
---

### Spacing
 
- `\\` creates a line break
 
- `\nolinebreak` prevents line breaks `\nolinebreak[1] - [4]` requests stronger

- Add a 10 pts of space between this line and the next
  ```tex
  If      we     use    multiple spaces     it    won't    matter\\[10pt]
  ```
 
- Cancel the indent
 
  - Eliminate paragraph indents with `\usepackage{parskip}`
 
    ```tex 
    \noindent Special characters can be escaped \% \$ \& \_ \textbackslash
    ```
 - Line Spacing
    - Increase the line spacing : singlespacing, onehalfspacing, doublespacing
    
    ```tex 
    \usepackage[onehalfspacing]{setspace}
    ```
- Another way to add space between paragraphs
 
  ```tex
  \bigskip
  ```
---

### Lists

#### Bulleted Lists

- Create a bulleted list
  - You can add an abbreviated name for the table of contents between []
  ```tex
  \section[Technologies]{Web Technologies}
  \begin{itemize}
    \item Browsers
    \item HTML and CSS
    \item Web Dev Frameworks
    % Create a list in a list
    \begin{itemize}
      \item ReactJS
      \item Angular
    \end{itemize}
    \item 6 Programming Languages
  \end{itemize}
  ```
 
- `\item[customNumbering]` allows for any numbering scheme
---
 
#### Numbered Lists

- You can change the numbering \arabic*, \alpha*, \Alph*, \roman*
- You can change the font just for the numbering
 ```tex
 /section{Programming Languages and their Frameworks }
\begin{enumerate}[label=\Roman*, font=\bfseries]
	\item JavaScript
	\begin{itemize}
		\item 1 ReactJS  
		\item 1 Angular  
		\item 1 ExpressJS  
	\end{itemize}
	\item Java
	\begin{itemize}
		\item Spring
		\item Structs
		\item Hibernate
	\end{itemize}
	\item Python
	\begin{itemize}
		\item Django
		\item Flask
		\item Web2py
	\end{itemize}
	\item Ruby
	\begin{itemize}
		\item Roda
		\item Ruby on Rails
	\end{itemize}
\end{enumerate}
 ```
- Nesting numbering goes from 1 to a to i. to A.
- You can compact the list by replacing enumerate with compactenum and itemize with compactitem and add `\usepackage{paralist}`
- You can compact lists with this
 ```tex
  \setlist{nolistsep}
 ```
 ---
 
 #### Definition Lists

 ```tex 
\begin{description}
	\item[JavaScript] React, Angular, Express, 
	\item[Java] Spring, Hibernate
	\item[Ruby] Roda, Ruby on Rails
	\item[Python] Django, Flask, Web2py
\end{description}
 ```
---

### Tabbing

```tex
\begin{tabbing}
 
% On setup row define where tabs occur and the space to set aside
 
Customer  \= Name \hspace*{1.5cm} \= Street \hspace*{1.5cm} \= City \\
 
% \> Jumps to the next tab
 
\> Sammy Nyakabau \> --- \> --- \\
\end{tabbing}
```
---
### Tables, Type Emphasis & Fonts
 
- Wrap a table around tabular to make captions

  ```tex
  \begin{table}
  % Define a table with 3 left aligned columns (Use c (Center) or r (Right)
  
  % The center | creates a vertical line
  
  \begin{tabular}{l|l|l}
  
  % Draw horizontal line
  
  % \usepackage{booktabs} provides different line thicknesses
  
  % \toprule, \midrule, \bottomrule
  
  \hline
  
  % & Defines the breaks in the table
  
  \textbf{Name} & \textbf{Command} & \textbf{Sample Text} \\
  \hline
  % \verb| | allows you to type commands
  
  emphasize & \verb|\emph| & \emph{abcdefgh} \\
  italic & \verb|\textit| & \textit{abcdefgh} \\
  slanted & \verb|\textbf| & \textbf{abcdefgh} \\
  bold & \verb|\emph| & \emph{abcdefgh} \\
  small capped & \verb|\textsc| & \textsc{abcdefgh} \\
  medium & \verb|\textmd| & \textmd{abcdefgh} \\
  upright & \verb|\textup| & \textup{abcdefgh} \\
  roman family & \verb|\textrm| & \textrm{abcdefgh} \\
  sans serif & \verb|\textsf| & \textsf{abcdefgh} \\
  typewriter & \verb|\texttt| & \texttt{abcdefgh} \\
  combo & \verb|\textup{\textbf{}}| & \textit{\textbf{abcdefgh}} \\
  \end{tabular}
  \caption{Ways to emphasize text}
  \end{table}
  ```
  ![Latex Table](https://i.ibb.co/tZhjkHW/LATEX.png)
 
- Leave some columns blank & merge others
 
 ```tex 
  % Create 3 columns
  
  \begin{tabular}{@{}*3l@{}}
  
  % Take up to columns with Name and 1 with age
  
  \multicolumn{2}{c}{Name} &
  \multicolumn{1}{c}{Age}\\
  
  % Add headers with the last left blank
  
  First & Last & \\
  \hline
  Sammy & Nyakabau & 00\\
  Jane & Doe & 00\\
  \end{tabular}//
 ```
---

### Accent Characters

- These is a package that allows you to enter accented characters
- `\usepackage[utf8]{inputenc}` on Linux/MacOS and 
- `\usepackage[latin1]{inputenc} on Windows`
  ```tex
    \'{a} \^{e} `{o} \"{u} \.{a} \={o} \~{n} \u{a} \H{a} \v{e} \t{oo} \c{c} \d{n} \b{i}
  ```
- There are numerous fonts [here](http://www.tug.dk/FontCatalogue/) 
---

### More Type Emphasis 
 
-  Abbreviate listing in table of contents to just Type and make sans serif font
- I use label here so I can refer to this section later
 
  ```tex
    \section[Type]{\textsf{Type Emphasis \& Sizing}} \label{sec:typeemp}
  ```
 
- If you want font changes to continue `\itshape` *italic*, `\slshape` slanted, `\scshape` small caps, `\upshape` upright, `\normalfont` back to normal
 
- As you change text size that size remains after the command
 ```tex
  Get Smaller : \normalsize{normal}, \small{small}, \footnotesize{footnote}, \scriptsize{script}, \tiny{tiny}
  
  Get Bigger : \large{large}, \Large{larger}, \LARGE{larger}, \huge{huge}, \Huge{Hugest}
 ```
 
- Apply sizing change over a block of text
 ```tex
  \begin{LARGE}
    I want to use a big font
  \end{LARGE}

  \normalsize{Back to normal}
 ```
- More on Font Families

```tex 
\section{\textsf{Font Families}}
We can {\sffamily temporarily change} a font family, \ttfamily or change it for the rest of the document \sffamily
```
 
- Create quotes

```tex
\begin{quote}
``I like long walks, especially when they are taken by people who annoy me.'' 
- Fred Allen
\end{quote} 
```
---

### Math Formulas 
 
- Using this package : `\usepackage{amsmath}`
- `flalign*` with formula surrounded with `&`s makes it left justified
 
  - Quadratic Equation
  ```tex
  \begin{flalign*}
    & ax^2 + bx + c = 0 &\\
  \end{flalign*}
  ```
- Place a formula in text
  ```tex
  This \( ax^2 + bx + c = 0 \) is the quadratic equation \\
  ```
- I prefer the $ TeX shortcut
  - Quadratic Formula
  ```tex
  $x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$ \\
  ```
 
- List of LaTeX Symbols http://www.rpi.edu/dept/arc/training/latex/LaTeX_symbols.pdf
 

```tex
  Greek letters $\alpha \beta \gamma \delta \epsilon \zeta \eta \theta 
\vartheta  \iota \kappa \lambda \Lambda \mu \nu \xi \Xi \pi \Pi
\rho \varrho \sigma \Sigma \tau \upsilon \Upsilon \phi \varphi \Phi
\chi \psi \Psi \Omega \omega $ \\ 
 
Script letters $\mathcal{A}, \mathcal{B}$
 
Subscript $t_0$ \\ 
 
Superscript $x^2$ \\ 
 
Vectors $\vec{a}\cdot\hat{x}=a_x$
 
Matrices
$\begin{pmatrix} 
1 & 2 \\ 
3 & 4 
\end{pmatrix}$
 
Integrals $\Delta x=\int_{t_0}^{t_1} v(t)dt$ \\
 
Limits $\lim_{x\to0} \frac 1 x = \infty$ \\ 
 
Summations $e^x=\sum_{n=0}^\infty\frac{x^n}{n!}$ \\
 
Operators $\arccos, \arcsin, \arctan, \arg, \cos, \cosh, \cot, \coth, \deg, 
\det, \dim, \exp, \gcd,\\ \hom, \inf, \ker, \lim, \lg, \liminf, \limsup, \ln, \log, 
\max, \min, \Pr, \sec, \sin, \sinh, \sup, \tan, \tanh$ \\
 
Arrows $\leftarrow, \Leftarrow, \rightarrow, \Rightarrow, \leftrightarrow, \rightleftharpoons,
 \uparrow, \downarrow, \Uparrow, \Downarrow, \Leftrightarrow, \Updownarrow, \mapsto, \longmapsto, 
 \nearrow, \searrow, \swarrow, \nwarrow, \leftharpoonup, \rightharpoonup, \leftharpoondown, \rightharpoondown$ \\
 
 Relational Operators $ \geq, \gg, \leq, \ll, \neq $ \\
 
Binary Operation/Relation Symbols $ \approx, \asymp, \bowtie, \cong, \dashv, \doteq, 
\equiv, \frown, \mid, \models, \parallel, \perp, \prec, \preceq, \propto, \sim, \simeq, \smile, 
\succ, \succeq, \vdash $ \\
```
---
### Text Boxes & Justification 
  
- You can center text
 
```tex
  {\centering
  Get in the middle of me\\
  Okay\\[10pt]
  }
```
 
- Create a fully justified column 4cm wide
 
```tex
 \parbox{4cm}{I used to think I was indecisive, but now I'm not too sure.}
```
 
- `[t]{2cm}` aligns to top, `[b]` aligns to bottom, `[s]` stretches vertically, `[c]` centers
- `\quad` adds horizontal spacing between the boxes
 
 ```tex
  \quad\parbox{2cm}{I used to think I was indecisive, but now I'm not too sure.}
  % You can define hyphenation with\-
  \quad\parbox{2cm}{Always re\-mem\-ber that you're unique. Just like everyone.}
  % raggedright eliminates justification and hyphenation (Justifies Left)
  
  % You can do this document wide if typed in the preamble
  
  \quad\parbox{2cm}{\raggedright I always wanted to be somebody, but I should have been more specific.}
  % raggedleft eliminates justification and hyphenation (Justifies Right)
  
  \quad\parbox{2cm}{\raggedleft When I was a kid my parents moved a lot, but I always found them. }
 ```
 
- Minipages are blocks of text that will maintain size restrictions
 
```tex
\begin{minipage}{5cm}
 
One advantage of talking to yourself is that you know at least somebody's listening.
 
\end{minipage}
```
---

### Referencing Content

- You can add footnotes and override the numbering 
- Add a 5 pts of space between this line and the next
```tex
The answer you're looking for is inside of you, but it's wrong.\footnote[2]{author unknown} \\[5pt]
``` 
- You can get the section with `\ref` and the page with `\pageref`
 
```tex
  There is a great table on Type Emphasis is in this section~\ref{sec:typeemp} on page~\pageref{sec:typeemp}\\[2pt]
  There is a pretty picture in section~\ref{fig:prettypic} on page~\pageref{fig:prettypic}\\[2pt]
```

- Listing references in a bibliography
 
```tex
How I learned my ABCs \cite{ABCAFR}. 
 
\begin{thebibliography} {books}
\bibitem{ABCAFR} Walter Abish \emph{The Alphabetical Africa}, 1974
\end{thebibliography} 
```
---
 

 