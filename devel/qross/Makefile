# Created by: Gvozdikov Veniamin <g.veniamin@googlemail.com>
# $FreeBSD: ports/devel/qross/Makefile,v 1.3 2012/12/12 08:39:42 svnexp Exp $

PORTNAME=	qross
PORTVERSION=	0.2.2
PORTREVISION=	1
CATEGORIES=	devel
MASTER_SITES=	http://cloud.github.com/downloads/0xd34df00d/Qross/

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	Qt-only fork of Kross, the KDE scripting framework

USE_BZIP2=	yes
USE_CMAKE=	yes
USE_LDCONFIG=	yes
USE_QT4=	designer gui network xml qmake_build uic_build moc_build \
		rcc_build script

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}/src

OPTIONS_DEFINE=	PYTHON
OPTIONS_DEFAULT=PYTHON

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MPYTHON}
BUILD_DEPENDS=	sip:${PORTSDIR}/devel/py-sip
PLIST_SUB+=	PYTHON=""
.else
CMAKE_ARGS=	-DENABLE_PYTHON=OFF
PLIST_SUB+=	PYTHON="@comment "
.endif

post-extract:
	@${CP} ${FILESDIR}/CMakeLists.txt ${WRKSRC}

post-install:
.for lib in libqrossui libqrosscore qrossqts
	@${LN} -s ${lib}.so.0.1 ${PREFIX}/lib/${lib}.so.1
.endfor

.include <bsd.port.mk>
