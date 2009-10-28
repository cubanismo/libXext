SUBDIRS = man src

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = xext.pc

EXTRA_DIST=xext.pc.in 

.PHONY: ChangeLog INSTALL

INSTALL:
	$(INSTALL_CMD)

ChangeLog:
	$(CHANGELOG_CMD)

dist-hook: ChangeLog INSTALL

if LINT
# Check source code with tools like lint & sparse
lint:
	(cd src && $(MAKE) $(MFLAGS) lint)
endif LINT
