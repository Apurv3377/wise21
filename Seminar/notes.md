% This is samplepaper.tex, a sample chapter demonstrating the
% LLNCS macro package for Springer Computer Science proceedings;
% Version 2.20 of 2017/10/04
%
\documentclass[runningheads]{llncs}
%
\usepackage{graphicx}
% Used for displaying a sample figure. If possible, figure files should
% be included in EPS format.
%
% If you use the hyperref package, please uncomment the following line
% to display URLs in blue roman font according to Springer's eBook style:
% \renewcommand\UrlFont{\color{blue}\rmfamily}

\begin{document}
%
\title{ICT Degradation Modelling}
%
%\titlerunning{Abbreviated paper title}
% If the paper title is too long for the running head, you can set
% an abbreviated paper title here
%
\author{Pranav Deo\inst{1} \newline Matriculation number 104145}
%Matriculation Number: 104145
%
\authorrunning{F. Author et al.}
% First names are abbreviated in the running head.
% If there are more than two authors, 'et al.' is used.
%


\institute{Universitat Passau, 94032, Passau, Germany \\
\email{deo01@ads.uni-passau.de}
}

%
\maketitle              % typeset the header of the contribution
%
\begin{abstract}

With the advent of Cyber-Physical Energy Systems (CPES) and their application on Smart Grids (SG), the integration of Communication Technologies (ICT) and Power Systems (PS) have been rooted deeply. ICTs and PS in such environments have heavy mutual inter-dependencies on one another. Failures in ICT can disrupt PS, while failures in PS could disrupt ICTs due to lack of energy, thus leading into  cascading system failures. While the ENTSO-ESSC provides classification systems for classifying PS operation states to determine PS degradation, such comparable systems are not available for ICTs. In this paper, we attempt to understand various components of an ICT system, and understand the various operation states of the ICT components. We attempt to survey the distribution network technologies as a part of the SG paradigm, and isolate components of interest. The essential properties such as availability and reliability are determined and used to map the states of components. Since distribution networks can be treated as Markov models, we attempt to design degradation models of the distribution networks using Markov chain analysis. 

\keywords{Cyber-Physical Energy Systems \and Information and Communication Technology \and [More to follow later]}
\end{abstract}

\section{Introduction}

The ENTSO-ESSC is a system state classification that is implemented to determine the operational state of a Power System. ESSC however does not regard for the impact that the ICT system has on determining the operational state of a PS. 
ENSTO-E PS state classification defines five various states - Normal, Alert, Emergency, Blackout a Restoration. There is a change in the system state each time a failure may occur. For example, a certain failure may escalate the PS from a Normal state to an Alert state. In this paper, we shall attempt to understand if such a classification can be implemented on an ICT systems, and what components can be understood to achieve such a classification.

\section{Background Work}

In \cite{paper1}, there is an attempt to understand the bridge between the PS and ICT state classifications, and to isolate the elements, which could be used as properties to define system states. The study is adopts from the ResiliNets project (reference patil paper) with the difference being a slight deviation in the definition of what an operation state is. While the ResiliNets project only consider the network and the service that it provides, the paper accounts for both the network infrastructure and the various services that it provides while defining the operational state. The three Key Performance Indicators (KPIs) considered are those of availability, Accuracy and Latency. As such three states were defined as follows - Normal State, Limited State and Failed State.

2018 kamp refernce
In a study on modelling communication technologies to find the Distribution Grid's reliability, the ICT components are 




\subsection{A Subsection Sample}
Please note that the first paragraph of a section or subsection is
not indented. The first paragraph that follows a table, figure,
equation etc. does not need an indent, either.

Subsequent paragraphs, however, are indented.

\subsubsection{Sample Heading (Third Level)} Only two levels of
headings should be numbered. Lower level headings remain unnumbered;
they are formatted as run-in headings.

\paragraph{Sample Heading (Fourth Level)}
The contribution should contain no more than four levels of
headings. Table~\ref{tab1} gives a summary of all heading levels.

\begin{table}
\caption{Table captions should be placed above the
tables.}\label{tab1}
\begin{tabular}{|l|l|l|}
\hline
Heading level &  Example & Font size and style\\
\hline
Title (centered) &  {\Large\bfseries Lecture Notes} & 14 point, bold\\
1st-level heading &  {\large\bfseries 1 Introduction} & 12 point, bold\\
2nd-level heading & {\bfseries 2.1 Printing Area} & 10 point, bold\\
3rd-level heading & {\bfseries Run-in Heading in Bold.} Text follows & 10 point, bold\\
4th-level heading & {\itshape Lowest Level Heading.} Text follows & 10 point, italic\\
\hline
\end{tabular}
\end{table}


\noindent Displayed equations are centered and set on a separate
line.
\begin{equation}
x + y = z
\end{equation}
Please try to avoid rasterized images for line-art diagrams and
schemas. Whenever possible, use vector graphics instead (see
Fig.~\ref{fig1}).


---- Bibliography ----
%
% BibTeX users should specify bibliography style 'splncs04'.
% References will then be sorted and formatted in the correct style.
%
% \bibliographystyle{splncs04}
% \bibliography{mybibliography}
%
\begin{thebibliography}{8}

\bibitem{paper1}
Klaes et al. Energy Informatics 2020, 3(Suppl 1):16
https://doi.org/10.1186/s42162-020-00119-3


\bibitem{ref_article1}
Author, F.: Article title. Journal \textbf{2}(5), 99--110 (2016)

\bibitem{ref_lncs1}
Author, F., Author, S.: Title of a proceedings paper. In: Editor,
F., Editor, S. (eds.) CONFERENCE 2016, LNCS, vol. 9999, pp. 1--13.
Springer, Heidelberg (2016). \doi{10.10007/1234567890}

\bibitem{ref_book1}
Author, F., Author, S., Author, T.: Book title. 2nd edn. Publisher,
Location (1999)

\bibitem{ref_proc1}
Author, A.-B.: Contribution title. In: 9th International Proceedings
on Proceedings, pp. 1--2. Publisher, Location (2010)

\bibitem{ref_url1}
LNCS Homepage, \url{http://www.springer.com/lncs}. Last accessed 4
Oct 2017
\end{thebibliography}


\end{document}
