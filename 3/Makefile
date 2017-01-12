
R_OPTS=--vanilla

main.pdf: main.tex main.aux
	pdflatex $<

main.tex: main.Rnw
	R ${R_OPTS} -e "library(knitr);knit('$<')"

main.aux: main.tex
	pdflatex $<

view: main.pdf
	xdg-open main.pdf > /dev/null 2>&1 &

clean:
	rm -f main.pdf
	rm -f *.aux
	rm -f *.log
	rm -f *.toc
	rm -f *.out
	rm -f main.tex
