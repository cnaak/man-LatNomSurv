PREF=2020-NaaktgeborenC+AndradeFN-LatNomSurv

clean:
	for EXT in log aux blg bbl out toc dvi; do \
		rm -vf ${PREF}.$$EXT; \
	done

${PREF}.pdf: ${PREF}.tex 0*tex yearReport.tex \
		bibfile.bib
	pdflatex ${PREF}.tex
	bibtex   ${PREF}
	pdflatex ${PREF}.tex
	pdflatex ${PREF}.tex

