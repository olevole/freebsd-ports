# Created by: Gvozdikov Veniamin <g.veniamin@googlemail.com>
# $FreeBSD$

PORTNAME=	libkpass
PORTVERSION=	5
CATEGORIES=	security
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}-${PORTVERSION}/

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	Library for a reading/writing KeePass 1.x DB

LICENSE=	GPLv3

LIB_DEPENDS=	nettle:${PORTSDIR}/security/nettle

GNU_CONFIGURE=	yes
USE_GMAKE=	yes
USE_LDCONFIG=	yes
CFLAGS+=	-Dbswap_32=bswap32 -Dbswap_16=bswap16 \
		-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

PLIST_FILES=	include/kpass.h \
		lib/libkpass.so \
		lib/libkpass.so.1 \
		lib/libkpass.la \
		lib/libkpass.a

.include <bsd.port.mk>
