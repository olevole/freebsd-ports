# Created by: Gvozdikov Veniamin <g.veniamin@googlemail.com>
# $FreeBSD: ports/textproc/py-pyctpp2/Makefile,v 1.3 2012/11/17 06:02:18 svnexp Exp $

PORTNAME=	pyctpp2
PORTVERSION=	0.12.2
PORTREVISION=	1
CATEGORIES=	textproc
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	g.veniamin@googlemail.com
COMMENT=	Python interface to CTPP2 library

LICENSE=	MIT

LIB_DEPENDS=	ctpp2:${PORTSDIR}/textproc/ctpp2

# Python3 ready
USE_PYTHON=	yes
USE_PYDISTUTILS=	easy_install

PLIST_FILES=	%%PYTHON_SITELIBDIR%%/%%PYEASYINSTALL_EGG%%
PYEASYINSTALL_ARCHDEP=	yes

.include <bsd.port.mk>
