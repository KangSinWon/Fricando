AUTOMAKE_OPTIONS = gnu
ACLOCAL_AMFLAGS = -I m4

EXTRA_DIST = AUTHORS \
             COPYING \
             NEWS \
             autogen.sh  

MAINTAINERCLEANFILES=\
	$(srcdir)/configure \
	$(srcdir)/Makefile.in \
	$(srcdir)/aclocal.m4 \
	$(srcdir)/compile \
	$(srcdir)/depcomp \
	$(srcdir)/install-sh \
	$(srcdir)/ltmain.sh \
	$(srcdir)/missing \
	$(srcdir)/config.guess \
	$(srcdir)/config.sub \
	$(srcdir)/config.h.in \
	$(srcdir)/config.h.in~ \
	$(srcdir)/INSTALL \
	$(srcdir)/m4/ltsugar.m4 \
	$(srcdir)/m4/libtool.m4 \
	$(srcdir)/m4/ltversion.m4 \
	$(srcdir)/m4/lt~obsolete.m4 \
	$(srcdir)/m4/ltoptions.m4

SUBDIRS = include \
          libio \
          libext4 \
          libfat \
          src

doc_DATA = README

dist-hook:
	$(MKDIR_P) "$(distdir)/m4"

libtool: $(LIBTOOL_DEPS)
	$(SHELL) ./config.status --recheck

libs: libio libext4 libfat

libio:
	(cd libio && $(MAKE) libs) || exit 1;

libext4:
	(cd libext4 && $(MAKE) libs) || exit 1;

libfat:
	(cd libfat && $(MAKE) libs) || exit 1;
