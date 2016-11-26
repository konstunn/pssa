
.PHONY: main.pdf

all: main.pdf

R_OPTS=--vanilla

main.pdf: main.Rnw
	R ${R_OPTS} -e "library(knitr);knit('$<')"
	pdflatex $(basename $@).tex

view: main.pdf
	xdg-open main.pdf || explorer main.pdf

clean:
	rm -f *.pdf
	rm -f *.aux
	rm -f *.log
	rm -f *.toc
	rm -f *.out
