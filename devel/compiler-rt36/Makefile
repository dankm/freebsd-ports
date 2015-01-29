# Created by: Daniel McGregor
# $FreeBSD$

PORTNAME=	compiler-rt
DISTVERSION=	3.6.2
CATEGORIES=	devel
MASTER_SITES=	http://llvm.org/releases/3.6.2/
PKGNAMESUFFIX=	${LLVM_SUFFIX}
DISTNAME=	${CRT_NAME}
DISTFILES=	${CRT_SOURCE}

MAINTAINER=	To be filled out
COMMENT=	Compiler runtime library with sanitizer support

CRT_NAME=	compiler-rt-${DISTVERSION}.src
CRT_SOURCE=	${CRT_NAME}${EXTRACT_SUFX}
CRT_EXTRACT=	compiler-rt-${DISTVERSION}.src

BUILD_DEPENDS=	cmake:${PORTSDIR}/devel/cmake
BUILD_DEPENDS+=	clang${LLVM_SUFFIX}:${PORTSDIR}/lang/clang${LLVM_SUFFIX}
BUILD_DEPENDS+=	llvm-config${LLVM_SUFFIX}:${PORTSDIR}/devel/llvm${LLVM_SUFFIX}

LLVM_SUFFIX=	${PORTVERSION:C/([0-9]\.[0-9]).*/\1/:S/.//g:C/r.//}
LLVM_RELEASE=	${PORTVERSION:C/([0-9]\.[0-9].[0-9]).*/\1/}
LLVM_PREFIX=	${PREFIX}/llvm${LLVM_SUFFIX}
DATADIR=	${PREFIX}/share/${PORTNAME}${LLVM_SUFFIX}
DOCSDIR=	${PREFIX}/share/doc/${PORTNAME}${LLVM_SUFFIX}

# This probably needs expansion
LLVM_ARCH=	${ARCH:C/amd64/x86_64/}

CMAKE_SOURCE_PATH=	${WRKSRC}
CMAKE_INSTALL_PREFIX=	${LLVM_PREFIX}
CMAKE_ARGS=		-DLLVM_CONFIG_PATH=llvm-config${LLVM_SUFFIX} \
			-DCOMPILER_RT_INSTALL_PATH=${LLVM_PREFIX}/lib/clang/${LLVM_RELEASE}

USES=		cmake:outsource tar:xz
USE_LDCONFIG=	yes

CC=	clang${LLVM_SUFFIX}
CXX=	clang++${LLVM_SUFFIX}

PLIST_SUB+=	LLVM_SUFFIX=${LLVM_SUFFIX} \
		LLVM_RELEASE=${LLVM_RELEASE}

ONLY_FOR_ARCHS=	amd64 i386
ONLY_FOR_ARCHS_REASON=	Only tested on amd64 and i386

.include <bsd.port.pre.mk>

.if ${ARCH} == "i386"
PLIST_SUB+=	CRTAMD64="@comment "
PLIST_SUB+=	CRTI386=""
.elif ${ARCH} == "amd64"
PLIST_SUB+=	CRTAMD64=""
PLIST_SUB+=	CRTI386="@comment "
.endif

regression-test:
	cd ${BUILD_WRKSRC} && make test

.include <bsd.port.post.mk>
