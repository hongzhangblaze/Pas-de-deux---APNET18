TARGET=paper
all: paper.tex
	rm -f *.aux paper.bbl paper.blg *.log paper.dvi paper.ps paper.out paper.thm
	-pdflatex paper.tex
	-bibtex paper
	-pdflatex paper.tex
	-pdflatex paper.tex
	open paper.pdf

pdf:
	GS_OPTIONS=-dPDFSETTINGS=/prepress rubber -e "bibtex.crossrefs 100" --pdf -Wrefs -Wmisc $(TARGET) 

clean:
	rm -f *.aux *.log *.out *.bbl *.blg *~ *.bak $(TARGET).ps $(TARGET).pdf $(TARGET).dvi

ps: pdf
	GS_OPTIONS=-dPDFSETTINGS=/prepress pdftops -level1 $(TARGET).pdf
