# New ports collection makefile for:	clementine-player
# Date created:		2010-03-23
# Whom:			Gvozdikov Veniamin <g.veniamin@googlemail.com>
#
# $FreeBSD: ports/audio/clementine-player/Makefile,v 1.1 2010/04/04 01:22:23 amdmi3 Exp $
#

PORTNAME=	clementine
PORTVERSION=	0.2
PORTREVISION=	1
CATEGORIES=	audio
MASTER_SITES=	GOOGLE_CODE
PKGNAMESUFFIX=	-player
DISTNAME=	${PORTNAME}_${PORTVERSION}-1

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	A cross-platform music player based on Amarok 1.4

LIB_DEPENDS=	lastfm.0:${PORTSDIR}/audio/liblastfm \
		tag.1:${PORTSDIR}/audio/taglib \
		notify.1:${PORTSDIR}/devel/libnotify \
		xine.1:${PORTSDIR}/multimedia/libxine
BUILD_DEPENDS=	${LOCALBASE}/include/boost/shared_ptr.hpp:${PORTSDIR}/devel/boost-libs

PROJECTHOST=	${PORTNAME}${PKGNAMESUFFIX}

USE_CMAKE=	yes
USE_ICONV=	yes
USE_QT_VER=	4
QT_COMPONENTS=	gui xml qmake_build uic_build moc_build rcc_build \
		linguist_build network sql opengl dbus qtestlib corelib
USE_GCC=	4.2+
INSTALLS_ICONS=	yes

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

.include <bsd.port.mk>