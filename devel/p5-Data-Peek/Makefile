# $NetBSD: Makefile,v 1.23 2017/08/22 12:16:06 mef Exp $

DISTNAME=	Data-Peek-0.47
PKGNAME=	p5-${DISTNAME}
CATEGORIES=	devel perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=Data/}
EXTRACT_SUFX=	.tgz

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/Data-Peek/
COMMENT=	Perl 5 collection of low-level debug functions
LICENSE=	${PERL5_LICENSE}

USE_LANGUAGES=		c
PERL5_PACKLIST=		auto/Data/Peek/.packlist
MAKE_ENV+=		AUTOMATED_TESTING=1

# For test target
BUILD_DEPENDS+=	p5-Test-NoWarnings-[0-9]*:../../devel/p5-Test-NoWarnings

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
