# $OpenBSD: Makefile.template,v 1.79 2020/04/01 19:09:24 reivyr Exp $

# TODO:
# - double-check license
# - does brynet want MAINTAINER?
# - depends on games/allegro (likely LDEP) and audio/dumb
# - revamp DESCR
# - can CFLAGS/CXXFLAGS etc. be passed?

COMMENT =	IDE and engine for creating and running adventure games

V =		3.5.0.24
DISTNAME =	v.${V}
PKGNAME =	ags-${V}

CATEGORIES =	games

HOMEPAGE =	http://www.adventuregamestudio.co.uk

MAINTAINER =	Thomas Frohwein <thfr@openbsd.org>

# Artistic License 2.0
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} X11 alleg c freetype m ogg theora
WANTLIB += vorbis vorbisfile

MASTER_SITES =	https://github.com/adventuregamestudio/ags/archive/

EXTRACT_SUFX =		.tar.gz

#COMPILER =		???
#MODULES =		???
BUILD_DEPENDS =	audio/dumb
#RUN_DEPENDS =		???
LIB_DEPENDS =	audio/libogg \
		audio/libvorbis \
		games/allegro \
		multimedia/libtheora
#TEST_DEPENDS =		???

MAKE_FLAGS =	V=1 CC="${CC}" CXX="${CXX}"
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
USE_GMAKE =		Yes

NO_TEST =	Yes

CFLAGS +=	-I${LOCALBASE}/include \
		-I${WRKSRC}/Common \
		-I${WRKSRC}/Common/libinclude \
		-I${WRKSRC}/Engine \
		-I${X11BASE}/include/freetype2
CXXFLAGS +=	-I${LOCALBASE}/include \
		-I${WRKSRC}/Common \
		-I${WRKSRC}/Common/libinclude \
		-I${WRKSRC}/Engine \
		-I${X11BASE}/include/freetype2
#LDFLAGS =		???
#MAKE_FILE =		???
#PKG_ARCH =		??? (* for arch-independent packages)
#WRKDIST =		??? if other than ${WRKDIR}/${DISTNAME}
WRKDIST =		${WRKDIR}/ags-${DISTNAME}
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

MAKEFILE =	Engine

#ALL_TARGET =	""
#INSTALL_TARGET =	???
#TEST_TARGET =		???

do-build:
	cd ${WRKSRC}/Engine && env -i ${MAKE_ENV} ${MAKE_PROGRAM} \
		${MAKE_FLAGS} -f ${MAKE_FILE}

do-install:
	cp ${WRKBUILD}/Engine/ags ${PREFIX}/bin/

.include <bsd.port.mk>
