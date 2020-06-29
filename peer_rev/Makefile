PREF=2020-NaaktgeborenC+AndradeFN-LatNomSurv

clean:
	for EXT in log aux blg bbl out toc dvi; do \
		rm -vf ${PREF}.$$EXT; \
	done

cc/%.pdf: cc/%.svg
	inkscape \
		--export-type=pdf \
		--export-pdf-version=1.4 \
		--export-filename=$@ \
		$<

fig/%.pdf: fig/%.svg
	inkscape \
		--export-type=pdf \
		--export-pdf-version=1.4 \
		--export-filename=$@ \
		$<

%.ps: fig/%.pdf
	inkscape \
		--export-type=ps \
		--export-filename=$@ \
		$<

yearReport.tex: bibfile.bib
	yearReport | tee yearReport.tex

${PREF}.pdf: ${PREF}.tex 0*tex yearReport.tex \
		bibfile.bib
	pdflatex ${PREF}.tex
	bibtex   ${PREF}
	pdflatex ${PREF}.tex
	pdflatex ${PREF}.tex

