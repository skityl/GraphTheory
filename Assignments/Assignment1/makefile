COMP = pdflatex
READ = evince
STYLE = unsw
NAME = ass1
BIB = false


$(NAME).pdf: $(NAME).tex $(STYLE)maths.cls shortcuts.sty artwork/*
ifeq ($(BIB),true)
	$(COMP) $<
	bibtex $(NAME).aux
	$(COMP) $<
	$(COMP) $<
else
	$(COMP) $<
	$(COMP) $<
endif

read: $(NAME).pdf
	$(READ) $^

ques: assignment1.pdf
	$(READ) $<

notes: 
	$(READ) ../../Notes/math5425-summarynotes.pdf

clean:
	rm -f *.log *.aux *.lot *.lof *.toc *~ *.out *.blg *.bbl

spell: $(NAME).tex
	ispell $^

coffee:
	@echo "You're way too addicted."
