# $FreeBSD$

PORTNAME=	smart_proxy_dynflow
PORTVERSION=	0.0.4
CATEGORIES=	sysutils ruby
MASTER_SITES=	RG

MAINTAINER=	mmoll@FreeBSD.org
COMMENT=	Plugin to use Dynflow in Foreman Smart Proxy

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	foreman-proxy>=1.9.0:${PORTSDIR}/net/foreman-proxy \
		rubygem-dynflow>=0.8.4:${PORTSDIR}/devel/rubygem-dynflow \
		rubygem-sequel>=0:${PORTSDIR}/devel/rubygem-sequel \
		rubygem-sqlite3>=0:${PORTSDIR}/databases/rubygem-sqlite3

NO_ARCH=	yes

USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes

PLIST_FILES=	share/foreman-proxy/bundler.d/dynflow.rb \
		"@sample etc/foreman-proxy/settings.d/dynflow.yml.sample"

post-install:
		${MKDIR} ${STAGEDIR}${PREFIX}/etc/foreman-proxy/settings.d
		${INSTALL_DATA} ${WRKSRC}/settings.d/dynflow.yml.example \
			${STAGEDIR}${PREFIX}/etc/foreman-proxy/settings.d/dynflow.yml.sample
		${MKDIR} ${STAGEDIR}${PREFIX}/share/foreman-proxy/bundler.d
		${INSTALL_DATA} ${WRKSRC}/bundler.d/dynflow.rb \
			${STAGEDIR}${PREFIX}/share/foreman-proxy/bundler.d/dynflow.rb

.include <bsd.port.mk>
