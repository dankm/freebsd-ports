# Created by: Kubilay Kocak <koobs@FreeBSD.org>
# $FreeBSD$

PORTNAME=	requests-oauthlib
PORTVERSION=	0.5.0
CATEGORIES=	www python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	koobs@FreeBSD.org
COMMENT=	OAuthlib authentication support for Requests

LICENSE=	ISCL

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}oauthlib>=0.6.2:${PORTSDIR}/security/py-oauthlib \
		${PYTHON_PKGNAMEPREFIX}requests>=2.0.0:${PORTSDIR}/www/py-requests
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}mock>0:${PORTSDIR}/devel/py-mock

USES=		python
USE_PYTHON=	autoplist distutils

do-test:
	@cd ${WRKSRC} && ${PYTHON_CMD} ${PYDISTUTILS_SETUP} test

.include <bsd.port.mk>
