# Directory for source md files
	source := main

	# Directory for pdf output
	output := report

	config :=
	
	Figures :=
doc:
	$(output)/%.pdf: $(source)/%.md
	pandoc \
		--V mainfont="DejaVu Sans" \
		--V fontsize=11pt \
		--V geometry:"top=1.5cm, bottom=2.5cm, left=1.5cm, right=1.5cm" \
		--V geometry:a4paper \
		--V date=`date '+%F'` \
		--toc \
		--number-sections \
		--filter pandoc-citeproc --bibliography=refs.bib --csl Config/elsevier-vancouver.csl \
		-o $@

clean:
	rm -f $(output)/*.pdf
	

graveyard:
	sed 's/\///g' doc.md | pandoc \
	-V date=`date '+%F'` \
	--toc \
	--filter pandoc-citeproc --bibliography=refs.bib --csl Config/elsevier-vancouver.csl \
	-o doc.pdf
