SUBDIRS = src testsuite
EXTRA_DIST = check.lrzsz COMPATABILITY README.cvs \
	fastcheck.sh README.tests
PR=@PACKAGE@-@VERSION@
CLEAN_FILES=fastcheck.done

dist-hook:

oldcheck-local:
	QUIET=-q $(srcdir)/check.lrzsz $(srcdir) `pwd`	

fastcheck: 
	$(srcdir)/fastcheck.sh $(srcdir) `pwd`

vcheck:
	$(srcdir)/check.lrzsz $(srcdir) `pwd`
# vcheck-%:
# 	$(srcdir)/check.lrzsz $(srcdir) `pwd`	$(subst vcheck-,,$@)
# check-%:
# 	QUIET=-q $(srcdir)/check.lrzsz $(srcdir) `pwd`	$(subst check-,,$@)
vcheck-x:
	$(srcdir)/check.lrzsz $(srcdir) `pwd`	x
vcheck-y:
	$(srcdir)/check.lrzsz $(srcdir) `pwd`	y
vcheck-z:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` z
vcheck-z8:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` z8
vcheck-sz-r:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` sz-r
vcheck-rz-r:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` rz-r
vcheck-turbo:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` turbo
vcheck-error:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` error
vcheck-manag vcheck-manage:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` manage
vcheck-zm-rz:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` zm-rz
vcheck-zm-sz:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` zm-sz
vcheck-orig-rz:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` orig-rz
vcheck-orig-sz:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` orig-sz
vcheck-orig-kombi:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` orig-kombi
vcheck-abuse:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` abuse
vcheck-startup:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` startup
vcheck-tmp:
	$(srcdir)/check.lrzsz $(srcdir) `pwd` tmp

# Tag before making distribution.  Also, don't make a distribution if
# checks fail.  Also, make sure the NEWS file is up-to-date.
cvs-dist: 
	@if sed 1q NEWS | grep -e "$(VERSION)" > /dev/null; then :; else \
		echo "NEWS not updated; not releasing" 1>&2; \
		exit 1;                               \
	fi
	cvs tag `echo "Release-$(VERSION)" | sed 's/\./-/g'`
	$(MAKE) dist


ACLOCAL_AMFLAGS = -I m4
