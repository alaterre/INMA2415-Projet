
# the viewer to show the latex

#PDFVIEWER=evince 	# GNOME
#PDFVIEWER=okular 	# KDE
#PDFVIEWER=xpdf 	# lightweight
#PDFVIEWER=xdg-open 	# Default pdf viewer - GNU/Linux
PDFVIEWER=open 		# Default pdf viewer - Mac OS


MAIN_NAME=rapport
PDF_NAME=$(MAIN_NAME).pdf

.PHONY=$(MAIN_NAME)

all: $(PDF_NAME)

$(PDF_NAME): $(MAIN_NAME).tex
	latexmk -pdf -pdflatex="pdflatex -shell-escape -enable-write18" \
	  -use-make $(MAIN_NAME).tex

clean:
	latexmk -CA

show: $(PDF_NAME)
	$(PDFVIEWER) $(PDF_NAME) 2> /dev/null &

release: all
	smartcp -v config.yml
#clean:
#	@rm -fv $(MAIN_NAME).{dvi,ps,fls,toc,fdb_latexmk,aux,log,bbl,blg}
