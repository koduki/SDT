% How to make keynote like presentation with Markdown
% @koduki
% Oct 27, 2013

Introduction
================================================================================
## Why am I not satisfied with PowerPointa and Keynote?
- PowerPoint or keynote are a good tool.
- But this has some problems.
	- It is hard to be the same layout. (Template is freedom too.)
	- It needs a Office Application.
	- Binary! This means is that git or svn do not good work.

Solution => Markdow and Panddoc
================================================================================
## Markdown
- Markdown is simple text format!
- Git or svn work very good.
- It is easy-to-read and easy-to-write.
- It provides a simple sentence structure.

## Pandoc
- Pandoc is multi format transrator. (HTML, PDF, docx, markdown, LaTex, reStructuredText...)
- This is able to make slide from markdown. 
- Not only HTML base(ex. s5) but also PDF is.

How to use
================================================================================
## Install Pandoc.
- Mac is download pkg.
http://code.google.com/p/pandoc/downloads/

## Tex to generate PDF 
- Install MacTex(please select suit your platform)
http://tug.org/mactex/

## Run command
```{.sh}
$ pandoc -t beamer test.md -o test.pdf
```

Example
================================================================================
!["default slide"](./images/slide-sample01.png)

Change Template
================================================================================
## Download and Copy
- I want use keynote like presentation desigin.
- Download this [beamerthemeKeynoteLikeGradient.sty](https://sites.google.com/site/tokeijikakenoringo/Home/keynote-like-gradient-theme-for-latex-beamer).
```{.sh}
$ sudo cp ./beamerthemeKeynoteLikeGradient.sty /usr/local/texlive/2013/texmf-dist/tex/latex/beamer/themes/theme/
```

## Update Theme Index
- Run "Tex Live Utility"
- re-install someting package.(Mabey there is better solution. :P )

## Run command
```{.sh}
$ pandoc -V theme:KeynoteLikeGradient -t beamer test.md -o test.pdf
```

Modify code block desigin.
================================================================================
## Using listing option.
- Default code block is very simple.
- Listing is code format module.
```{.sh}
$ pandoc --listings -t beamer test.md -o test.pdf
```
- Make header.tex. This is some settings(font, background, line...)
- Add "-H" option, for header.
```{.sh}
$ pandoc -H header.tex --listings -t beamer test.md -o test.pdf
```

header.tex sample.
================================================================================
```{#tex}
\usepackage{listings}
\lstset{%
 %language={sh},
 backgroundcolor={\color[rgb]{0.1, 0.1, 0.1}},%
 basicstyle=\footnotesize,%
 commentstyle=\textit,%
 classoffset=1,%
 keywordstyle=\bfseries,%
 frame=tRBl,framesep=5pt,%
 breaklines=true,
 showstringspaces=false,%
 %numbers=left,stepnumber=1,numberstyle=\footnotesize%
}
```

Conclusions
================================================================================
- Markdown and Pandoc are good tool for typical presentation document.
- If you want to make graphical presentaion, You should use PowerPoint or Keynote.
- But if you want to make typical presentation document quickly and lightweight, You try run this command.
```{.sh}
$ pandoc --listings -H header.tex -V theme:KeynoteLikeGradient -t beamer test.md -o test.pdf
```
- This code is following url.
https://gist.github.com/koduki/7183121

- Happy Hacking!

