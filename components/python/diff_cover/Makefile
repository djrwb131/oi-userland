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
#   $WS_TOOLS/python-integrate-project diff_cover
#

BUILD_STYLE = pyproject

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		diff_cover
HUMAN_VERSION =			7.3.0
COMPONENT_SUMMARY =		diff_cover - Run coverage and linting reports on diffs
COMPONENT_PROJECT_URL =		https://github.com/Bachmann1234/diff-cover
COMPONENT_ARCHIVE_URL =		\
	https://files.pythonhosted.org/packages/42/d0/0b8207a228d70d608e8bfeb66f02740f9f6545cb8d44d347859e26243ba0/diff_cover-7.3.0.tar.gz
COMPONENT_ARCHIVE_HASH =	\
	sha256:a9b1f2bbd14962cd5279d7358a3ba8d726b9a6cc03dbf409f89cc2076a424234
COMPONENT_LICENSE =		Apache-2.0
COMPONENT_LICENSE_FILE =	LICENSE

TEST_STYLE = pytest

include $(WS_MAKE_RULES)/common.mk

# Testing fails with the checkdocs plugin installed
PYTEST_ADDOPTS += -p no:checkdocs

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += library/python/chardet
PYTHON_REQUIRED_PACKAGES += library/python/jinja2
PYTHON_REQUIRED_PACKAGES += library/python/pluggy
PYTHON_REQUIRED_PACKAGES += library/python/poetry-core
PYTHON_REQUIRED_PACKAGES += library/python/pygments
PYTHON_REQUIRED_PACKAGES += library/python/setuptools
PYTHON_REQUIRED_PACKAGES += runtime/python
