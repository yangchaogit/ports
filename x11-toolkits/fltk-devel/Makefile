# Created by: gahr
# $FreeBSD$

PORTNAME=	fltk
DISTVERSION=	1.3.x-r${SNAPSHOT_VERS}
PORTREVISION=	1
CATEGORIES=	x11-toolkits
MASTER_SITES=	http://fltk.org/pub/${PORTNAME}/snapshots/
PKGNAMESUFFIX=	-devel

MAINTAINER=	gahr@FreeBSD.org
COMMENT=	Cross-platform C++ graphical user interface toolkit

LICENSE=	LGPL20

LIB_DEPENDS=	libpng15.so:${PORTSDIR}/graphics/png \
		libjpeg.so:${PORTSDIR}/graphics/jpeg \
		libfreetype.so:${PORTSDIR}/print/freetype2 \
		libfontconfig.so:${PORTSDIR}/x11-fonts/fontconfig

OPTIONS_DEFINE=	EXAMPLES
EXAMPLES_CMAKE_OFF=	-DOPTION_BUILD_EXAMPLES:BOOL=OFF

USE_XORG=	xft
USE_GL=		glu
USE_LDCONFIG=	${PREFIX}/lib/fltk-devel
USES+=		cmake:outsource
LDFLAGS+=	-L${LOCALBASE}/lib
CMAKE_ARGS+=	-DOPTION_BUILD_SHARED_LIBS:BOOL=ON \
    		-DPREFIX_BIN:PATH=${PREFIX}/bin/fltk-devel \
		-DPREFIX_DATA:PATH=${PREFIX}/share/fltk-devel \
		-DPREFIX_DOC:PATH=${PREFIX}/share/examples/fltk-devel \
		-DPREFIX_INCLUDE:PATH=${PREFIX}/include/fltk-devel \
		-DPREFIX_LIB:PATH=${PREFIX}/lib/fltk-devel


SNAPSHOT_VERS=	10370
PORTEXAMPLES=	*
EXAMPLESDIR=	${PREFIX}/share/examples/${PORTNAME}${PKGNAMESUFFIX}

PORTSCOUT=	limit:1.3.*

post-install:
	${INSTALL_SCRIPT} ${INSTALL_WRKSRC}/fltk-config ${STAGEDIR}${PREFIX}/bin/fltk-devel
	${LN} -sf fltk-devel/libfltk.so ${STAGEDIR}${PREFIX}/lib/libfltk-devel.so

.include <bsd.port.mk>
