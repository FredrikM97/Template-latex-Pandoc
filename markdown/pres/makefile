pres:
	# Not sure if the sed will work but try
	sed 's/\///g' pres.md | pandoc -t beamer -o pres.pdf

pres_debug:
	sed 's/\///g' ../pres.md | pandoc --verbose -t beamer -o ../pres.pdf