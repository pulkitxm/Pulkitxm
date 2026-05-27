# Build the resume PDF from resume.tex
LATEX   := pdflatex
FLAGS   := -interaction=nonstopmode -halt-on-error
SRC     := resume.tex
PDF     := resume.pdf

# Auxiliary files pdflatex leaves behind (matches .gitignore)
AUX     := $(SRC:.tex=.aux) $(SRC:.tex=.log) $(SRC:.tex=.out) \
           $(SRC:.tex=.fls) $(SRC:.tex=.fdb_latexmk) $(SRC:.tex=.synctex.gz)

.PHONY: all clean

all: $(PDF)

# Run twice so references/layout settle, then drop the aux files
$(PDF): $(SRC)
	$(LATEX) $(FLAGS) $(SRC)
	$(LATEX) $(FLAGS) $(SRC)
	$(RM) $(AUX)

clean:
	$(RM) $(PDF) $(AUX)
