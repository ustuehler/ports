# $OpenBSD: Makefile,v 1.4 2017/05/13 19:54:27 jung Exp $

COMMENT =		set the color temperature of the screen

DISTNAME =		sct-0.4

CATEGORIES =		x11 sysutils

HOMEPAGE =		https://www.umaxx.net/

MAINTAINER =		Joerg Jung <jung@openbsd.org>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c X11 Xrandr

MASTER_SITES =		${HOMEPAGE}/dl/

MAKE_FLAGS =		CC="${CC}"
MAKE_ENV =		LDFLAGS="${LDFLAGS}"
FAKE_FLAGS =		DESTDIR=""

NO_TEST =		Yes

.include <bsd.port.mk>
