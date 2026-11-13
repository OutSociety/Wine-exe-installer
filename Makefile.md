PREFIX ?= /usr/local
BINDIR  = $(PREFIX)/bin

.PHONY: all install uninstall test lint help

all: help

install:
	install -d $(DESTDIR)$(BINDIR)
	install -m 755 install.sh $(DESTDIR)$(BINDIR)/wine-exe-installer

uninstall:
	rm -f $(DESTDIR)$(BINDIR)/wine-exe-installer

test:
	bash -n install.sh && echo "Sintaxis OK."
	command -v shellcheck >/dev/null && shellcheck install.sh || echo "shellcheck no instalado."

lint: test

help:
	@echo "Targets: install, uninstall, test, lint"