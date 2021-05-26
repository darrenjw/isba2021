# Makefile

FORCE:
	make talk.pdf

talk.pdf: talk.md
	pandoc -t beamer -Vtheme:metropolis talk.md -o talk.pdf

view: talk.pdf
	xdg-open talk.pdf &




# eof

