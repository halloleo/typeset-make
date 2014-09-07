# Makefiles for typesetting Markdown, LaTeX et al

Typesetting with plain text files needs multi-pass workflows. Makefiles can
greatly simplify this.

At this stage, I have only a makefile for  LaTeX sources.

# LaTeX makefile

This makefile creates from your LaTeX source the output PDF. It does the necessary re-runs for TOCs and bibliographies and cleans the intermediate files up, **except the log file from the last TeX run**. (The log file is kept in order to give the end user the chance to check on layout issues the TeX system had detected.)

## How to use

Say your main LaTeX file is called `wunderbar.tex`.

Then have `makelatex.incl` in your directory with the  LaTeX source(s) and write a `Makefile` with the content:

    INPUT=wunderbar.tex
    include makelatex.incl

Now execute

    $ make

You should end up with the files `wunderbar.pdf` and `wunderbar.log`.

## How it works and Requirements

`makelatex.incl` uses [latexmk][latexmk] to deal with the dependencies. On a full TeXlive/MikTeX installation it should run without other requirements.

[latexmk]: http://www.ctan.org/pkg/latexmk/




