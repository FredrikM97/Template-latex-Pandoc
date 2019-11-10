# Makefile for markdown presentation
# Following is needed:
	# pandoc
	# pandoc-crossref
	# pandoc-citeproc
# Directory for source md files
source := report
# Directory for pdf output
output := pres
# Directory for config files
config := config
# Directory for figures
images := image

pres:
	# Not sure if the sed will work but try
	sed 's/\///g' $(source).md | pandoc \
	-t beamer \
	-V classoption="aspectratio=169" \
	-V colortheme=crane \
	-V theme=CambridgeUS \
	-V fonttheme=serif \
	-V date=`date '+%F'` \
	--filter pandoc-citeproc --bibliography=refs.bib --csl $(config)/elsevier-vancouver.csl \
	--extract-media=$(images) \
	-o $(output).pdf

pres_debug:
	sed 's/\///g' $(source).md | pandoc \
	--verbose \
	-t beamer \
	-V classoption="aspectratio=169" \
	-V colortheme=crane \
	-V theme=CambridgeUS \
	-V fonttheme=serif \
	-V date=`date '+%F'` \
	--filter pandoc-citeproc --bibliography=refs.bib --csl $(config)/elsevier-vancouver.csl \
	--extract-media=$(images) \
	-o $(output).pdf

# Remove all pdf files
clean:
	rm -f $(output)*.pdf

# --include-in-header $(config)/titlesec.tex \