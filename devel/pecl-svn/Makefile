# Created by: Alex Kiesel <kiesel@schlund.de>
# $FreeBSD$

PORTNAME=	svn
PORTVERSION=	1.0.2
PORTREVISION=	1
CATEGORIES=	devel pear
MASTER_SITES=	http://pecl.php.net/get/
PKGNAMEPREFIX=	pecl-
DIST_SUBDIR=	PECL

MAINTAINER=	ports@FreeBSD.org
COMMENT=	PECL extension to the libsvn library

LICENSE=	PHP301

LIB_DEPENDS=	libsvn_client-1.so:${PORTSDIR}/devel/subversion17

DEPRECATED=	Depends on deprecated subversion17
EXPIRATION_DATE=2015-12-29

USES=		tar:tgz
USE_PHP=	yes
USE_PHPEXT=	yes

.include <bsd.port.mk>
