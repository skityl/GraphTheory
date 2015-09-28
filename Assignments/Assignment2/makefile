# The makefile for graph theory assignment 2
# ----------------------
# Some variables need to be filled in:
# NAME = file name: for name.pdf and name.tex 
# STYLE = skityl or unsw. 
# BIB = true if including a bibliography, false otherwise.
# REMARK = coffee?
#
# Don't forget that the tex file also needs to be edited!
# Version last edited 2015-09-03.

# Variables:
BIB =  false

NAME = ass2
COMP = pdflatex
READ = evince
STYLE =   unsw
REMARK = "No! It'll make you sick."


# Code begins. No need to touch anything below here.

ifeq ($(BIB),true)
    BIB_FILE = Bibliography.bib
else
    BIB_FILE = # Leave blank.
endif


$(NAME).pdf: $(NAME).tex $(STYLE)maths.cls shortcuts.sty artwork/* $(BIB_FILE)
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

ques: assignment2.pdf
	$(READ) $<

notes: 
	$(READ) ../../Notes/math5425*

clean:
	rm -f *.log *.aux *.lot *.lof *.toc *~ *.out *.blg *.bbl

spell: $(NAME).tex
	ispell $^

coffee:
	@echo $(REMARK)
