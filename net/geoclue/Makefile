# Created by: Gustau Perez i Querol <gustau.perez@gmail.com>
# $FreeBSD$

PORTNAME=	geoclue
PORTVERSION=	2.2.0
CATEGORIES=	net devel gnome
MASTER_SITES=	http://www.freedesktop.org/software/geoclue/releases/${PORTVERSION:R}/

MAINTAINER=	gnome@FreeBSD.org
COMMENT=	D-Bus service that provides location information

LIB_DEPENDS=	libjson-glib-1.0.so:${PORTSDIR}/devel/json-glib \
		libsoup-2.4.so:${PORTSDIR}/devel/libsoup

USES=		gettext gmake pathfix pkgconfig tar:xz
USE_GNOME=	glib20 intlhack
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes
CONFIGURE_ARGS=	--disable-3g-source \
		--disable-cdma-source \
		--disable-modem-gps-source
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

.include <bsd.port.mk>
