# nome do arquivo principal
MAIN = sbc-template

# comandos para compilar
LATEX = pdflatex
BIBTEX = bibtex

# para continuar compilando mesmo com erros
LATEX_FLAGS = -interaction=nonstopmode -halt-on-error

# arquivos gerados temporários
TEMP_FILES = *.aux *.log *.bbl *.blg *.toc *.out *.synctex.gz *.snm *.nav auto *-blx.bib *.run.xml


all: 
	$(LATEX) $(MAIN).tex
	$(LATEX) $(LATEX_FLAGS) $(MAIN)
	$(BIBTEX) $(MAIN)  
	$(LATEX) $(LATEX_FLAGS) $(MAIN)
	$(LATEX) $(LATEX_FLAGS) $(MAIN)

# limpa arquivos temporários
clean:
	rm -rf $(TEMP_FILES)

# limpa o pdf também
cleanall: clean
	rm -f $(MAIN).pdf

# visualização do PDF com o evince
view: all
	@echo "Abrindo $(MAIN).pdf com o Evince..."
	evince $(MAIN).pdf &
