# Created by: Steve Wills <swills@FreeBSD.org>
# $FreeBSD$

PORTNAME=	jbuilder
PORTVERSION=	2.3.2
CATEGORIES=	devel rubygems
MASTER_SITES=	RG

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	Create JSON structures via a Builder-style DSL

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/MIT-LICENSE

RUN_DEPENDS?=	rubygem-activesupport4>=3.0.0:${PORTSDIR}/devel/rubygem-activesupport4 \
		rubygem-multi_json>=1.2:${PORTSDIR}/devel/rubygem-multi_json

NO_ARCH=	yes
USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes

.include <bsd.port.mk>
