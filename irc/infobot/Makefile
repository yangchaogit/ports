# Created by: perlguy@perlguy.com
# $FreeBSD$

PORTNAME=	infobot
PORTVERSION=	0.45.3
CATEGORIES=	irc
MASTER_SITES=	http://www.infobot.org/src/ \
		http://www.infobot.org/src/prior/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Bot written in Perl with a rabid AI

USES=		perl5
USE_PERL5=	run
NO_BUILD=	yes

OPTIONS_DEFINE=	DOCS

post-patch:
	-@${RM} ${WRKSRC}/src/*.orig
.for i in config help users
	@${RM} ${WRKSRC}/conf/infobot.$i
.endfor

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}
	${CP} -r ${WRKSRC}/src ${WRKSRC}/extras ${WRKSRC}/files \
		${WRKSRC}/scripts ${STAGEDIR}${DATADIR}/
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/doc/* ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/LICENSE ${WRKSRC}/README ${WRKSRC}/REVISIONS ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${ETCDIR}
	${INSTALL_DATA} ${WRKSRC}/conf/* ${STAGEDIR}${ETCDIR}
	${SED} -e 's,$$param{\(.\)basedir\(.\)} = .*,$$param{\1basedir\2} = "${DATADIR}";,' \
	-e 's,$$param{\(.\)confdir\(.\)} = .*,$$param{\1confdir\2} = "${ETCDIR}";,' \
	${WRKSRC}/infobot  > ${WRKDIR}/infobot
	${INSTALL_SCRIPT} ${WRKDIR}/infobot ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
