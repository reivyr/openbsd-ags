# $OpenBSD: Makefile.template,v 1.79 2020/04/04 19:31:38 reivyr Exp $

# TODO:
# - double-check license
# - does brynet want MAINTAINER?
# - depends on games/allegro (likely LDEP) and audio/dumb
# - revamp DESCR
# - can CFLAGS/CXXFLAGS etc. be passed?

COMMENT =	IDE and engine for creating and running adventure games

V =		2020.03.22
DISTNAME =	ags-${V}

GH_ACCOUNT =	adventuregamestudio
GH_PROJECT =	ags
GH_COMMIT =	3ba1b2a91aee2ebf9a5a0cb67d93ab93e8042ee0
CATEGORIES =	games

HOMEPAGE =	http://www.adventuregamestudio.co.uk

MAINTAINER =	Thomas Frohwein <thfr@openbsd.org>

# Artistic License 2.0
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} X11 alleg c freetype m ogg theora
WANTLIB += vorbis vorbisfile

BUILD_DEPENDS =	audio/dumb
LIB_DEPENDS =	audio/libogg \
		audio/libvorbis \
		games/allegro \
		multimedia/libtheora

MAKE_FLAGS =	V=1 CC="${CC}" CXX="${CXX}"

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

MAKEFILE =	Engine

do-build:
	cd ${WRKSRC}/Engine && env -i ${MAKE_ENV} ${MAKE_PROGRAM} \
		${MAKE_FLAGS} -f ${MAKE_FILE}

do-install:
	cp ${WRKBUILD}/Engine/ags ${PREFIX}/bin/

.include <bsd.port.mk>
