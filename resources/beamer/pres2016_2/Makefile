#!/usr/bin/make

NAME=ejemplo

ejemplo.pdf: $(NAME).tex
	pdflatex $<
	pdflatex $<
	@rm -fr *.log *.tdo *.out *.aux .*.ini *.snm *.toc *.nav

clean:
	@rm -fr *.log *.tdo *.out *.aux .*.ini *.snm *.toc *.nav $(NAME).pdf

