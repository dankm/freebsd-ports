# Created by: nork@FreeBSD.org
# $FreeBSD$

PORTNAME=	Crypt-OpenSSL-DSA
PORTVERSION=	0.15
CATEGORIES=	security perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl5 module to DSA signature verification using OpenSSL

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

USES=		perl5
USE_PERL5=	configure
USE_OPENSSL=	yes
MAKE_ARGS+=	PASTHRU_INC=-I${OPENSSLINC}

post-patch:
	@${RM} ${WRKSRC}/lib/Crypt/OpenSSL/DSA.pm.orig

.include <bsd.port.mk>
