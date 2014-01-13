# PANDOC = pandoc -s --mathml 
# PANDOC = pandoc -s --webtex 
PANDOC = pandoc -s 
MD0 = $(patsubst %.md0,%.md,$(wildcard *.md0))
# MD0 = $(wildcard *.md0)
HTML = $(patsubst %.md,%.html,$(wildcard *.md)) $(patsubst %.md0,%.html,$(wildcard *.md0))
SLIDE = $(patsubst %.mds,%.htm,$(wildcard *.mds))
MD   = head.md preface.md license.md basic.md prob.md randvar.md distribution.md exp.md joint.md descriptive.md CentralLimit.md test1.md test2.md anova.md regression.md PCA.md appendix.md dBinomial.md dNbinomial.md dGeometric.md dHypergeometric.md dPoisson.md dUniform.md dNormal.md

# dGamma.md dExp.md dChisquare.md dWeibull.md dF.md dBeta.md dT.md 

# descriptive.md inference.md CentralLimitTheorem.md estimation.md estimation1.md regression.md anova.md expdesign.md  learning.md bayesnet.md markov.md emalgorithm.md dBinomial.md dNbinomial.md dGeometric.md dHypergeometric.md dPoisson.md dUniform.md dNormal.md dGamma.md dExp.md dChisquare.md dWeibull.md dF.md dBeta.md dT.md 
PARG = -c ../css/book.css -B header.htm -A footer.htm --toc --base-header-level=1 --toc-depth=2 
PARG_HTM = -c ../css/book.css -B header.htm -A footer.htm --toc --base-header-level=1 --toc-depth=2 
PEPUB = --toc --base-header-level=1 --toc-depth=2 --epub-metadata=metadata.xml --epub-stylesheet=../css/book.css 
EARG = --margin-top=16 --margin-bottom=16 --margin-left=20 --margin-right=20 \
--pretty-print --base-font-size=9 --font-size-mapping="7, 8, 9, 12, 14, 16, 20, 24" 
RM = rm -f

.PHONY: all

all: $(HTML) shtm epubipad epubA4 pdfipad pdfA4 

slide : $(SLIDE)

%.htm: %.mds
	$(PANDOC) -s --webtex -i -t dzslides --template=ccc.dtslides $< -o ../htm/$@

epubA4: $(MD0)
	$(PANDOC) $(PEPUB) --epub-cover-image=../img/coverA4.jpg $(MD) -o ../book/A4.epub

pdfA4: epubA4
	ebook-convert ../book/A4.epub ../book/A4.pdf $(EARG) --paper-size=a4

epubipad: $(MD0)
	$(PANDOC) $(PEPUB) --epub-cover-image=../img/cover.jpg $(MD) -o ../book/ipad.epub

pdfipad: epubipad
	ebook-convert ../book/ipad.epub ../book/ipad.pdf $(EARG) --output-profile=ipad3
	
html: $(MD0) $(HTML)

shtm: 
	$(PANDOC) $(MD) -o ../book/book.html $(PARG)

md0: $(MD0)
    
%.md0 : 
	node md0.js $*.md0 $*.md
    
%.md: %.md0
	node md0.js $< $@

%.html: %.md
	$(PANDOC) $< reflink.md9 -o ../htm/$@ $(PARG_HTM)
	
clean: 
	${RM} ../htm/*.*
	${RM} ../book/*.*
	${RM} ../timg/*.*
	${RM} $(MD0)

    
# $?：代表已被更新的 dependencies 的值。也就是 dependencies 中，比 targets 還新的值。
# $@：代表 targets 的值。
# $<：代表第一個 dependencies 的值。
# $* : 代表 targets 所指定的檔案，但不包含副檔名。
