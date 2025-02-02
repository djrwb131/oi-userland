#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# This file was automatically generated using the following command:
#   $WS_TOOLS/python-integrate-project psycopg2
#

BUILD_STYLE = setup.py

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		psycopg2
HUMAN_VERSION =			2.9.5
COMPONENT_SUMMARY =		psycopg2 - psycopg2 - Python-PostgreSQL Database Adapter
COMPONENT_PROJECT_URL =		https://psycopg.org/
COMPONENT_ARCHIVE_URL =		\
	https://files.pythonhosted.org/packages/89/d6/cd8c46417e0f7a16b4b0fc321f4ab676a59250d08fce5b64921897fb07cc/psycopg2-2.9.5.tar.gz
COMPONENT_ARCHIVE_HASH =	\
	sha256:a5246d2e683a972e2187a8714b5c2cf8156c064629f9a9b1a873c1730d9e245a
COMPONENT_LICENSE =		LGPL-3.0-only

# see doc/src/install.rst
TEST_STYLE = custom

include $(WS_MAKE_RULES)/common.mk

# Both build and install needs PATH environment variable and build should
# not depend on host default pg_config
COMPONENT_BUILD_ENV += PATH=$(PG_BINDIR):$(PATH)
COMPONENT_INSTALL_ENV += PATH=$(PATH)

# force needed rpath
LD_OPTIONS += -R$(PG_LIBDIR)

#
# Note:
#
# To test we need to fulfill following prerequisites:
#	1) the default system postgres version must match the version we built
#	   psycopg2 for,
#	2) the postgresql service must be running,
#	3) the psycopg2_test database with plpgsql extension must exist.
#
# To check 1) and 2) you can run following commands:
#	gmake print-value-PG_VERSION
#	pkg mediator postgres
#	svcs '*postgresql*'
# To create the psycopg2_test database you could run:
#	su - postgres
#	createdb psycopg2_test
#	psql -c 'CREATE EXTENSION plpgsql;' psycopg2_test
#
# Testing will use the default 'postgres' user.
#
COMPONENT_TEST_ENV += PSYCOPG2_TESTDB_USER=postgres

# Custom test style - see doc/src/install.rst
COMPONENT_TEST_CMD =		$(PYTHON) -c "import tests; tests.unittest.main(defaultTest='tests.test_suite')"
COMPONENT_TEST_ARGS =		--verbose
COMPONENT_TEST_TARGETS =

# Manually added build and testing dependencies
REQUIRED_PACKAGES += $(PG_DEVELOPER_PKG)
TEST_REQUIRED_PACKAGES += service/$(PG_BASEPKG)

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += runtime/python
REQUIRED_PACKAGES += $(PG_LIBRARY_PKG)
REQUIRED_PACKAGES += system/library
