# Created by: Andrew Pantyukhin <infofarmer@FreeBSD.org>
# $FreeBSD$

PORTNAME=	aria2
PORTVERSION=	1.19.2
CATEGORIES=	www
MASTER_SITES=	https://github.com/tatsuhiro-t/${PORTNAME}/releases/download/release-${PORTVERSION}/

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Yet another download tool

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

OPTIONS_DEFINE=	CA_BUNDLE DOCS NLS SQLITE
OPTIONS_DEFAULT=SQLITE
OPTIONS_SUB=	yes
CA_BUNDLE_DESC=	Use CA bundle from Mozilla Project

CONFIGURE_ARGS=	--disable-epoll --enable-bittorrent --enable-libaria2 \
		--enable-metalink --enable-shared --enable-ssl --enable-static \
		--enable-threads=posix --enable-websocket \
		--with-disk-cache=${ARIA2_DISK_CACHE} \
		--with-libxml2 --with-libz --with-openssl \
		--without-appletls --without-gnutls --without-libcares \
		--without-libexpat --without-libgcrypt --without-libgmp \
		--without-libnettle --without-libuv
CONFIGURE_ENV=	OPENSSL_CFLAGS=-I${OPENSSLINC} \
		OPENSSL_LIBS="-L${OPENSSLLIB} -lcrypto -lssl" \
		ZLIB_CFLAGS=-I${INCLUDEDIR} \
		ZLIB_LIBS="-L${LIBDIR} -lz" \
		ac_cv_path_RST2HTML=no
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USE_CXXSTD=	c++11
USE_GNOME=	libxml2
USE_LDCONFIG=	yes
USE_OPENSSL=	yes
USE_RC_SUBR=	${PORTNAME}
USES=		compiler:c++11-lib libtool pathfix pkgconfig tar:xz

PORTDOCS=	*

CA_BUNDLE_CONFIGURE_OFF=--without-ca-bundle
CA_BUNDLE_CONFIGURE_ON=	--with-ca-bundle=${LOCALBASE}/share/certs/ca-root-nss.crt
CA_BUNDLE_RUN_DEPENDS=	${LOCALBASE}/share/certs/ca-root-nss.crt:${PORTSDIR}/security/ca_root_nss
NLS_CONFIGURE_OFF=	--disable-nls --without-libintl-prefix
NLS_CONFIGURE_ON=	--with-libintl-prefix=${LOCALBASE}
NLS_LDFLAGS=		-lintl
NLS_USES=		gettext localbase
SQLITE_CONFIGURE_OFF=	--without-sqlite3
SQLITE_CONFIGURE_ON=	--with-sqlite3
SQLITE_USE=		SQLITE=yes

ARIA2_DISK_CACHE?=	16M

.include <bsd.port.mk>
