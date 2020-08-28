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
8. Spacing
9. Lists
   - Bulleted
   - Numbered
   - Definition
10. Tabbing
11. Tables, Type Emphasis & Fonts
12. Accent Characters
13. More Type Emphasis
14. Math Formulae
15. Text Boxes & Justification
16. Referencing Content

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



 

 

 