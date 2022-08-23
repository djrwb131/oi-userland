#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"). You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2014 Josef 'Jeff' Sipek <jeffpc@josefsipek.net>
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		nibbles
COMPONENT_VERSION=	0.13
COMPONENT_PROJECT_URL=	http://method-combination.net/lisp/nibbles/
COMPONENT_FMRI=		library/common-lisp/nibbles
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
	sha256:45116a0102240c010eee55aced35580ed8466cc522f6a80afaceea32027036f1
#COMPONENT_ARCHIVE_URL=	http://www.method-combination.net/lisp/files/$(COMPONENT_ARCHIVE)
COMPONENT_ARCHIVE_URL=	https://github.com/froydnj/$(COMPONENT_NAME)/archive/refs/tags/v$(COMPONENT_VERSION).tar.gz
COMPONENT_LICENSE=	MIT-like
COMPONENT_LICENSE_FILE=	$(COMPONENT_NAME).license
COMPONENT_SUMMARY=	nibbles is a library for accessing multibyte integers from octet arrays and streams

include ../../../make-rules/prep.mk
include ../../../make-rules/common-lisp.mk
include ../../../make-rules/ips.mk

build:		$(BUILD_32)

install:	$(INSTALL_32)
