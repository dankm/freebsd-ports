# Created by: Andrew J. Caines <A.J.Caines@halplant.com>
# $FreeBSD$

PORTNAME=	postfinger
PORTVERSION=	1.30
CATEGORIES=	mail
MASTER_SITES=	ftp://ftp.wl0.org/ftp.wl0.org/postfinger/
DISTFILES=	${DISTNAME} README
DIST_SUBDIR=	${PORTNAME}

MAINTAINER=	A.J.Caines@halplant.com
COMMENT=	Postfix Configuration Summary Reporter

EXTRACT_CMD=		${CP}
EXTRACT_BEFORE_ARGS=
EXTRACT_AFTER_ARGS=	${WRKDIR}
NO_BUILD=		yes
WRKSRC=			${WRKDIR}

PLIST_FILES=	bin/postfinger
PORTDOCS=	README

OPTIONS_DEFINE=	DOCS

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${DISTNAME} \
		${STAGEDIR}${PREFIX}/bin/${PORTNAME}
	${MKDIR} ${STAGEDIR}${DOCSDIR}
.for f in ${PORTDOCS}
	${INSTALL_DATA} ${WRKSRC}/${f} ${STAGEDIR}${DOCSDIR}
.endfor

.include <bsd.port.mk>
