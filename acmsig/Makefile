# Simple Makefile for ACM SIGCHI LaTeX template
# Public domain, 2015 by Florian Echtler
#
# To use, copy to top-level LaTeX folder and run 'make'.

VIEWER=$(shell which xdg-open open | head -n l)

# initial target files
all: proceedings.pdf

# initial aux file generation
%.aux: %.tex
	pdflatex $<

# bbl file generation (change bib name if required)
%.bbl: %.aux sample.bib
	bibtex $<

# pdf output
%.pdf: %.tex %.bbl
	pdflatex $<
	$(VIEWER) $@ &

# do not delete intermediate aux/bbl files
.PRECIOUS: %.aux %.bbl

clean:
	-rm *.aux *.log *.bbl *.blg *.out *.synctex.gz

veryclean: clean
	-rm *.pdf
