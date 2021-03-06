# Created by: Gvozdikov Veniamin <g.veniamin@googlemail.com>
# $FreeBSD$

PORTNAME=	clucene2
PORTVERSION=	2.3.3.4
CATEGORIES=	textproc devel
MASTER_SITES=	SF/clucene/clucene-core-unstable/2.3
DISTNAME=	clucene-core-${PORTVERSION}

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	CLucene is a C++ port of Lucene

USE_CMAKE=	yes
USE_GNOME=	gnomehack
USE_LDCONFIG=	yes

CONFLICTS=	clucene-0.*

CMAKE_ARGS+=	-DENABLE_PACKAGING=OFF
CMAKE_INSTALL_PREFIX=	${PREFIX}

FIX_ME=		Don not build with it option

OPTIONS_DEFINE=	ANSI_MODE ASCII_MODE CONTRIBS DEBUG DEMO DMALLOC \
		INTERNAL_CHAR GPROF MMAP MULTITHREADING STATIC TESTS

ANSI_MODE_DESC=	Compile with -ansi flag
ASCII_MODE_DESC=Enable ascii support
DEMO_DESC=	Build demo
CONTRIBS_DESC=	Building the clucene-contribs
DEBUG_DESC=	Enable debug support
DMALLOC_DESC=	Enable dmalloc memory leak checker (fix me)
INTERNAL_CHAR_DESC=	Use internal character functions (fix me)
GPROF_DESC=	Turn on gprof profiling support (fix me)
MMAP_DESC=	Enable mmap support (experimental)
MULTITHREADING_DESC=	Enable multithreading (fix me)
STATIC_DESC=	Building static libraries
TESTS_DESC=	Enable various projects that test (fix me)

OPTIONS_DEFAULT=INTERNAL_CHAR MULTITHREADING

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MANSI_MODE}
CMAKE_ARGS+=	-DENABLE_ANSI_MODE=ON
.else
CMAKE_ARGS+=	-DENABLE_ANSI_MODE=OFF
.endif

.if ${PORT_OPTIONS:MASCII_MODE}
CMAKE_ARGS+=	-DENABLE_ASCII_MODE=ON
.else
CMAKE_ARGS+=	-DENABLE_ASCII_MODE=OFF
.endif

.if ${PORT_OPTIONS:MDEMO}
CMAKE_ARGS+=	-DENABLE_DEMO=ON
PLIST_SUB+=	DEMO=""
.else
CMAKE_ARGS+=	-DENABLE_DEMO=OFF
PLIST_SUB+=	DEMO="@comment "
.endif

.if ${PORT_OPTIONS:MCONTRIBS}
CMAKE_ARGS+=	-DBUILD_CONTRIBS=ON \
		-DBUILD_CONTRIBS_LIB=ON
PLIST_SUB+=	CONTRIBS=""
.else
CMAKE_ARGS+=	-DBUILD_CONTRIBS=OFF \
		-DBUILD_CONTRIBS_LIB=OFF
PLIST_SUB+=	CONTRIBS="@comment "
.endif

.if ${PORT_OPTIONS:MDEBUG}
CMAKE_ARGS+=	-DENABLE_DEBUG=ON
.else
CMAKE_ARGS+=	-DENABLE_DEBUG=OFF
.endif

.if ${PORT_OPTIONS:MDMALLOC}
BROKEN=		${FIX_ME}
CMAKE_ARGS+=	-DENABLE_DMALLOC=ON
LIB_DEPENDS+=	dmallocthcxx:${PORTSDIR}/devel/dmalloc
.else
CMAKE_ARGS+=	-DENABLE_DMALLOC=OFF
.endif

.if ${PORT_OPTIONS:MINTERNAL_CHAR}
CMAKE_ARGS+=	-DLUCENE_USE_INTERNAL_CHAR_FUNCTIONS=ON
.else
BROKEN=		${FIX_ME}
CMAKE_ARGS+=	-DLUCENE_USE_INTERNAL_CHAR_FUNCTIONS=OFF
.endif

.if ${PORT_OPTIONS:MGPROF}
BROKEN=		${FIX_ME}
CMAKE_ARGS+=	-DENABLE_GPROF=ON
.else
CMAKE_ARGS+=	-DENABLE_GPROF=OFF
.endif

.if ${PORT_OPTIONS:MMMAP}
CMAKE_ARGS+=	-DENABLE_MMAP=ON
.else
CMAKE_ARGS+=	-DENABLE_MMAP=OFF
.endif

.if ${PORT_OPTIONS:MMULTITHREADING}
CMAKE_ARGS+=	-DDISABLE_MULTITHREADING=OFF
.else
CMAKE_ARGS+=	-DDISABLE_MULTITHREADING=ON
BROKEN=		${FIX_ME}
.endif

.if ${PORT_OPTIONS:MSTATIC}
CMAKE_ARGS+=	-DBUILD_STATIC_LIBRARIES=ON
PLIST_SUB+=	STATIC_LIB=""
.else
CMAKE_ARGS+=	-DBUILD_STATIC_LIBRARIES=OFF
PLIST_SUB+=	STATIC_LIB="@comment "
.endif

.if ${PORT_OPTIONS:MTESTS}
BROKEN=		${FIX_ME}
CMAKE_ARGS+=	-DENABLE_COMPILE_TESTS=ON
.else
CMAKE_ARGS+=	-DENABLE_COMPILE_TESTS=ON
.endif

.include <bsd.port.mk>
