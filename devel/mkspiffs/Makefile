# $FreeBSD$

PORTNAME=	mkspiffs
PORTVERSION=	0.2.3
CATEGORIES=	devel

MAINTAINER=	y@trombik.org
COMMENT=	Tool to build and unpack SPIFFS images

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

USES=	gmake compiler
USE_GITHUB=	yes
GH_TUPLE=	\
	pellepl:spiffs:f5e26c4:spiffs/spiffs \
	igrr:mkspiffs:0.2.3

MKSPIFFS_VERSION=	${PORTVERSION}
SPIFFS_VERSION=	f5e26c4
ALL_TARGET=	dist

.include <bsd.port.pre.mk>

pre-configure:
	(cd ${WRKSRC} && ${REINPLACE_CMD} \
		-e 's|%%MKSPIFFS_VERSION%%|${MKSPIFFS_VERSION}|g' \
		-e 's|%%SPIFFS_VERSION%%|${SPIFFS_VERSION}|g' \
		Makefile)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/mkspiffs ${STAGEDIR}${PREFIX}/bin/mkspiffs

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/mkspiffs

.include <bsd.port.post.mk>
