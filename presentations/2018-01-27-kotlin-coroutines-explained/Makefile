# Modified from https://gist.github.com/bertvv/e77e3a5d24d8c2a9bcc4

# Directory containing source (Markdown) files
source := .

# Directory containing pdf files
output := .

# All markdown files in src/ are considered sources
sources := $(wildcard $(source)/*.md)

# Convert the list of source files (Markdown files in directory src/)
# into a list of output files (PDFs in directory print/).
objects := $(patsubst %.md,%.pdf,$(subst $(source),$(output),$(sources)))

all: $(objects)

# Recipe for converting a Markdown file into PDF using Pandoc
$(output)/%.pdf: $(source)/%.md
	pandoc \
		-t beamer \
		--slide-level=3 \
		--pdf-engine=xelatex \
		--variable monofont="Operator Mono" \
		$< -o $@

.PHONY : clean

clean:
	rm -f $(output)/*.pdf