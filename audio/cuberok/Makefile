# New ports collection makefile for:	cuberok
# Date created:		2010-05-09
# Whom:			Gvozdikov Veniamin <g.veniamin@googlemail.com>
#
# $FreeBSD: ports/audio/cuberok/Makefile,v 1.1 2010/05/13 06:05:30 wen Exp $
#

PORTNAME=	cuberok
PORTVERSION=	0.1.0
CATEGORIES=	audio
MASTER_SITES=	GOOGLE_CODE

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	A music player and a collection manager based on Qt4

BUILD_DEPENDS=	audiere-config:${PORTSDIR}/audio/audiere \
		${LOCALBASE}/lib/libdumb.a:${PORTSDIR}/audio/dumb
LIB_DEPENDS=	avcodec.1:${PORTSDIR}/multimedia/ffmpeg \
		avformat.1:${PORTSDIR}/multimedia/ffmpeg \
		avutil.1:${PORTSDIR}/multimedia/ffmpeg \
		tag.1:${PORTSDIR}/audio/taglib \
		yajl.1:${PORTSDIR}/devel/yajl

LICENSE=	GPLv3

USE_QT_VER=	4
USE_LDCONFIG=	yes
QT_COMPONENTS=	gui xml qmake_build uic_build moc_build rcc_build \
		network phonon-gst sql
USE_ICONV=	yes
USE_GETTEXT=	yes
USE_SDL=	sdl
QMAKEFLAGS+=	"CONFIG+=player_phonon"
MAKE_ENV+=	INSTALL_ROOT=${PREFIX}
QMAKEPRO=	Cuberok.pro

do-configure:
	cd ${WRKSRC} && ${REINPLACE_CMD} -e 's/lib64/lib/g' \
		plugins/plugins_path-x86*

	@cd ${WRKSRC} && ${SETENV} ${CONFIGURE_ENV} \
		${QMAKE} ${QMAKEFLAGS} ${QMAKE_ARGS}

.include <bsd.port.mk>
