#!/usr/bin/make
# by RAM

%.pdf: %.fodg
	unoconv -f pdf $<

%-crop.pdf: %.pdf
	perl ../../resources/scripts/pdfcrop.pl $<

###################################################################################################

all: articulo.pdf

###################################################################################################

ifneq ($(wildcard articulo.tex),)

DEPENDENCIES = \
../../resources/IEEEtranBST2/IEEEabrv.bib ../../resources/IEEEtranBST2/IEEEtran.bst \
../../resources/IEEEtran/IEEEtran.cls ../shared.bib ../shared.tex $(wildcard *.bib)

articulo: articulo.pdf

articulo.pdf: articulo.tex $(DEPENDENCIES) images-crop.pdf
	pdflatex $<
	bibtex -terse articulo.aux
	pdflatex $<
	pdflatex $<

embed_fonts: articulo.pdf
	pdf2ps $< articulo.ps
	ps2pdf14 -dPDFSETTINGS=/prepress -dEmbedAllFonts=true articulo.ps $<
    
aspell: articulo.tex
	aspell -t -l $(LANG) -c $<

endif


###################################################################################################

clean:
	@rm -fr *.aux *.log *.ps *.bbl *.blg *.pdf
