# contrib/bloom/Makefile

MODULE_big = bloom
OBJS = blcost.o blinsert.o blscan.o blutils.o blvacuum.o blvalidate.o $(WIN32RES)

EXTENSION = bloom
DATA = bloom--1.0.sql
PGFILEDESC = "bloom access method - signature file based index"

REGRESS = bloom

ifdef USE_PGXS
PG_CONFIG = pg_config
PGXS := $(shell $(PG_CONFIG) --pgxs)
include $(PGXS)
else
subdir = contrib/bloom
top_builddir = ../..
include $(top_builddir)/src/Makefile.global
include $(top_srcdir)/contrib/contrib-global.mk
endif

wal-check: temp-install
	$(prove_check)
wal-checkdma: temp-install
	$(prove_checkdma)
