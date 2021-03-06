WCM Thesis Template
---
The LaTeX template is placed in `main/dissertation.tex` and you can view the compiled PDF file in `main/dissertation.pdf`.

### Why you should use LaTeX templates instead of Word:
 - [Have a read](https://axiezai.github.io/thoughts/2022/01/06/why-latex.html)
 - All formatting already done for you.
 - Automatically generated table of contents, list of figures/tables, and bibliography.
 - Clearly defined sections for your thesis.
 - Referencing and hyperlinking your figures, chapters, sections, equations in your pdf.
 - Automatic placement of figures without manually dragging and resizing.
 - Easy entry of math symbols and equations.
 - Large Word files are heavy and prone to crashing, LaTeX files are lightweight and all contents are kept separately until compilation, so no crashing or fears of losing your work progress.

### Attributions
 - Adapted from https://github.com/axiezai/dissertation, feel free to take a look as an example of a complete thesis. 
 - Modified from Cornell University's [templates](https://gradschool.cornell.edu/academic-progress/thesis-dissertation/templates/) resources. 
 - Used LaTeX template examples from <em>overleaf</em>.

### How to compile:
For beginners that's never touched LaTeX before, you will need:

- LaTeX compilers like `pdflatex` and `bibtex` to turn text files into a beautiful PDF. MacOS users familiar with the commandline should have `brew` setup and follow [this](https://formulae.brew.sh/cask/mactex-no-gui) to install the necessary compilers. More details can be found at [https://www.latex-project.org/get/](https://www.latex-project.org/get/).

- A plain text editor of any sort, there are ones made for LaTeX specifically.
    - I personally used [`texmaker`](https://www.xm1math.net/texmaker/), remember to go to Preferences and edit <em>Quick Build</em> to `pdflatex + bib(la)tex + pdflatex + View PDF` for a smooth experience. Change the font size and other preferences while you are at it for your comfort.
    - For coders, use [`VSCode`](https://code.visualstudio.com/) with the [`LaTeX Workshop`](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension, it's quite lightweight and you can add a bunch of other text editing extensions for quite a good experience.
    - Here's quite a large list of other options: https://tex.stackexchange.com/questions/339/latex-editors-ides
    - Don't want to download anything and try out LaTeX? Head to <em>[overleaf](https://www.overleaf.com/)</em> and use their online editor with any journal's template. I don't recommend creating your entire thesis online, it will take a long time to compile and you will have to upload a lot of stuff.


You will only `build` the `main/dissertation.tex` file. It includes everything you will need. For experienced `git` users, feel free to `clone` this repository and start your own project by copying over `main/{dissertation.tex,hangcaption.sty,cornell.cls}` to your repo. Then create a blank `References.bib` and copy over from a citation manager your desired references in `bibtex` format.

Notice all files are placed with relative paths (ex: `../chapter1/introduction` from `main/dissertation.tex` for `chapter1/introduction`). So follow the folder structure or modify the paths to match your own.


### Add-On's to make your life easier AND to accomodate formatting requirements that nobody wants to read:
 - `\usepackage{subfiles}` to separate chapters into digestable files.
 - `\usepackage{indentfirst}` indents first paragraph after `\section` tags
 - `\usepackage[all]{nowidow}` to eliminate widow/orphan sentences.
 - `\usepackage[justification=centerlast]{caption}` to uniformly justify figure captions.
 - `begin{tabular*}{\textwidth}` to fit fat tables to text width with the `tabular*` environment instead of the simpler `tabular` environment.
 - For long figures or captions that span more than one page:
    - First delcare a new command to label the figure as ***Continued***: `\DeclareCaptionLabelFormat{adja-page}{\hrulefill\\#1 #2 \emph{(Continued)}}`
    - For the large figure, declare 2 figure environments, and use `\ContinuedFloat` and `\captionsetup{labelformat=adja-page}` for continuation. 
    - Make sure the figure caption is alone with no other text with `\clearpage` before and after inserting the caption.
    - The second figure environment's caption should be `\caption[]{}` to avoid an empty caption being added to the figures list.

These changes are already implemented in `main/dissertation.tex`, do not edit the preamble unless you know what you are doing, and you are certain your edits will still follow formatting guidelines.

For LaTeX newcomers that's never created documents in plain text before, google `overleaf how to x` for simple guidelines on how to do certain things if following my `.tex` files are not instructive.

If you have questions that you couldn't solve from googling around, create an issue in this GitHub repository and I will try to help if I have time. 
