# $FreeBSD$

PORTNAME=	rednose
PORTVERSION=	0.4.3
PORTREVISION=	1
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	wg@FreeBSD.org
COMMENT=	Coloured output for nosetests

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}colorama>0:${PORTSDIR}/devel/py-colorama \
		${PYTHON_PKGNAMEPREFIX}termstyle>0:${PORTSDIR}/devel/py-termstyle

USES=		python
USE_PYTHON=	distutils autoplist

.include <bsd.port.mk>
