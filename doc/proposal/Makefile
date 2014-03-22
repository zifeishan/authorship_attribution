NAME=PAA

all: markdown pdf 

markdown: intro related model dataset conc

intro: src/intro.md
	pandoc src/intro.md -o build/intro.tex

related: src/related.md 
	pandoc src/related.md -o build/related.tex

model: src/model.md
	pandoc src/model.md -o build/model.tex

dataset: src/dataset.md 
	pandoc src/dataset.md -o build/dataset.tex

conc: src/conc.md
	pandoc src/conc.md -o build/conc.tex

pdf: template/templateacm.tex
	cp template/sig-alternate.cls ./
	pdflatex template/templateacm.tex
	bibtex templateacm
	pdflatex template/templateacm.tex
	pdflatex template/templateacm.tex
	rm -f *.log *.aux *.out *.bbl *.blg
	rm -f sig-alternate.cls
	mv templateacm.pdf proposal.pdf
	echo 'Compiled document: proposal.pdf'

clean:
	rm -rf build/*
	rm -f *.log *.aux *.out *.bbl *.blg
	rm -f *.log *.aux *.out *.bbl *.blg
	rm -f sig-alternate.cls
	