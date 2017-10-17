#!/usr/bin/make

NAME=ejemplo

ejemplo.pdf: $(NAME).tex
	pdflatex $<

clean:
	@rm -fr *.log *.tdo *.out *.aux .*.ini *.snm *.toc *.nav $(NAME).pdf

