# Laboration-2-Computer-Technology-I

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% LEGv8 Lab Template for Students
% Adapted from a template by Björn Lindenberg, LNU
% Modified for 1dt301 by Christian Artback, 2025
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\documentclass[a4paper, 12pt, oneside]{article}
\renewcommand{\baselinestretch}{1.5}
\usepackage[T1]{fontenc}
\usepackage{blindtext}
%\usepackage[english]{babel}
\usepackage[utf8]{inputenc}
\usepackage{geometry}
\usepackage{times} % Times New Roman
\usepackage{graphicx}
\usepackage{subcaption}
\usepackage[pages = some]{background}
\usepackage{anyfontsize}
\usepackage{tikz}
\usepackage{rotating}
\usepackage{float}
\usepackage{lastpage}
\usepackage{fancyhdr}
\usepackage[noindentafter]{titlesec}
\usepackage[titletoc,title]{appendix}
\graphicspath{{./figures/}{./}}
%%% You paper specific packages
\usepackage{lipsum} % For dummy text. Delete.
\usepackage{amsmath,amssymb,amsthm}
\usepackage{enumerate}
\usepackage{url} 
\usepackage{hyperref}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{enumitem}
\usepackage{siunitx}
\usepackage{forest}
\usepackage[many]{tcolorbox} % load tcolorbox with extra features


\tcbset{
  myinstr/.style={
    colback=gray!10,       % light background
    colframe=gray!70,      % frame color
    boxrule=0.5mm,         % thickness of frame
    arc=2mm,               % rounded corners
    left=2mm, right=2mm,   % horizontal padding
    top=1mm, bottom=1mm,   % vertical padding
    breakable
  }
}

\definecolor{mygreeni}{HTML}{4CAF50} % green shade
\definecolor{mygreenii}{HTML}{388E3C} % darker green shade


%% if you find a keyword is lacking please add it. %%
\lstdefinelanguage{LEGv8}{
  morekeywords={
    ADD, SUB, AND, ORR, LSL, LSR, LDUR, STUR, CBZ, CBNZ, B, BL, BR, NOP,
    MOVZ, MOVK, MUL, SDIV, UDIV %%ADDI%%
  },
  sensitive=true,
  morecomment=[l]{//},
  morecomment=[s]{/*}{*/},
  morestring=[b]"
}


\lstset{
  language        = LEGv8,
  basicstyle      = \ttfamily\small,
  keywordstyle    = \color{blue}\bfseries,
  stringstyle     = \color{orange},
  commentstyle    = \color{gray}\itshape,
  showstringspaces= false,
  frame           = single,
  backgroundcolor = \color{gray!10},
  breaklines      = true,
  numbers         = none,       % important: avoid line numbers
  columns         = fullflexible
}

%CHANGE in this PART where APPLICABLE
% Paper subject, paper title, supervisor, author, semester, course here
% You can change any categories in the command \bgsetuptab below
\newcommand{\papersubject}{Lab Assignment 1} 
\newcommand{\papertitle}{LEGv8 Assembly Programming} % Change this to your title!
\newcommand{\papersubtitle}{Computer Technology 1 \\ \today} % Remove this if you do not have a subheading!
\newcommand{\givenname}{John} % Given name(s) / First name(s)
\newcommand{\surname}{Doe} % Surname / Family name
\newcommand{\auth}{\givenname~\surname} % Combined Author Name
\newcommand{\superv}{Supervisor Name} % Supervisor name
\newcommand{\sem}{HT25} % Semester
\newcommand{\subj}{Your Program} % Your program here
\newcommand{\course}{1dt301} 

\input{config} %%DO NOT CHANGE THIS FILE

\begin{document}
%%%% Creates title page, table of contents and headers %%%%
\newgeometry{top=5.47cm, bottom=3.9cm, inner=2.54cm, outer=2.54cm}
\maketitle
\thispagestyle{empty}
\makeatletter
\AddThispageHook{\bgsetupetch
\bg@material
}
\AddThispageHook{\bgsetuptab
\bg@material
}
\AddThispageHook{\bgsetupline
\bg@material
}
\AddEverypageHook{\bgsetupheadtree
\bg@material
}
\AddEverypageHook{\bgsetupheaduni
\bg@material
}
\makeatother
\clearpage


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

%%%%%%%% Your Content begins here %%%%%%%%%%%%
\section*{Task 1 – Basic Instructions in LEGv8}
%% Please use listings for each codeblock! %% 
%% if you find a keyword you utilized is lacking please add it, see for example ADDI %%
Write the following code in the simulator and run it:
(Assemble and execute all instructions)
\begin{lstlisting}[caption={LEGv8 program for Task 1}]
        MOVZ    X0, #5
        MOVZ    X1, #10
        ADDI    X1, X1, #2
        ADD     X2, X0, X1
\end{lstlisting}

\noindent\rule{\linewidth}{0.4pt}

Add a screenshot of you having run the program.
Remove the task 1 example and add your own screenshot of the program where you have executed all instructions and the result is visible in register x0

\begin{center}
\includegraphics[width=1\textwidth]{screenshots/task1.png}
\end{center}

\subsection*{Answer}

The number stored in register X2 is:

\clearpage

\section*{Task 2 – Machine Code to LEGv8 Assembly}

Below is an example, Remove this and add the given instruction binaries.

\begin{tcolorbox}[myinstr]
    \textbf{Instruction 0}
    
    \textbf{Machine Code:} \texttt{10001011000000010000000000000010}
    
    \textbf{Assembly:}
    \begin{lstlisting}[language=LEGv8]
    ADD X2, X0, X1
    \end{lstlisting}
    
    \textbf{Explanation:} Add X0 and X1, store the result in X2.
\end{tcolorbox}

\begin{tcolorbox}[myinstr]
    \textbf{Instruction 1}
    
    \textbf{Machine Code:} \texttt{10001011000000010000000000000010}
    
    \textbf{Assembly:}
    \begin{lstlisting}[language=LEGv8]
    ADD X2, X0, X1
    \end{lstlisting}
    
    \textbf{Explanation:} Add X0 and X1, store the result in X2.
\end{tcolorbox}


\clearpage

\section*{Task 3 - LEGv8 Arithmetic}
Create a LEGv8 Assembly program to calculate the value of the following
expression:
$$ 4 \cdot 5 + 16 \cdot 11 + 25 $$
When finished, the result shall be stored in register x0.

\subsection*{Code}
\begin{lstlisting}[caption={LEGv8 program for Task 3}]
adsafasdf

asdfasdfasdf


asdfasdf


\end{lstlisting}

\subsection*{Screenshot}

Supply a screenshot of the program where the result in register x0 is visible.

\subsection*{Explanation}
Briefly explain how calculated the arithmetic expression. 

\clearpage

\section*{Task 4 – Sum of Large Numbers}

\textbf{Instruction:} Write a LEGv8 Assembly program to calculate the sum
$$1\,893\,423 + 443\,924$$

\noindent The numbers are decimal integers.
You will probably encounter a problem to load these large numbers into registers, so you will have to find a way to solve this problem!

%% Use a code listing just as above %%
\subsection*{Code}
\begin{lstlisting}[caption={LEGv8 program for Task 4}]
\end{lstlisting}

\subsection*{Screenshot}

Supply a screenshot of the program where the result is visible and write in the image caption which register shows the result. 

\subsection*{Explanation}
Briefly explain how you loaded large numbers and calculated the sum.


\clearpage

\section*{Task 5 – Sum of Odd Numbers}
Write a LEGv8 Assembly program to calculate the sum

1 + 3 + 5 + ... + 99.

When finished, the sum shall be stored in register x1.

\subsection*{Code}
\begin{lstlisting}[caption={LEGv8 program for Task 5}]
\end{lstlisting}

\subsection*{Screenshot}

Just as above supply a screenshot of the program where you have executed all instructions and the result is visible in register x1. 

\subsection*{Explanation}
Briefly explain the logic and how you sum the odd numbers.



\clearpage

\section*{Task 6 – Sum Numbers Stored in Memory}

\textbf{Instruction:} Write a loop to add all the numbers stored in memory. When finished, the result shall be stored in register x0.

\subsection*{Memory Initialization (provided)}
\begin{lstlisting}[language=LEGv8]
// Set up base memory address
MOVZ X7, #0x1000, LSL #16

// Store the numbers 1, 4, 1, 5, 9, 2 in memory
MOVZ x1, #1
STUR x1, [x7, #0]
MOVZ x1, #4
STUR x1, [x7, #8]
MOVZ x1, #1
STUR x1, [x7, #16]
MOVZ x1, #5
STUR x1, [x7, #24]
MOVZ x1, #9
STUR x1, [x7, #32]
MOVZ x1, #2
STUR x1, [x7, #40]
\end{lstlisting}

\subsection*{Code}
\begin{lstlisting}[caption={LEGv8 program to sum memory values}]
\end{lstlisting}


\subsection*{Screenshots}

Provide a screenshot of the fully executed program with the result showing in register x0. 

\subsection*{Explanation}
Explain the logic you used to add the numbers stored in memory.



\clearpage

% ---------------- References (Optional) ----------------
% If you want to add references, you can use BibTeX.
% See guides here: 
% https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex
% Example usage:
% \bibliographystyle{IEEEtran}  % Choose a bibliography style
% \bibliography{ref.bib}        % Use your .bib file
% \clearpage                     % Start a new page after references



\end{document}

