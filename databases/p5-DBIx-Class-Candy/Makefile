# Created by: Wen Heping <wen@FreeBSD.org>
# $FreeBSD$

PORTNAME=	DBIx-Class-Candy
PORTVERSION=	0.005000
CATEGORIES=	databases perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Sugar for your favorite ORM, DBIx::Class

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-DBIx-Class>=0.08123:${PORTSDIR}/databases/p5-DBIx-Class \
		p5-Lingua-EN-Inflect>=0:${PORTSDIR}/textproc/p5-Lingua-EN-Inflect \
		p5-String-CamelCase>=0:${PORTSDIR}/textproc/p5-String-CamelCase
RUN_DEPENDS:=	${BUILD_DEPENDS}
TEST_DEPENDS=	p5-Test-Deep>=0:${PORTSDIR}/devel/p5-Test-Deep \
		p5-Test-Fatal>=0:${PORTSDIR}/devel/p5-Test-Fatal

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
