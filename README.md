![Latex Logo](https://i.ibb.co/H2bZ2DJ/LATEX.png)

# LATEX-Cheatsheet

This repo contains small code snippets (with explanation) that highlight the fundamentals of [LaTex](https://www.latex-project.org/) typesetting system.

## Table of Contents :book:

1. Introduction
2. Paper Types
3. Layout
4. Packages
5. Custom Commands
6. Document Environment
7. Using Pictures
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
