#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright (c) 2011, 2017, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2022 Niklas Poslovski
#
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		tcpdump
COMPONENT_VERSION=	4.99.3
COMPONENT_SUMMARY=	A tool for network monitoring and data acquisition
COMPONENT_PROJECT_URL=	https://www.tcpdump.org/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= sha256:ad75a6ed3dc0d9732945b2e5483cb41dc8b4b528a169315e499c6861952e73b3
COMPONENT_ARCHIVE_URL=	$(COMPONENT_PROJECT_URL)release/$(COMPONENT_ARCHIVE)
COMPONENT_SIG_URL=	$(COMPONENT_ARCHIVE_URL).sig
COMPONENT_FMRI=	diagnostic/tcpdump
COMPONENT_CLASSIFICATION=	Applications/Internet
COMPONENT_LICENSE=	BSD
COMPONENT_LICENSE_FILE=	LICENSE

# Prevent macro redefinition error 
CFLAGS += -D _NETINET_IP_H

include $(WS_MAKE_RULES)/common.mk

# fix my alignment issues instead of falling over on sparc
studio_ALIGN.sparc.64=-xmemalign=16i
CONFIGURE_OPTIONS.sparc += ac_cv___attribute__=no
CONFIGURE_OPTIONS += $(CONFIGURE_OPTIONS.$(MACH))

# lazyloading (indirectly enabled by -Bdirect) seems to cause problems with
# libpcap device enumeration.
LD_B_DIRECT=

CONFIGURE_OPTIONS += --enable-ipv6=yes
CONFIGURE_OPTIONS += --with-user=nobody
CONFIGURE_OPTIONS += --without-crypto

# Fixes tests
COMPONENT_TEST_ENV += PATH=$(PATH.gnu)

ASLR_MODE = $(ASLR_ENABLE)

COMPONENT_PRE_TEST_ACTION = \
        ($(CP) -r $(SOURCE_DIR)/tests $(@D)/.)

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/libpcap
