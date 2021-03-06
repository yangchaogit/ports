# Created by: Dmitry Marakasov <amdmi3@amdmi3.ru>
# $FreeBSD$

PORTNAME=	ode
PORTVERSION=	1.2.0
PORTREVISION=	2
CATEGORIES=	devel python
MASTER_SITES=	SF/py${PORTNAME}/py${PORTNAME}/${PORTVERSION}
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	PyODE-${PORTVERSION}
DIST_SUBDIR=	python

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Python bindings for The Open Dynamics Engine

BUILD_DEPENDS=	${LOCALBASE}/lib/libode.a:${PORTSDIR}/devel/ode

USES=		python tar:bzip2
USE_PYTHON=	distutils
PYDISTUTILS_PKGNAME=	PyODE

OPTIONSFILE=	${PORT_DBDIR}/py-${PORTNAME}/options

OPTIONS_DEFINE=	TRIMESH
OPTIONS_DEFAULT=TRIMESH
TRIMESH_DESC=	Trimesh support (sync with OPCODE opt of devel/ode)

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e 's|/usr/local|${LOCALBASE}|' ${WRKSRC}/setup.py
.if ! ${PORT_OPTIONS:MTRIMESH}
	@${REINPLACE_CMD} -e '/TRIMESH_ENABLE/ s|True|False|' ${WRKSRC}/setup.py
.endif

.include <bsd.port.mk>
