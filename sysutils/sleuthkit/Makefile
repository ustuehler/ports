# $OpenBSD: Makefile,v 1.21 2017/07/26 22:45:30 sthen Exp $

COMMENT=		forensic toolkit based on TCT

DISTNAME=		sleuthkit-4.3.0
CATEGORIES=		sysutils security
REVISION=		0

SHARED_LIBS +=		tsk	0.0 # 14.0

HOMEPAGE=		http://www.sleuthkit.org/

MAINTAINER=		Nigel Taylor <nigel@openbsd.org>

# CPLv1 & IBM & GPLv2
PERMIT_PACKAGE_CDROM=	commercial contributor must indemnify all others
PERMIT_PACKAGE_FTP=	Yes

MASTER_SITES =		https://github.com/sleuthkit/sleuthkit/releases/download/${DISTNAME}/

WANTLIB += 		c m pthread ${COMPILER_LIBCXX} z

CONFIGURE_STYLE =	simple

CONFIGURE_ARGS += 	--mandir='${PREFIX}/man' \
			--disable-java \
			--without-afflib \
			--without-libewf

BUILD_DEPENDS=		devel/cppunit
RUN_DEPENDS=		converters/p5-DateManip

NO_TEST =		Yes

pre-configure:
	@sed -i 's:%%PREFIX%%:${PREFIX}:' ${WRKSRC}/man/sorter.1

.include <bsd.port.mk>
