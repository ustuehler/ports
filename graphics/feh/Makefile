# $OpenBSD: Makefile,v 1.83 2017/08/06 08:46:47 dcoppa Exp $

COMMENT=	lightweight image viewer

DISTNAME=	feh-2.19.1
EXTRACT_SUFX=	.tar.bz2
CATEGORIES=	graphics

HOMEPAGE=	http://feh.finalrewind.org/

MAINTAINER=	David Coppa <dcoppa@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	Imlib2 X11 Xinerama c curl exif m png

MASTER_SITES=	${HOMEPAGE}

LIB_DEPENDS=	graphics/imlib2 \
		graphics/libexif \
		net/curl

RUN_DEPENDS+=	devel/desktop-file-utils \
		x11/gtk+3,-guic

CFLAGS+=	-I${LOCALBASE}/include \
		-I${X11BASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib -L${X11BASE}/lib
MAKE_FLAGS=	LDFLAGS="${LDFLAGS}" man_dir="${DESTDIR}${PREFIX}/man" \
		example_dir="${DESTDIR}${PREFIX}/share/examples/feh"
FAKE_FLAGS=	PREFIX="${PREFIX}"

USE_GMAKE=	Yes

NO_TEST=	Yes

post-configure:
	${SUBST_CMD} ${WRKSRC}/examples/themes ${WRKSRC}/man/feh.pre \
		${WRKSRC}/src/events.c ${WRKSRC}/src/keyevents.c \
			${WRKSRC}/src/options.c

.include <bsd.port.mk>
