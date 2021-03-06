# Created by: Masahiro Teramoto <markun@onohara.to>
# $FreeBSD$

PORTNAME=	POE-Component-Server-IRC
PORTVERSION=	1.54
CATEGORIES=	irc perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:HINRIK
PKGNAMEPREFIX=	p5-

MAINTAINER=	markun@onohara.to
COMMENT=	Fully event-driven networkable IRC server daemon module

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

RUN_DEPENDS=	p5-Crypt-PasswdMD5>=1.3:${PORTSDIR}/security/p5-Crypt-PasswdMD5 \
		p5-IRC-Utils>=0.10:${PORTSDIR}/irc/p5-IRC-Utils \
		p5-Net-Netmask>=1.9012:${PORTSDIR}/net-mgmt/p5-Net-Netmask \
		p5-POE>=0.9999:${PORTSDIR}/devel/p5-POE \
		p5-POE-Component-Client-DNS>=1:${PORTSDIR}/dns/p5-POE-Component-Client-DNS \
		p5-POE-Component-Client-Ident>=1:${PORTSDIR}/net/p5-POE-Component-Client-Ident \
		p5-POE-Component-IRC>=6.68:${PORTSDIR}/irc/p5-POE-Component-IRC \
		p5-POE-Component-Syndicator>=0.04:${PORTSDIR}/devel/p5-POE-Component-Syndicator \
		p5-POE-Component-SSLify>=0:${PORTSDIR}/security/p5-POE-Component-SSLify \
		p5-POE-Filter-IRCD>=2.2:${PORTSDIR}/irc/p5-POE-Filter-IRCD \
		p5-POE-Filter-Zlib>0:${PORTSDIR}/archivers/p5-POE-Filter-Zlib
BUILD_DEPENDS:=	${RUN_DEPENDS}

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
