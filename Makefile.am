COUCHBASE_PYTHON_LIB = ../couchbase-python-client/couchbase

default:

pythonlibdir=$(libdir)/python

pythonlib_SCRIPTS= workload-generator

PYTHON_TOOLS= wrapper/workload-generator

${PYTHON_TOOLS}: wrapper/wrapper
	cp $< $@

CLEANFILES = ${PYTHON_TOOLS}
bin_SCRIPTS = ${PYTHON_TOOLS}

EXTRA_DIST = $(pythonlib_SCRIPTS)

install-data-hook:
	if test ! "$(mkdir_p)" = ""; then \
	    $(mkdir_p) "$(DESTDIR)$(localstatedatdir)"; \
	else \
	    echo "WARNING: You may have to create these directories by hand."; \
	    mkdir -p "$(DESTDIR)$(localstatedatdir)"; \
	fi
	cp -rf $(COUCHBASE_PYTHON_LIB) $(pythonlibdir)


