# Created by: Sunpoet Po-Chuan Hsieh <sunpoet@sunpoet.net>
# $FreeBSD$

PORTNAME=	tidyp
PORTVERSION=	1.04
PORTREVISION=	2
CATEGORIES=	textproc www
MASTER_SITES=	GHC LOCAL/sunpoet

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Library and program to validate and fix HTML

CONFIGURE_ARGS=	--enable-asian --enable-utf16
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes
USES=		libtool
USE_GITHUB=	yes
GH_ACCOUNT=	petdance

OPTIONS_DEFINE=	ACCESS DEBUG
ACCESS_DESC=	Accessibility checks

PLIST_SUB=	PORTVERSION=${PORTVERSION}

ACCESS_CONFIGURE_ENABLE=access
DEBUG_CONFIGURE_ENABLE=	debug

.include <bsd.port.mk>
