# Created by: Matthias Petermann <matthias@petermann-it.de>
# $FreeBSD$

PORTNAME=	trytond28_stock_supply_production
PORTVERSION=	2.8.0
PORTREVISION=	1
CATEGORIES=	finance python
MASTER_SITES=	https://pypi.python.org/packages/source/t/trytond_stock_supply_production/ \
		http://downloads.tryton.org/${PORTVERSION:R}/
DISTNAME=	trytond_stock_supply_production-${PORTVERSION}

MAINTAINER=	matthias@petermann-it.de
COMMENT=	Tryton Application Platform (Stock Supply Production Module)

LICENSE=	GPLv3

RUN_DEPENDS=	trytond28>=2.8.2:${PORTSDIR}/finance/trytond28 \
		trytond28_stock_supply>=2.8.1:${PORTSDIR}/finance/trytond28_stock_supply \
		trytond28_production>=2.8.0:${PORTSDIR}/finance/trytond28_production \
		trytond28_product>=2.8.0:${PORTSDIR}/finance/trytond28_product

CONFLICTS=	trytond_stock_supply_production-2.[46].*

USES=		python
USE_PYTHON=	distutils autoplist

.include <bsd.port.mk>
