# Makefile for Sphinx documentation
#
# Copyright 2022 Stéphane Caron

# You can also set these variables from the command line.
DOXYGEN      = doxygen
HTMLDIR      = html
REMOTEDIR    = tasts-robots.org:public_html/doc/upkie

.PHONY: clean html open upload

html:
	(cd .. && $(DOXYGEN) Doxyfile)

clean:
	rm -rf $(HTMLDIR)
	rm -f $(wildcard images/*.eps) $(wildcard images/*.png)

open:
	firefox $(HTMLDIR)/index.html

images/%.eps : figures/%.svg
	inkscape --without-gui --file=$< --export-eps=$@

images/%.png : figures/%.svg
	inkscape --without-gui --export-area-page --file=$< --export-png=$@

figures: images/floor-contact.eps images/floor-contact.png images/observers.eps images/observers.png images/wheel-odometry.eps images/wheel-odometry.png

upload: clean figures html
	rsync -auz --delete-after --progress $(HTMLDIR)/ $(REMOTEDIR)/
