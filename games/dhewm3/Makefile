# Created by: Dmitry Marakasov <amdmi3@FreeBSD.org>
# $FreeBSD$

PORTNAME=	dhewm3
PORTVERSION=	1.4.0
CATEGORIES=	games

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Doom 3 GPL source port

LICENSE=	GPLv3 # or later
LICENSE_FILE=	${WRKSRC}/../COPYING.txt

LIB_DEPENDS=	libcurl.so:${PORTSDIR}/ftp/curl \
		libogg.so:${PORTSDIR}/audio/libogg \
		libvorbis.so:${PORTSDIR}/audio/libvorbis

USE_GITHUB=	yes
GH_ACCOUNT=	dhewm

USES=		cmake jpeg openal:al
USE_SDL=	sdl2

WRKSRC_SUBDIR=	neo

SUB_FILES=	pkg-message

PORTDOCS=	*

DESKTOP_ENTRIES="dhewm 3" \
		"" \
		"doom3" \
		"${PORTNAME}" \
		"Game;ActionGame;" \
		""

OPTIONS_DEFINE=	OPTIMIZED_CFLAGS DEDICATED DOCS
OPTIONS_DEFAULT=OPTIMIZED_CFLAGS DEDICATED
OPTIONS_SUB=	yes

DEDICATED_DESC=		Build dedicated server
DEDICATED_CMAKE_ON=	-DDEDICATED=ON

post-patch-OPTIMIZED_CFLAGS-off:
	@${REINPLACE_CMD} -e 's|-O3 -ffast-math -fno-unsafe-math-optimizations -fomit-frame-pointer||' ${WRKSRC}/CMakeLists.txt

post-install:
	${MKDIR} ${STAGEDIR}${DATADIR}/base
	${MKDIR} ${STAGEDIR}${DATADIR}/d3xp
	${INSTALL_DATA} ${WRKSRC}/sys/linux/setup/image/doom3.png \
		${STAGEDIR}${PREFIX}/share/pixmaps/

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/../README.md ${STAGEDIR}${DOCSDIR}/

.include <bsd.port.mk>
