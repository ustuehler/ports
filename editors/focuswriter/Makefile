# $OpenBSD: Makefile,v 1.14 2017/07/26 22:45:19 sthen Exp $

COMMENT =	simple, distraction-free writing environment

DISTNAME =	focuswriter-1.5.5-src
PKGNAME =	${DISTNAME:S/-src//}
CATEGORIES =	editors
EXTRACT_SUFX =	.tar.bz2
WRKDIST =	${WRKDIR}/${DISTNAME:S/-src//}
REVISION =	1
HOMEPAGE =	http://gottcode.org/focuswriter/

MASTER_SITES =	${HOMEPAGE}

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

MODULES +=	devel/gettext \
		devel/qmake \
		x11/qt4
RUN_DEPENDS +=	devel/desktop-file-utils \
		x11/gtk+3,-guic
LIB_DEPENDS +=	textproc/hunspell
WANTLIB +=	ICE SM X11 Xext Xi Xinerama Xrender fontconfig freetype
WANTLIB +=	QtNetwork z QtGui c m pthread ${COMPILER_LIBCXX} hunspell-1.6

NO_TEST =	Yes

post-install:
	mv ${PREFIX}/share/man/man1/focuswriter.1 ${PREFIX}/man/man1
	rm -Rf ${PREFIX}/share/man/

.include <bsd.port.mk>
