# Created by: Gvozdikov Veniamin <g.veniamin@googlemail.com>
# $FreeBSD: databases/tarantool/Makefile 314960 2013-03-22 20:06:14Z makc $

PORTNAME=	tarantool
PORTVERSION=	1.4.8
PORTREVISION=	2
CATEGORIES=	databases
MASTER_SITES=	http://tarantool.org/dist/
DISTNAME=	${PORTNAME}-${PORTVERSION}-${TR_REV}-src

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	High performance key/value storage server

LICENSE=	BSD

TR_REV=		72-g277010b
USES=		cmake
USE_GCC=	4.6+
USE_GETTEXT=	build
USE_GMAKE=	yes
USE_LDCONFIG=	yes
USE_PERL5=	yes
USE_RC_SUBR=	${PORTNAME}
SUB_FILES=	pkg-message
MAN1=		tarantool_box.1

OPTIONS_DEFINE=	CLIENT DEBUG STATIC
CLIENT_DESC=	Enable client
DEBUG_DESC=	Enable debug
STATIC_DESC=	Enable static (got core dump)

OPTIONS_DEFAULT=CLIENT DEBUG

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MCLIENT}
CMAKE_ARGS+=	-DENABLE_CLIENT=true
CFLAGS+=	"-O0 -g"
PLIST_SUB+=	CLIENT=""
MAN1+=		tarantool.1
.else
PLIST_SUB+=	CLIENT="@comment "
.endif

.if ${PORT_OPTIONS:MDEBUG}
CMAKE_ARGS+=	-DCMAKE_BUILD_TYPE=RelWithDebugInfo
.endif

.if ${PORT_OPTIONS:MSTATIC}
CMAKE_ARGS+=	-DENABLE_STATIC=true
.endif

post-install:
	@${CAT} ${PKGMESSAGE}

.include <bsd.port.mk>
